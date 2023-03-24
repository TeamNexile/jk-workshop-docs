---
layout: default
title: Ravens
grand_parent: Level Making
parent: Props
nav_order: 5
last_modified_date: 2023-03-24 13:32
---

# Ravens
{: .no_toc }

the birds that can move and carry an item
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## How do they work?

Ravens use a sequence of multiple positions and can be used to "carry" and "drop items" paired with a graphic showing a raven. The raven will get scared away by getting very close to it, from the current position it will move to the following one.

This will repeat until there are no more positions. You can modify to have it drop an item before flying away for the last time.

### Types

You can have up to 4 different ravens in your level, which are the following:

|Type|Used in|
|---|---|
|raven|The Main Babe's dark raven|
|white_raven|The New Babe Plus' white raven|
|fly|The **really** annoying fly in Ghost of the Babe|
|tsuchinoko|The red bird with human feet in Ghost of the Babe|

<!-- ### Customizing/removing a raven (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Customizing a raven's texture

To customize use the following image as base for your raven:

![Raven]({{site.baseurl}}/images/level-making/raven.png)

> Use the second and fourth row (from top to bottom) with the item that you have in mind to use for the raven to carry.
{: .highlight }

Once done customizing it:

1. Convert the image into a packed XNB file.
2. Name it based on [what raven you want to use](#types).
3. Place the file in `props/textures/raven` and replace the file.

### Customizing a raven's details

1. Navigate to `props/textures/raven` and open the raven's `ravset` file (it's an xml file).
2. Replace the `item` value as your chosen [**Item**]({{site.baseurl}}/api/items).
   > If you want you can replace the `fly_sfx` to either **bird_fly**, **white_bird_fly** or **bug_fly** depending which flight sound effect you want to have.


### Customizing a raven's path

Make sure you have a list of screen numbers and relative positions for your raven to spawn in.

1. Navigate to `props/textures/raven` and open the raven's `ravset` file (it's an xml file).
2. **If it's your first time creating a raven's path**, delete every single `RavenPosition` present.
3. Copy the following snippet:
   ```xml
   <RavenPosition>
    <screen>YOUR_RAVEN_SCREEN</screen>
    <position>
        <X>YOUR_RAVEN_X_POSITION</X>
        <Y>YOUR_RAVEN_Y_POSITION</Y>
    </position>
    <treasure>YOUR_RAVEN_HAS_TREASURE</treasure>
    <look_direction>YOUR_LOOK_DIRECTION</look_direction>
    <fly_direction>YOUR_FLY_DIRECTION</fly_direction>
   </RavenPosition>
   ```
4. Replace `YOUR_RAVEN_SCREEN` with the first screen number position.
5. Replace `YOUR_RAVEN_X_POSITION` and `YOUR_RAVEN_Y_POSITION` with the respective relative position, you might want to tinker this later if it's not precise.
6. If it has the treasure, set `YOUR_RAVEN_HAS_TREASURE` to `true`, otherwise set it to `false`.
   > If the raven was set to true in the previous position, setting it to false will make it drop the carrying item.
7. Replace `YOUR_LOOK_DIRECTION` to either **Left** or **Right**.
8. Replace `YOUR_FLY_DIRECTION` to either **Left** or **Right**.
9.  Repeat Step 3 for each raven position.

### Removing a raven

While you can't inherently remove the files of the raven and that will get rid of your raven there is a tricky way to get it to not spawn in the visible area.

1. Navigate to `props/textures/raven` and open the raven's `ravset` file (it's an xml file).
2. Delete every `RavenPosition` tags.
3. If you encounter issues by opening the game, add the following `RavenPosition` in a new line after the opening tag of `positions`:
   ```xml
   <RavenPosition>
    <screen>0</screen>
    <position>
        <X>0</X>
        <Y>0</Y>
    </position>
    <treasure>false</treasure>
    <look_direction>Left</look_direction>
    <fly_direction>Left</fly_direction>
   </RavenPosition>
   ```

## Next up

[Messages]({{site.baseurl}}/level-making/props/messages).