---
layout: default
title: Mod Making
has_children: true 
has_toc: false # true if you want the list of subpages
nav_order: 10
last_modified_date: 2024-09-04 13:45 # remember to change this when updating a file (just for UI effect)!
---

<!-- your content -->

# Mod Making
{: .no_toc}
<!-- the .no_toc class prevents to add the title to the following table of contents -->

**everything** you need to know to make a mod.<!-- more -->
{: .fs-6 .fw-300 }

<!-- more -->
<!-- cuts text for "seo"/embed -->

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

> Making a mod for Jump King requires **<u>at least</u>** a basic programming background!<br>**This is not made for starters!**
{: .warning }

## How a mod works under the hood

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

- **BeforeLevelLoadAttribute** - 
    `public static void method`<br>
    Called before Jump King attempts to load the data for the game. You should use this entry point for the registration of any custom blocks or for any logic that the level relies on.

- **OnLevelUnloadAttribute** - `public static void method`<br>
Called when the player swaps to a new map to allow you to unload any data or unregister behaviours that are no longer needed. Eg, if a player started a base game map, but then changes to a Workshop map, or swaps between workshop maps.

- **OnLevelStartAttribute** - `public static void method`<br>
Called when a Level is loaded and the player has been created, but before the user gets a chance to see/act on anything. You should use this entry point for the registration of any behaviours that will affect the player.

- **OnLevelEndAttribute** - `public static void method`<br>
Called when the player stops playing a Level and moved back to the Main Menu, whether this be through the pause menu or by beating the map.

- **PauseMenuItemSetting** - `public static BehaviorTree.IBTSimpleMenuItem method`<br>
Called on pause menu creation, the item will be displayed under the item's menu on Pausemenu's Mods submenu. Can be used together with MainMenuItemSetting.

- **MainMenuItemSetting** - `public static BehaviorTree.IBTSimpleMenuItem method`<br>
Called on main menu creation, the item will be displayed under the item's menu in the main menu Workshop items list. Can be used together with PauseMenuItemSetting.

A mod making use of these attributes would look like this:
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

## Further Reading

- [Player Behaviour]({{site.baseurl}}/mod-making/player-behaviour)
    - A rundown on how the Player functions within Jump King and how you can interface with it using your mod

- [Collision Info]({{site.baseurl}}/mod-making/collision-info)
    - A rundown on how the Player collides within Jump King and how you can interface with it using your mod

- [Block Behaviours]({{site.baseurl}}/mod-making/block-behaviours)
    - A rundown on how blocks can influence how the player behaves in Jump King

- [Advanced Modding using Harmony]({{site.baseurl}}/mod-making/harmony)
    - A brief introduction into 'Harmony' - an open source library that can help you make more advanced mods

## Next up

Once you are done with your mod, read [**Publishing**]({{site.baseurl}}/publishing).