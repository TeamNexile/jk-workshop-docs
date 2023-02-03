---
layout: default
title: Props
parent: Level Making
nav_order: 5
has_children: true
last_modified_date: 2023-02-03 14:59
---

# Props folder
{: .no_toc }

contains all types of props used in-game<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is a prop?

A prop is essentially a small object that more or less dynamic. In Jump King, there are countless of props around that you don't even know, just to name a few:

- the bonfire at the start of your journey,
- the Old Man,
- the hidden cap in the sewer,
- the hiddle wall preventing you to see the cap,
- the bird with the gold coin,
- the gold coin,
- the merchant in Bargainburg,
- et cetera...

All of these are a prop, and in the following subcategories, you are going to learn how to create and personalize your props.

But first let's start with the basics,<br>**the bonfire**.

> Good practice with props
> 
>Avoid using props in the final screen to prevent slight visual bugs from the game after beating the level.
{: .note-title }

## Simple prop

The props in-game (such as the bonfire in the first screen) are stored in the `props/textures` folder. Inside this folder, there's a configuration file named `prop_settings.xml` which contains a list of `<PropSetting>` tags.

### Adding/replacing/removing a simple prop (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding a simple prop (without Worldsmith)

1. Convert

### Replacing a simple prop (without Worldsmith)

### Removing a simple prop (without Worldsmith)

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

## Next up

The bonfire has been lit! Let's continue with [**hidden walls**]({{site.baseurl}}/level-making/props/hidden-walls).