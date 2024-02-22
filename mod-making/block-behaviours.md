---
layout: default
title: Block Behaviours
parent: Mod Making
nav_order: 3
last_modified_date: 2024-02-22 12:09
---

# Block Behaviours 
A 'Block Behaviour' implements the `IBlockBehaviour` interface and is responsible for controlling how a given type of block affects the player during play.

A block may affect the player outside of any given 'instance' of the block, lets say we have a 'black hole' block that pulls the player into an orbit around it - we'd want multiple blocks next to each other to all affect the player at once.

To give this flexibility the onus of controlling this behaviour is given to the _player_ through this 'Block Behaviour' object.

The `IBlockBehaviour` interface requires you to implement the following:
- `BlockPriority` block behaviours with a lower priority number are ran first
- `IsPlayerOnBlock` a way for other parts of code to determine if the player is on a block or not. It's up to you how you determine if the player is "on" your block or not and keep this bool up to date.
- `ModifyXVelocity` a way to modify the X velocity of the player before it is applied to the player's position
- `ModifyYVelocity` a way to modify the Y velocity of the player before it is applied to the player's position
- `ModifyGravity` a way to modify the gravity before it is applied to the player's velocity
- `AdditionalXCollisionCheck` & `AdditionalYCollisionCheck` allow you to provide any block-specific collision checks that will be performed when doing the collision resolution step of the player's BodyComp update tick. If your block has specific collision logic (eg, Sand) then this is a good way to set it up
- `ExecuteBlockBehaviour` is a simple 'update' method for your block behaviour to run any extra arbitrary code it needs to. This is a good place to check and update `IsPlayerOnBlock` for example.

## Registering Block Behaviours
To register a block behaviour with the player, we need to call the `RegisterBlockBehaviour` function on the `BodyComp` component. This should be called as part of the `OnLevelStart` function (the player entity doesnt exist unless the level has started!)

```cs
[OnLevelStart]
public static void OnLevelStart()
{
    PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
    if (player != null)
    {
        player.m_body.RegisterBlockBehaviour<LowGravityBlock>(new LowGravityBlockBehaviour());
    }
}
```
A more detailed example of this can be found in the [Low Grabity Mod example]({{site.baseurl}}/mod-making/examples/low-gravity-block)

## Example - IceBlockBehaviour
All of the block behaviours used by the base game follow this API - for example, the code that controls how Ice affects the player is driven by the `IceBlockBehaviour` implementation.

_*Though typically the `IsPlayerOnBlock` logic is handled by other parts of the game, a quirk which was retained when refactoring the game for mod support_

```cs
/// <summary>
/// An implementation of <see cref="IBlockBehaviour"/> controlling how the <see cref="IceBlock"/>
/// affects the player.
/// Since Ice ties in a lot with Ground checks, we need to know about the player's current ground state often
/// so this uses <see cref="BodyComp"/> regularly
/// </summary>
public class IceBlockBehaviour : IBlockBehaviour
{
    /// <inheritdoc/>
    public float BlockPriority => 2f;

    /// <inheritdoc/>
    public bool IsPlayerOnBlock 
    { 
        get
        {
            if (InventoryManager.HasItemEnabled(Items.SnakeRing))
            {
                return m_bodyComp.IsOnGround;
            }

            return m_isPlayerOnBlock;
        }
        set
        {
            m_isPlayerOnBlock = value;
        }
    }
    private bool m_isPlayerOnBlock;

    private readonly BodyComp m_bodyComp;

    /// <summary>
    /// Ctor for creating an <see cref="IceBlockBehaviour"/>
    /// </summary>
    /// <param name="bodyComp">The player's <see cref="BodyComp"/> component</param>
    public IceBlockBehaviour(BodyComp bodyComp)
    {
        this.m_bodyComp = bodyComp ?? throw new ArgumentNullException(nameof(bodyComp));
    }

    /// <inheritdoc/>
    public float ModifyXVelocity(float inputXVelocity, BehaviourContext behaviourContext)
    {
        return inputXVelocity;
    }

    /*
    .
    . Ice doesnt modify velocity before being applied, nor does it change gravity
    . so these methods have been omitted from the example for brevity
    .
    .*/

    /// <inheritdoc/>
    public bool ExecuteBlockBehaviour(BehaviourContext behaviourContext)
    {
        BodyComp bodyComp = behaviourContext.BodyComp;
        if (IsPlayerOnBlock)
        {
            bodyComp.Velocity.X = ErikMaths.ErikMath.MoveTowards(bodyComp.Velocity.X, 0, PlayerValues.ICE_FRICTION);
        }
        return true;
    }
```