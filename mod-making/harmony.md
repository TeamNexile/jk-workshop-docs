---
layout: default
title: Advanced Modding using Harmony
parent: Mod Making
nav_order: 4
last_modified_date: 2024-02-20 18:07
---

# Advanced Modding using Harmony
Great care has been taken to design, refactor, and implement an API that gives you the flexibility to implement any number of mods that affect game code. 

However there's always limits to what you can do with what Jump King exposes, and in these cases Harmony is an option you can leverage to push the limits of your creativity!

## Harmony
Harmony is an Open Source library for patching, replacing, and decorating .NET functions during the runtime.

You can use Harmony to have custom code run before, after, or instead of any methods in Jump King, and is how a lot of the early mods for the game were written.

Learn more about Harmony here: https://github.com/pardeike/Harmony

Learn more about how to use Harmony here: https://harmony.pardeike.net/articles/intro.html

## Patching Etiquette
You should always assume that a player may have more than just your mod installed, so try to prevent implementing any patching logic that could stop other modder's code from running. 

For example, you could add a patch method to run before the `JumpState.DoJump` function. At the end of your function you can return `true` to allow the original DoJump (or any other patches) to continue, or `false` to prevent it.

Now your mod may have an appropriate reason to stop the player from jumping (maybe they are meant to be in some form of cutscene or stuck state for your mod) but keep in mind this could prevent other mods from having their code executed.