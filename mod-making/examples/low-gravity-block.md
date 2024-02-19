---
layout: default
title: Low gravity block
parent: Mod examples
grand_parent: Mod Making
last_modified_date: 2024-02-19 18:21
---

We have a few requirements for a custom block to be correctly used by the game, these are:
- An `IBlockFactory` implementation which tells the game how to make our block when encountering it during map loading
- An `IBlock` implementation dictating how our block exists within the level (as well as handling any specifics for physics checks)
- (Optional) An `IBlockBehaviour` implementation, which when registered to the player will dictate how the player character should act when encountering this block

## Entry Class
In this example we will create a 'Low Gravity' custom block, create custom behaviour for the player to run when encountering it, and tell the game how to create this block when loading a level that uses it. 

Let's get started with our new project and entry point as described in the [Getting Started](GettingStarted.md) document. We will call this class `LowGravityBlockModEntry` to make its purpose clear.

In this case, we need to both tell the game how to make our block when it's loading a level, and tell the player how to interact with our block. So we will make use of both the `BeforeLevelLoad` and `OnLevelStart` attributes
```cs
using JumpKing.Mods;

namespace JumpKingLowGravityBlockMod
{
    /// <summary>
    /// Use the <see cref="JumpKingModAttribute"/> to define details about the current mod
    /// This mod includes a 'Low Gravity' custom block
    /// </summary>
    [JumpKingMod("Example.LowGravityBlock")]
    public class LowGravityBlockModEntry
    {
        [BeforeLevelLoad]
        public static void BeforeLevelLoad()
        {
            // TODO - Tell the game how to make our block when loading maps that use it
        }

        [OnLevelStart]
        public static void OnLevelStart()
        {
            // TODO - Tell the player how to act when encountering our block
        }
    }
}
```
## Low Gravity Block
First let's create our 'Low Gravity Block' - this acts as the game's representation for each instance of our block in the map. These classes are typically leightweight and mainly dictate the 'solidness' of our block, as well as basics for how collision checks should work.
We make use of the `IBlock` interface, which expects us to provide a hitboc for the block via `GetRect` function and intersection logic via the `Intersects` function. For solid blocks we can instead extend the `BoxBlock` type, which handles all normal collision info for us, but in this case we want the player to move *through* our block (which acts as a 'low gravity' field) rather than be stopped by it, so we'll implement it ourselves.
```cs
using JumpKing.Level;
using Microsoft.Xna.Framework;

namespace JumpKingLowGravityBlockMod
{
    /// <summary>
    /// An implementation of <see cref="IBlock"/> which represents a block capable of creating a low gravity area
    /// impacting the player
    /// </summary>
    public class LowGravityBlock : IBlock
    {
        private readonly Rectangle m_collider;

        /// <summary>
        /// Ctor for creating a <see cref="LowGravityBlock"/> 
        /// </summary>
        /// <param name="p_collider">The <see cref="Rectangle"/> dictating the size of the block</param>
        public LowGravityBlock(Rectangle p_collider)
        {
            m_collider = p_collider;
        }

        /// <summary>
        /// Get the collision rectangle of this block
        /// </summary>
        public Rectangle GetRect()
        {
            return m_collider;
        }

        /// <summary>
        /// Returns whether the provided hitbox is intersecting with this block, and if so gives information about
        /// the collision
        /// </summary>
        /// <param name="p_hitbox">A <see cref="Rectangle"/> to test against</param>
        /// <param name="p_intersection">A <see cref="Rectangle"/> indicating the intersection of the collision</param>
        /// <returns>A <see cref="BlockCollisionType"/> indicating the type of collision</returns>
        public BlockCollisionType Intersects(Rectangle p_hitbox, out Rectangle p_intersection)
        {
            bool ret = m_collider.Intersects(p_hitbox);

            if (ret)
            {
                p_intersection = Rectangle.Intersect(p_hitbox, m_collider);
                return BlockCollisionType.Collision_NonBlocking;
            }
            else
            {
                p_intersection = new Rectangle(0, 0, 0, 0);
                return BlockCollisionType.NoCollision;
            }
        }
    }
}
```
In the above code snippet we can see that our `Intersects` function returns either `BlockCollisionType.Collision_nonBlocking` or `BlockCollisionType.NoCollision` depending on the intersection check performed, this tells the game that the player is either *not* colliding with our block, or they are colliding with it, but can move through it (ie, it is **not blocking** them).

## Low Gravity Block Factory
Now that we have our block, we need to tell the game how to *create* it. A Jump King Map is comprised of a series of coloured squares, as the game parses these squares it will look for registered 'Block Factories' that know how to deal with that colour. Its up to our implementation of the `IBlockFactory` interface to create a block from the provided colour, in some cases there will be a one-to-one mapping of colour-to-block, but in others we may interpret variance in colours to mean different things (eg, a 'Warp Block' may use the colours to indicate where to warp to). 

The `IBlockFactory` interface requires a few functions to be implemented, `CanMakeBlock` is used to tell the game whether this factory can make something with the colour provided, `GetBlock` actively makes a block from the colour, and `IsSolidBlock` tells the game whether the block that would be made from the provided colour is 'solid' or not (meaning can the player be blocked by it). A block factory can (and should!) handle multiple blocks at once, so if your mod contains multiple blocks it's advised to make a single factory that knows how to make them all.

In our case, we will interpret a colour with 69 in the Red, Green, and Blue channels as being a 'Low Gravity' block. 
```cs
using JumpKing.API;
using JumpKing.Level;
using JumpKing.Level.Sampler;
using JumpKing.Workshop;
using Microsoft.Xna.Framework;
using System;
using System.Collections.Generic;

namespace JumpKingLowGravityBlockMod
{
    /// <summary>
    /// An implementation of <see cref="IBlockFactory"/> which knows how to create the Low Gravity Block
    /// </summary>
    public class LowGravityBlockFactory : IBlockFactory
    {
        private static readonly Color BLOCKCODE_LOWGRAVITY = new Color(69, 69, 69); // ha ha nice

        private readonly HashSet<Color> supportedBlockCodes = new HashSet<Color>()
        {
            BLOCKCODE_LOWGRAVITY,
        };

        /// <summary>
        /// Returns <c>true</c> if this factory can create a block from the provided
        /// <see cref="Color"/> block code, returns <c>false</c> if it can't
        /// </summary>
        public bool CanMakeBlock(Color blockCode, Level level)
        {
            return supportedBlockCodes.Contains(blockCode);
        }

        /// <summary>
        /// Returns <c>true</c> if this factory knows the provided code represents a solid block
        /// </summary>
        public bool IsSolidBlock(Color blockCode)
        {
            // LowGravity isnt a solid block, and that's all we know/care about
            return false;
        }

        /// <summary>
        /// Returns an <see cref="IBlock"/> implementation based on the provided inputs for 
        /// block construction
        /// </summary>
        /// <param name="blockCode">The <see cref="Color"/> block code for the target block</param>
        /// <param name="blockRect">The <see cref="Rectangle"/> to use for the block's size and shape</param>
        /// <param name="textureSrc">The <see cref="LevelTexture"/> source for this block in the map file</param>
        /// <param name="currentScreen">The index of the current screen being parsed</param>
        /// <param name="x">The x index of the block on the screen</param>
        /// <param name="y">The y index of the block on the screen</param>
        /// <returns>An <see cref="IBlock"/> implementation</returns>
        /// <exception cref="InvalidOperationException">
        /// Thrown if the factory is unable to create a block from the provided inputs
        /// </exception>
        public IBlock GetBlock(Color blockCode, Rectangle blockRect, JumpKing.Workshop.Level level, LevelTexture textureSrc, int currentScreen, int x, int y)
        {
            if (blockCode == BLOCKCODE_LOWGRAVITY)
            {
                return new LowGravityBlock(blockRect);
            }
            else
            {
                throw new InvalidOperationException($"{typeof(ModDemoBlockFactory).Name} is unable to create a block of Color code ({blockCode.R}, {blockCode.G}, {blockCode.B})");
            }
        }
    }
}

``` 
In the above snippet we declare `BLOCKCODE_LOWGRAVITY` as a constant representing the colour code for a Low Gravity block and keep it in a HashSet of supported block codes. This makes it easier for us to keep track of our block codes and expand our factory if we added any new blocks in future (eg. SuperLowGravityBlock???).

To have the game use our factory, we need to register it, this is done back in the `BeforeLevelLoad` method of our Entry class, and looks like this:
```cs
[BeforeLevelLoad]
public static void BeforeLevelLoad()
{
    // Register the block factory with the level manager, this way the 
    // level manager will know how to make our blocks when encountered in the level loading
    // code
    LevelManager.RegisterBlockFactory(new LowGravityBlockFactory());
}
```
## Low Gravity Block Behaviour
We now have our custom block, and a way for the game to make it when it loads a map that uses it, however our player character has no way of knowing how to act when it encounters our block. To change this we need to create an implementation of `IBlockBehaviour` and register it to our player.

The `IBlockBehaviour` interface gives us plenty of options, for this case we only care about the `ExecuteBlockBehaviour` and `ModifyGravity` functions, and the `BlockPriority` and `IsPlayerOnBlock` properties. For more information on this API check out the [Block Behaviours](BlockBehaviours.md) documentation.

```cs
using JumpKing.API;
using JumpKing.BodyCompBehaviours;
using JumpKing.Level;

namespace JumpKingLowGravityBlockMod
{
    /// <summary>
    /// An implementation of <see cref="IBlockBehaviour"/> representing how the <see cref="LowGravityBlock"/> will
    /// affect the player during runtime
    /// </summary>
    public class LowGravityBlockBehaviour : IBlockBehaviour
    {
        /// <summary>
        /// The priority of this block. This will determine what order it's actions are ran in
        /// Lower numbers are ran first.
        /// </summary>
        public float BlockPriority => 2f;

        /// <summary>
        /// Cached state of whether the player is currently on this block or not
        /// </summary>
        public bool IsPlayerOnBlock { get; set; }

        /// <inheritdoc/>
        public bool AdditionalXCollisionCheck(AdvCollisionInfo info, BehaviourContext behaviourContext)
        {
            // Do nothing to affect collision checks
            return false;
        }

        /// <inheritdoc/>
        public bool AdditionalYCollisionCheck(AdvCollisionInfo info, BehaviourContext behaviourContext)
        {
            // Do nothing to affect collision checks
            return false;
        }

        /// <inheritdoc/>
        public float ModifyXVelocity(float inputXVelocity, BehaviourContext behaviourContext)
        {
            // Do nothing and return input velocity unmodified
            return inputXVelocity;
        }

        /// <inheritdoc/>
        public float ModifyYVelocity(float inputYVelocity, BehaviourContext behaviourContext)
        {
            // Do nothing and return input velocity unmodified
            return inputYVelocity;
        }

        /// <summary>
        /// Modify the Gravity that is to be applied to the Player's Y Velocity as 
        /// part oof the update step
        /// </summary>
        /// <param name="inputGravity">The current Y gravity that would be applied</param>
        /// <param name="behaviourContext">An instance of <see cref="BehaviourContext"/> containing references to the player</param>
        /// <returns>The new Gravity that will be applied to the player</returns>
        public float ModifyGravity(float inputGravity, BehaviourContext behaviourContext)
        {
            return inputGravity * (IsPlayerOnBlock ? 0.01f : 1f);
        }

        /// <summary>
        /// Block-specific behaviour that may or may not affect the player. Executed during the player's update step.
        /// </summary>
        /// <param name="behaviourContext">An instance of <see cref="BehaviourContext"/> containing references to the player</param>
        /// <returns>
        /// <c>true</c> if the player's update step should continue after this. <c>false</c> if it shouldn't.
        /// </returns>
        public bool ExecuteBlockBehaviour(BehaviourContext behaviourContext)
        {
            // We determine if the player is colliding with this block by checking the state of the player prior to 
            // any collision resolution steps that took place this frame. We see if it was colliding with a Low 
            // Gravity Block and cache that state for reference elsewhere
            if (behaviourContext?.CollisionInfo?.PreResolutionCollisionInfo != null)
            {
                IsPlayerOnBlock = behaviourContext.CollisionInfo.PreResolutionCollisionInfo.IsCollidingWith<LowGravityBlock>();
            }
            return true;
        }
    }
}
```
We first set `BlockPriority` to be a sensible value, with this being our only block it doesn't really matter, but base game blocks are at priority '1' so lets set ours to '2' so it always runs after them.

We then define the `IsPlayerOnBlock` property, this is used to cache the collision state of the player across one-or-more frames. The various functions of this behaviour are called at different times in the player's update method, so this cached state gives us a way to know whether we should run any specialised logic or not. For base game blocks this flag is potentially set/unset by the various nuances of the collision resolution steps, however for our custom blocks we will typically handle it during the `ExecuteBlockBehaviour` function, like we do above.

The `ModifyGravity` function is where our block shines, this is called by the `ApplyGravityBehaviour` step of the Body Component's update function, here we check if the player is on the block or not, and if so modify the input gravity - lowering it to 1/100th of its normal value.

To tell our player character to use this new block behaviour we need to register it, as well as tell the player which block type it refers to. This is done in the `OnLevelStart` function in our Entry class, which looks like this:
```cs
[OnLevelStart]
public static void OnLevelStart()
{
    // Get the player and register the Low Gravity block's behaviour
    PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
    if (player != null)
    {
        // Register a new block behaviour to the player
        // this is used for the player to know how to react when encountering a LowGravityBlock
        player.m_body.RegisterBlockBehaviour(typeof(LowGravityBlock), new LowGravityBlockBehaviour());
    }
}
```
## Running the Mod
You can now build your mod, drop the built .dll into the game's /Content/JKMods folder, and fire it up! However, without a custom map that uses our block, it will never be created. You may find it useful to unpack the `level.xnb` file of the base game's map (as well as any relevant foreground/background images), modify it, and then re-package it. These files can be found in the /Content/ folder (and relevant subfolders).

For this demo, I modified the `level.xnb` and foreground `1.xnb` file to contain my new block colour code (and a little visual so I could see it in game). I then re-packaged the files and dropped them over the existing files used by the base game.

![An edited level.xnb and 1.xnb file to use our Low Gravity Block]({{ site.baseurl }}/images/mod-making/examples/image.png)

**The details of how to unpack and repack XNB files will not be covered in this document. However there are plenty of resources online covering this step*

You can now run the game and see your block in action!

![Alt text]({{ site.baseurl }}/images/mod-making/examples/moddemo2.gif)