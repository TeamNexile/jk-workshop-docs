---
layout: default
title: Props
parent: Level Making
nav_order: 5
has_children: true
last_modified_date: 2023-02-02 17:31
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