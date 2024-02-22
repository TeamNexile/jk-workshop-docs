---
layout: default
title: Mod Making
has_children: true 
has_toc: false # true if you want the list of subpages
nav_order: 9
last_modified_date: 2024-02-20 18:03 # remember to change this when updating a file (just for UI effect)!
---

<!-- your content -->

# Mod Making
{: .no_toc}
<!-- the .no_toc class prevents to add the title to the following table of contents -->

<!-- more -->
<!-- cuts text for "seo"/embed -->

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Getting started
Jump King has a world of modding capabilities, and as part of the Workshop update we have refactored and exposed a series of game systems to support the creation of mods. A mod for Jump King can be split broadly into three categories:
- Custom Content (Maps, Sprites, Sounds)
- Custom Blocks (New block types used by custom maps)
- Custom Behaviours (New game modes or in-game functionality)

The mods you create may end up being a combination of these three categories. Here we will run you through the authoring process for creating some simple options to get you on your way to making your first mod.

## Setting up Mod Projects
Mods that contain custom blocks and/or behaviours will be comprised of a C# project that outputs a Library (.dll), it is advised that you target .NET Framework 4.5.

To make use of the attributes and types referenced by Jump King you will need to add it as a reference to your project, how to do this varies depending on your IDE of choice. For Visual Studio, go to the Solution Explorer and right click on the 'References' option underneath your project and select 'Add Reference', then select the 'Browse...' button in the bottom right and navigate to the JumpKing.exe in your Steam install directory.

Your project has a single entry point, denoted by the `[JumpKingMod]` attribute affixed to a static class. This attribute should contain a unique name to identify your mod, this will help you debug any errors that may arise during the authoring of your work.

```cs
using JumpKing.Mods;

namespace MyCoolMod
{
    [JumpKingMod("MyName.MyCoolMod")]
    public static class MyCoolMod
    {
    }
}
```

This attribute is what tells Jump King where to look to find the 'setup' logic for your mod. From here there are four potential entry points you can register to, which you can use to set up and plug in your systems. This is done through the use of some additional attributes. When loading your mod, Jump King will note which methods contain these attributes and call them at the appropriate time.
- **BeforeLevelLoadAttribute** - Called before Jump King attempts to load the data for the game. You should use this entry point for the registration of any custom blocks or for any logic that the level relies on.
- **OnLevelUnloadAttribute** - Called when the player swaps to a new map to allow you to unload any data or unregister behaviours that are no longer needed. Eg, if a player started a base game map, but then changes to a Workshop map, or swaps between workshop maps.
- **OnLevelStartAttribute** - Called when a Level is loaded and the player has been created, but before the user gets a chance to see/act on anything. You should use this entry point for the registration of any behaviours that will affect the player.
- **OnLevelEndAttribute** - Called when the player stops playing a Level and moved back to the Main Menu, whether this be through the pause menu or by beating the map.

A mod making use of these attributes would look like this
```cs
using JumpKing.Mods;

namespace MyCoolMod
{
    [JumpKingMod("MyName.MyCoolMod")]
    public static class MyCoolMod
    {
        [OnLevelStart]
        public static void OnLevelStart()
        {
            // Get the player
            PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();

            // Do something...
        }
    }
}
```

A project/mod should have a single entry point, but it can be used to setup whatever suite of behaviours and logic your mod requires! 

### Debugging & Testing
In order to test your mod locally, you need only build it into a .dll, and then place this file (and any dependencies!) in the /Content/JKMods/ folder in your Jump King game's Steam install directory. It will now be loaded when the game is ran.

> If using Visual Studio, you can attach a debugger to the Jump King game directly to breakpoint and navigate through any of your custom code when it is loaded.

> If you're struggling - you can add `Debugger.Launch()` to your mod temporarily, which will prompt you to attach a debugger instance to the game when it is hit.

Additional logs about the game's `ModLoadLog.txt` and `crashlog.log` files respectively, which should both be found next to the JumpKing.exe

### Visual Studio Project Templates
Coming Soon

## Further Reading
- [Player Behaviour]({{site.baseurl}}/mod-making/player-behaviour)
    - A rundown on how the Player functions within Jump King and how you can interface with it using your mod
- [Collision Info]({{site.baseurl}}/mod-making/collision-info)
    - A rundown on how the Player collides within Jump King and how you can interface with it using your mod
- [Block Behaviours]({{site.baseurl}}/mod-making/block-behaviours)
    - A rundown on how blocks can influence how the player behaves in Jump King
- [Advanced Modding using Harmony]({{site.baseurl}}/mod-making/harmony)
    - A brief introduction into 'Harmony' - an open source library that can help you make more advanced mods