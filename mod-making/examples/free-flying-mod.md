---
layout: default
title: Free Flying Mod
parent: Mod examples
last_modified_date: 2024-02-19 18:19
---

## Entry Class
In this example we will make a custom `IBodyCompBehaviour` implementation. This behaviour, when registered to the player, will give you the ability to enter a 'Free Flying' mode in the game.
Let's get started with our new project and entry point as described in the [Getting Started](GettingStarted.md) document. We will call this class `FreeFlyingModEntry` to make its purpose clear.

In this case, since we want to modify the Player's behaviour within the world, we will want to make use of the `OnLevelStart` attribute, since we need to make sure a player has been created for us to modify
```cs
using JumpKing.Mods;

namespace JumpKingFreeFlyingMod
{
    /// <summary>
    /// Use the <see cref="JumpKingModAttribute"/> to define details about the current mod
    /// This mod allows the player to toggle a 'free-flying' mode
    /// </summary>
    [JumpKingMod("Example.FreeFlyingMod")]
    public static class FreeFlyingModEntry
    {
        /// <summary>
        /// Called by Jump King when the Level Starts
        /// Dictated by the <see cref="OnLevelStartAttribute"/>
        /// </summary>
        [OnLevelStart]
        public static void OnLevelStart()
        {
            // TODO
        }
    }
}
```
From here we will need to get a reference to the player character, this can be done through the `EntityManager` singleton, which allows us to request a `PlayerEntity` instance.
```cs
PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
```
Once we have our player we can register our new behaviour to it, which can be done with the `RegisterBehaviour` command on its Body Component. 
```cs
// Get the player and register the Free Fly player logic
PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
if (player != null)
{
    // Register a new behaviour for the player to execute each frame
    player.m_body.RegisterBehaviour(new FreeFlyBehaviour());
}
```
Our entry method now looks like this
```cs
using EntityComponent;
using JumpKing.Mods;
using JumpKing.Player;

namespace JumpKingFreeFlyingMod
{
    /// <summary>
    /// Use the <see cref="JumpKingModAttribute"/> to define details about the current mod
    /// This mod allows the player to toggle a 'free-flying' mode
    /// </summary>
    [JumpKingMod("Example.FreeFlyingMod")]
    public static class FreeFlyingModEntry
    {
        /// <summary>
        /// Called by Jump King when the Level Starts
        /// Dictated by the <see cref="OnLevelStartAttribute"/>
        /// </summary>
        [OnLevelStart]
        public static void OnLevelStart()
        {
            // Get the player and register the Free Fly player logic
            PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();
            if (player != null)
            {
                // Register a new behaviour for the player to execute each frame
                player.m_body.RegisterBehaviour(new FreeFlyBehaviour());
            }
        }
    }
}
```
For more information on how the Player and Player Behaviours function, check out the [Player Behaviour](PlayerBehaviour.md) documentation.

We now have our entry method all set up, this will be ran by the game and acts as the starting point for our mod. From here we need to define what `FreeFlyBehaviour` actually does!

## Free Flying Behaviour
Next we can create a new class - called FreeFlyBehaviour - that derives from the `IBodyCompBehaviour` interface. This interface gives the Body Component on the player character the capability to run our logic at the appropriate time.
This interface has one function we are required to provide - `ExecuteBehaviour`, which is ran by the Body Component each frame. It receives a `BehaviourContent` object (which is a way for us to find out information about the game's current state, as well as pass information between different behaviours)
```cs
using JumpKing.API;
using JumpKing.BodyCompBehaviours;

namespace JumpKingFreeFlyingMod
{
    /// <summary>
    /// An implementation of <see cref="IBodyCompBehaviour"/> which allows players to enter a free-flying mode
    /// </summary>
    public class FreeFlyBehaviour : IBodyCompBehaviour
    {
        /// <summary>
        /// Executes our free-flying behaviour, called by the Body Component each frame
        /// </summary>
        public bool ExecuteBehaviour(BehaviourContext behaviourContext)
        {
            // TODO
        }
    }
}
```
Jump King is authored using [MonoGame](https://monogame.net/), so we can leverage any of the engine's functionality to achieve our goals. In this case we want to be able to determine whether a key is pressed or not, we will use this to enter/exit our free flying mode.
We can get the current Keyboard state using the `Keyboard.GetState()` function, and then check if a given key is currently being pressed or not. Note that a check for a key being down will return true *every frame* that key is held down, so if we only want to run some logic *on* the press of a key, rather than *whenever* that key is held down, we need to handle that ourselves with a cooldown flag.
```cs
using JumpKing.API;
using JumpKing.BodyCompBehaviours;
using Microsoft.Xna.Framework;
using Microsoft.Xna.Framework.Input;

namespace JumpKingFreeFlyingMod
{
    /// <summary>
    /// An implementation of <see cref="IBodyCompBehaviour"/> which allows players to enter a free-flying mode
    /// </summary>
    public class FreeFlyBehaviour : IBodyCompBehaviour
    {
        private bool isActive = false;
        private bool freeFlyingToggleCooldown = false;

        private const Keys toggleKey = Keys.F1;

        /// <summary>
        /// Executes our free-flying behaviour, called by the Body Component each frame
        /// </summary>
        public bool ExecuteBehaviour(BehaviourContext behaviourContext)
        {
            KeyboardState state = Keyboard.GetState();

            // Handle toggling logic
            if (state.IsKeyDown(toggleKey) && !freeFlyingToggleCooldown)
            {
                isActive = !isActive;

                freeFlyingToggleCooldown = true;
            }
            else if (state.IsKeyUp(toggleKey) && freeFlyingToggleCooldown)
            {
                freeFlyingToggleCooldown = false;
            }
        }
    }
}
```
We now have an `isActive` bool we can use to determine when our mod should run its logic. In the above example the key used for toggling is a constant, but in reality it could be driven by a config file or any other flow you desire!

Now that we know when we're in the 'Free Flying' state, we want to update the player's location - possibly using the WASD or Arrow keys. To update the player's location in the world we will need to use the Body Component. This can be accessed via the `BehaviourContext` passed in.
```cs
// If active handle movement
if (isActive)
{
    Vector2 velocity = behaviourContext.BodyComp.Velocity;
    float curX = 0;
    float curY = 0;

    // Modify velocity if key is held
    if (state.IsKeyDown(Keys.W))
    {
        curY -= 5;
    }
    if (state.IsKeyDown(Keys.A))
    {
        curX -= 5;
    }
    if (state.IsKeyDown(Keys.D))
    {
        curX += 5;
    }
    if (state.IsKeyDown(Keys.S))
    {
        curY += 5;
    }

    velocity.X = curX;
    velocity.Y = curY;

    behaviourContext.BodyComp.Velocity = velocity;
}
```
Updating the `Velocity` over the `Position` in this case means all other player behaviours that function from velocity (such as collision) should work as expected. This prevents us from flying inside blocks.

Finally we want to return either `true` or `false`. Returning true for a behaviour tells the Body Component to continue executing other behaviours after this, whereas returning false tells it to exit and not execute anything else.

With all this put together our final flying behaviour looks like this!
```cs
using JumpKing.API;
using JumpKing.BodyCompBehaviours;
using Microsoft.Xna.Framework;
using Microsoft.Xna.Framework.Input;

namespace JumpKingFreeFlyingMod
{
    /// <summary>
    /// An implementation of <see cref="IBodyCompBehaviour"/> which allows players to enter a free-flying mode
    /// </summary>
    public class FreeFlyBehaviour : IBodyCompBehaviour
    {
        private bool isActive = false;
        private bool freeFlyingToggleCooldown = false;

        private const Keys toggleKey = Keys.F1;

        /// <summary>
        /// Executes our free-flying behaviour, called by the Body Component each frame
        /// </summary>
        public bool ExecuteBehaviour(BehaviourContext behaviourContext)
        {
            KeyboardState state = Keyboard.GetState();

            // Handle toggling logic
            if (state.IsKeyDown(toggleKey) && !freeFlyingToggleCooldown)
            {
                isActive = !isActive;

                freeFlyingToggleCooldown = true;
            }
            else if (state.IsKeyUp(toggleKey) && freeFlyingToggleCooldown)
            {
                freeFlyingToggleCooldown = false;
            }

            // If active handle movement
            if (isActive)
            {
                Vector2 velocity = behaviourContext.BodyComp.Velocity;
                float curX = 0;
                float curY = 0;

                // Modify velocity if key is held
                if (state.IsKeyDown(Keys.W))
                {
                    curY -= 5;
                }
                if (state.IsKeyDown(Keys.A))
                {
                    curX -= 5;
                }
                if (state.IsKeyDown(Keys.D))
                {
                    curX += 5;
                }
                if (state.IsKeyDown(Keys.S))
                {
                    curY += 5;
                }

                velocity.X = curX;
                velocity.Y = curY;

                behaviourContext.BodyComp.Velocity = velocity;
            }

            // Continue executing behaviours
            return true;
        }
    }
}
```
## Running the Mod
You can now build your mod, drop the built .dll into the game's /Content/JKMods folder, and fire it up! Once booted in, press `F1` to toggle your free-flying mode. 

![A gif showcasing our Free Flying mod]({{ site.baseurl }}/images/mod-making/examples/moddemo_cropped.gif)