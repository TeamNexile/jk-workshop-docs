---
layout: default
title: Props
parent: Level Making
nav_order: 5
last_modified_date: 2021-12-19 14:05
---

# Props folder
{: .no_toc }

contains textures and settings of props used in-game.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Good practice with props
Avoid using props in the final screen to prevent slight visual bugs from the game after beating the level.

<hr>

## World items

are **items that the player can pick up** by walking on them. These world items have their own texture inside `/mods/props/worlditems`. 


In order to have the world items working in-game, the game reads a file called `worlditems.xml` inside the folder specified above. This file contains an `<items>` tag which is an array (multiple instances) of the `<WorldItemState>` tag.

### WorldItemState
<p class="do-i-need-it">optional</p>

contains the information of a single world item.

`<WorldItemState>` contains:
- the name of the item (using the `<item>` tag)
- the number of the screen (using the `<screen>` tag)
- the position on the screen (using the `<_x>` and `<_x>` tags)

Following the logic, you'll end up with a `worlditems.xml` file like this:

<script src="https://gist.github.com/Phoenixx19/79522e0b5424f17bc8f5821e65885306.js"></script>

<br>

## NPCs
are the entities that talk and barter with you.

> **NPCs are hardcoded** in the game, so they *can not be removed*; but they **can be reskinned and moved** to a screen you are not using (like 169, the last screen possible in the game limitations).

NPCs can be of two types:
1. `old man`, a normal entity that only speaks
2. `merchant`, an extension of the `old man` but can also barter items with the player.

While the textures for both needs to be inside `textures/old_man`, the quotes and settings of each NPC is stored based of their type:
- `old man`, is stored inside `textures/old_man/lines`
- `merchant`, is stored inside `textures/old_man/merchant`


### Old Man

This following XML file explains one of the Old Man NPC-types, `hermit_quotes.xml`.

<script src="https://gist.github.com/Phoenixx19/44ac06687463a5ba28c6489948dba576.js"></script>

### Merchant

The following XML file **explains only** the other tags that need to be added if you want to make a merchant NPC. The tag `<settings>` contains the details above.

<script src="https://gist.github.com/Phoenixx19/69cbef46f1ac061b54d8b3afe8ab3dbe.js"></script>

### Item trigger

Implemented from <span class="badge-pill">**v1.5.0**</span>, you can create quotes that trigger when wearing an item.

|tag|description|
|---|---|
|`<items>`|multiple instances of `<OldManItem>`|
|`<OldManItem>`|Contains the info for every item trigger|
|`<item>`|Item name|

An example of item trigger:
```xml
<items>
  <OldManItem>
    <item>Cap</item>
    <quotes>
      <OldManQuote>
        <lines>
          <string>Sick hat, bro!</string>
        </lines>
      </OldManQuote>
    </quotes>
  </OldManItem>
  <!-- add another OldManItem, if you want another trigger -->
</items>
```

### Fall trigger

Implemented from <span class="badge-pill">**v1.5.0**</span>, you can create quotes that triggers when the amount of falls is reached.

|tag|description|
|---|---|
|`<falls>`|multiple instances of `<OldManFalls>`|
|`<OldManFalls>`|Contains the info for every item trigger|
|`<fallStart>`|Minimal fall number (number included!)|
|`<fallEnd>`|Maximum fall number|

An example of a fall trigger:
```xml
<falls>
  <OldManFall>
    <fallStart>15</fallStart> <!-- you can use 15 for fallEnd for the next OldManFall -->
    <fallEnd>20</fallEnd> <!-- you can use 20 for fallStart for the next OldManFall -->
    <quotes>
      <OldManQuote>
        <lines>
          <string>Just stop falling to get the babe!</string>
        </lines>
      </OldManQuote>
    </quotes>
  </OldManFall>
  <!-- add another OldManFall, if you want another trigger -->
</falls>
```

<br>


## Raven
is the entity related to the bird.

It is located inside the `textures/raven` folder. The folder should contain:
- the raven texture `(raven name).xnb`
- the configuration file `(raven name).ravset` (which is an xml file named ravset).

> Ravens are also hardcoded in the game. Please use the ones already available.

The following file shows an example of a raven.

<script src="https://gist.github.com/Phoenixx19/70bcf8d5b40f76d12a628dd71642f241.js"></script>

<br>

## Props

are details (that can also be animated!) on screen.

The props in-game (such as the bonfire in the first screen) are stored in the `props/textures` folder. Inside this folder, there's a configuration file named `prop_settings.xml` which contains a list of `<PropSetting>` tags.

### PropSetting
<p class="do-i-need-it">required</p>

is the setting file for every single prop.

|name|description|
|---|---|
|`<name>`|Name of the file|
|`<fps>`|Frames per second|
|`<frames>`|float[]|
|`<float>`|Time per frame|
|`<sheet_cells>`|Size of the spritesheet|
|`<X>`|Columns|
|`<Y>`|Rows|
|`<random_offset>`|Optional tag to get random offsets|

```xml
<?xml version="1.0"?>
<PropSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <settings>

    <PropSetting>
      <name>Bonfire</name>
      <fps>10</fps>
      <sheet_cells>
        <X>3</X>
        <Y>1</Y>
      </sheet_cells>
    </PropSetting>

  </settings>
</PropSettings>
```

To add a prop on a screen:
1. Add the prop on the list in your `prop_settings.xml` file.
2. Create a configuration file called `prop(SCREEN NUMBER).xml`.
3. Inside the file, add each prop with their type (name of the prop), position on X and Y axis (__0,0 is top-left!__) and optional if the prop should be flipped.
4. Done!

```xml
<?xml version="1.0"?>
<PropCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Props>
    <PropData>
      <type>Bonfire</type>
      <Position>
        <X>397</X>
        <Y>179</Y>
      </Position>
    </PropData>

    <PropData>
      <type>Bonfire</type>
      <Position>
        <X>200</X>
        <Y>150</Y>
      </Position>
    </PropData>
  </Props>
</PropCollection>
```

<br>

## Hidden walls
are used in-game to hide areas or make the screen more realistic, the hidden wall works as foreground until the player gets into its position where it becomes transparent.

The hidden walls textures are located in `props/hidden_walls/textures`, they are managed by a configuration file called `hidden_wall(SCREEN NUMBER).xml`.

```xml
<?xml version="1.0"?>
<RaymanCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <walls>

    <RaymanData> 
    	<achievements>              <!-- leave this as is -->
        <AchievementCode>GO_THOUGH_ILLUSORY_WALL</AchievementCode>  <!-- leave this as is -->
      </achievements>             <!-- leave this as is -->

      <texture_name>1_hidden_wall</texture_name>  <!-- name of the texture inside props/hidden_wall/texture -->
      <Position>                  <!-- contains the details on the X and Y coordinates -->
        <X>0</X>                  <!-- X coordinate on the screen -->
        <Y>169</Y>                <!-- Y coordinate on the screen -->
      </Position>
    </RaymanData>

  </walls>
</RaymanCollection>
```

### Hidden wall prop
Hidden walls can have props too; these can be added creating a different prop configuration file inside `props/hidden walls props` called `prop(SCREEN NUMBER).xml`.

```xml
<?xml version="1.0"?>
<PropCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <screen>133</screen> <!-- screen number -->

  <Props>
    <PropData>
      <type>ghost_platform</type>   <!-- texture inside props/textures -->
      <Position>                    <!-- contains the details on the X and Y coordinates -->
        <X>358</X>                  <!-- X coordinate on the screen -->
        <Y>206</Y>                  <!-- Y coordinate on the screen -->
      </Position>
      <flipped>false</flipped>      <!-- flip texture -->
    </PropData>
  </Props>
</PropCollection>
```

## Message
are text bubbles that get read by triggering a hitbox. The messages can be found inside `props/messages`.

An example of a message can be seen below:

<script src="https://gist.github.com/Phoenixx19/bd8fc739efbaf78159b5fd3b827df1df.js"></script>