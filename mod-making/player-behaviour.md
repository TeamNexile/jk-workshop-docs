---
layout: default
title: Player Behaviour
parent: Mod Making
nav_order: 1
last_modified_date: 2024-02-19 18:29
---

# Player Behaviour
## The Player
The player in Jump King consists of a en Entity (PlayerEntity.cs), and a series of Components - one of the more common ones being Node Trees (also referred to as a Behaviour Tree).
The majority of the logic of how the player interacts with the world around them is handled by the 'Body Component' (BodyComp.cs).

Each Entity has an 'Update' method, which is called each frame, and is then followed by a the update of any 'Enabled' component also being called.

As part of the work to refactor Jump King and make it suitable for modding the various steps of the player's behaviour, the BodyComp's logic was split into a series of 'Behaviours' (IBodyCompBehaviour.cs) covering each operation needing to be performed in a given frame. Data is passed between behaviours through a provided 'BehaviourContext' object.

The aforementioned node tree contains various other nodes controlling ways of managing player velocity and animations. This velocity is then used by the BodyComp to drive the player's interaction with the world.

You can access the PlayerEntity from most of your code through the Entity Manager
```cs
PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
```

You can get the BodyComp of a PlayerEntity (or any other node) like so:
```cs
BodyComp bodyComponent = player.GetComponent<BodyComp>();
```

You can access a specific Node from the behaviour tree a few ways depending on what you care about:
```cs
// The behaviour tree is contained within a Behaviour Tree Component
BehaviourTreeComp behaviourTreeComponent = player.GetComponent<BehaviorTreeComp>();
BTmanager behaviourTree = behaviourTreeComponent.GetRaw();

// This will get you the parent of the node you specify, useful if you want to add steps to run before/after it
// as there is no way to traverse 'up' a node tree
IBTcomposite walkSequencor = behaviourTreeComponent.FindParentNodeOf<WalkAnim>() as IBTcomposite;

// This will get you the first instance of the specified node, useful if you want to modify its behaviour in some way
WalkAnim walkAnimNode = behaviourTreeComponent.FindNode<WalkAnim>();
```

To summarise:
- Player Entity (PlayerEntity)
    - Components
        - Body Component (BodyComp)
            - Collection of Behaviours (IBodyCompBehaviour)
        - Input Component (InputComponent)
        - Node Tree (BehaviourTreeComp)
            - Walk Velocity Node (Walk)
            - Walk Anim Node (WalkAnim)
            - Jump Charging Node (JumpState)
            - etc
    
## BodyComp Behaviours
The base behaviour of the BodyComp is comprised of the following behaviours in the following order:
- **CacheCollisionStateBehaviour**
    - Caches initial states of the player's collision at the start of the frame. Used to set some states of the base game blocks
    - Sets the `StartOfFrameCollisionInfo` of the `BehaviourContext` object passed to other behaviours
- **WindVelocityUpdateBehaviour**
    - If the current screen has wind enabled it updates the X velocity of the player based on the current wind velocity
- **CacheLastScreenBehaviour**
    - Caches the current screen index the player is on to the `LastScreen` property of `BodyComp`
- **WaterParticleSpawningBehaviour**
    - If we were on a water block last frame and aren't this frame (or vice versa) this creates an appropriate water 'splash' particle
- **CacheVelocityBehaviour**
    - Caches the current velocity to the `LastVelocity` property of `BodyComp`
- **CollisionCheckEarlyExitBehaviour**
    - If the player is currently colliding with a block then the previous frame didn't fully resolve things and we early exit, preventing further behaviours from running
- **UpdateXPositionFromVelocityBehaviour**
    - Updates the `Position` property of the `BodyComp` based on the current `Velocity`
    - Registered `IBlockBehaviour` implementations have an opportunity to modify the velocity prior to it being applied via their `ModifyXVelocity` methods
- **CapPositionBehaviour**
    - Caps the player's X position between bounds of the screen
    - Doesn't run if the current screen has Teleporting somewhere in it
    - If it runs it adds a "CappedXPosition" flag to the `BehaviourContext` which is reset at the start of the next frame
- **HandlePlayerTeleportBehaviour**
    - If the current screen allows teleporting and the player's position exceeds the bounds of the screen it handles teleporting the player to the approproiate end position
    - If it runs it adds a "TeleportedPlayer" flag to the `BehaviourContext` which is reset at the start of the next frame
- **CachePreCollisionResolutionCollisionStateBehaviour**
    - Saves the current collision state of the player to the `PreResolutionCollisionInfo` property of the `CollisionInfo` in the `BehaviourContext` 
- **ResolveXCollisionBehaviour**
    - Resolves any collisions affecting the player by moving them along the X axis until they are no longer colliding with any solid blocks
    - It moves the player by a step (1 pixel) in the appropriate direction iteratively checking the collision state of the player after each movement.
    - Registered `IBlockBehaviour` implementations can require additional checks to be performed through the `AdditionalXCollisionCheck` method
    - If the player touched a slope as part of this flow the "TouchedXSlope" flag is added to the `BehaviourContext` which is reset at the start of the next frame
    - If the player is being put in a 'Knocked' state from this operation, the "PlayBumpSFX" flag is added to the `BehaviourContext` which is reset at the start of the next frame
- **UpdateYPositionFromVelocityBehaviour**
    - Updates the `Position` property of the `BodyComp` based on the current `Velocity`
    - Registered `IBlockBehaviour` implementations have an opportunity to modify the velocity prior to it being applied via their `ModifyYVelocity` methods
- **CachePreCollisionResolutionCollisionStateBehaviour**
    - Aggregates the current collision state of the player to the `PreResolutionCollisionInfo` property of the `CollisionInfo` in the `BehaviourContext` 
    - The `PreResolutionCollisionInfo` property ends up being a collection of every block that the player "has" collided with this frame, regardless of whether it has then resolved that collision or not
- **ResolveYCollisionBehaviour**
    - Resolves any collisions affecting the player by moving them along the Y axis until they are no longer colliding with any solid blocks
    - It moves the player by a step (1 pixel) in the appropriate direction iteratively checking the collision state of the player after each movement.
    - Registered `IBlockBehaviour` implementations can require additional checks to be performed through the `AdditionalYCollisionCheck` method
- **ApplyGravityBehaviour**
    - Applies Gravity to the `Velocity` of the `BodyComp`
    - Gives all registered `IBlockBehaviour` implementations a chance to modify the gravity using their `ModifyGravity` method
- **ExecuteBlockBehaviours**
    - Calls `ExecuteBlockBehaviour` on all registered `IBlockBehaviour` implementations
    - This is how we have custom blocks run any special logic they need
- **GuardtowerSoulBugFixBehaviour**
    - Deals with a specific edge case with Slope and Y collisions that caused some issues in the base game around the Guardtower
- **PlayBumpSFXBehaviour**
    - If the `BehaviourContext` has the "PlayBumpSFXFlag" set it plays the appropriate bump SFX

## Adding/Removing Behaviours
You will likely want to add your own behaviours to the BodyComp, or in some cases, replace/remove existing ones!

To add a new behaviour you simply need to call `BodyComp.RegisterBehaviour` with an instance of an `IBodyCompBehaviour` class.
```cs
PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
player.m_body.RegisterBehaviour(new MyCoolModBehaviour());
```

If you want your custom behaviour to run at a specific time in the update loop, you can call the `RegisterBehaviourBefore` or `RegisterBehaviourAfter` methods. To get a list of existing behaviours call the `GetBehaviourList` method
```cs
PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();

// Get a list of all current behaviours
IReadOnlyCollection<IBodyCompBehaviour> existingBehaviours = player.m_body.GetBehaviourList();

foreach (var behaviour in existingBehaviours)
{
    if (behaviour is ResolveXCollisionBehaviour)
    {
        // Make our new behaviour
        var newBehaviour = new MyCoolPreCollisionBehaviour();

        // Register it to run before the X collision resolve
        player.m_body.RegisterBehaviourBefore(behaviour, newBehaviour);
        break;
    }
}
```

You can remove a specific behaviour through the `RemoveBehaviour` function
```cs
PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();

// Get a list of all current behaviours
IReadOnlyCollection<IBodyCompBehaviour> existingBehaviours = player.m_body.GetBehaviourList();

foreach (var behaviour in existingBehaviours)
{
    if (behaviour is ResolveXCollisionBehaviour)
    {
        // Remove the collision behaviour
        player.m_body.RemoveBehaviour(behaviour);
        break;
    }
}
```