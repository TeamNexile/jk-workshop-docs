---
layout: default
title: Getting started
has_children: true
nav_order: 2
last_modified_date: 2022-01-03 13:55
---

# Getting started
{: .no_toc }

Let's get started on how to build a custom level, reskin or collection for Jump King.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Getting started for custom levels

### Installation procedure

0. Make sure you have the [**latest version of JumpKingPlus**](https://github.com/JumpKingPlus/JumpKingPlus/releases/latest) installed.
1. Download the [**sample level**]({{ site.baseurl }}/workshop/1/) from the workshop.
2. Drag the `mods` folder from the zip file to `Jump King/Content` folder. If you already have a `mods` folder existing, proceed to rename or delete the folder.
3. You now have a custom map ready to work on!

After installing and downloading all the files and tools needed; you can start working on your first custom level.

> In order to make the custom level working you will need to create two files inside your `JumpKing/Contents/mods` folder. JumpKingPlus loads the custom mode when both the `level.xnb` and the `mod.xml` files are in the folder above.

<u>Using the sample level, you don't have to worry about creating this</u>, but you will need to worry to understand the format and the meaning of those two files.

### Testing

Testing is the most important phase of your level that should take you a lot of time, a good level has every single fall calculated, nothing is left to be random. Check out some more on [**tips page**]({{ site.baseurl }}/workshop/publish/).

To test your sample level **for the first time** you just need to:
1. Boot up Jump King.
2. Click on the greeen "Sample Level" text.
3. Your sample level will now boot!

Next up, for testing the following times, you'll just boot up the game and click *Continue*.

<br>

## Getting started for reskins/collections
First of all, open the software of your choice and set two layers. The first (or top) layer should be the layer you use for drawing your reskin, the second (or bottom) layer should be the [**base file**](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/base.png); this second layer will help you building a fully working reskin.

A simple trick while making a custom reskin is setting the second (or bottom) layer to a lower opacity, like 50%.

Once done: 
> If you are doing a reskin: 
> 1. Disable the second (bottom) layer. 
> 2. Save to `(YOUR RESKIN NAME).png`.

> If you are doing a collection: 
> 1. Disable the second layer to all your images.
> 2. Save them with the current format: `(YOUR COLLECTION NAME)_(YOUR RESKIN NAME or ITEM NAME).png`.<br>
> This format is not mandatory but it's necessary to simplify the end user to understand what's inside a collection and what not.

### Config file for reskins
The config file (named as `(YOUR RESKIN NAME).xml`) is needed to define what skin is getting a reskin, and what reskin is enabled, plus other details.

**Each reskin needs one config file.**

|tag|description|
|---|---|
|`<isCollection>`|This is field is **required**, set to `false` for **reskins**.|
|`<skin>`|Can be: Crown, Shoes, CrownNBP, GiantBoots, Cap, GnomeHat, Tunic, YellowShoes, CrownOwl, CapeOwl, NULL (for jump king bases).|
|`<name>`|Any text (has to be the **same name for the .xnb and .xml**).|
|`<description>`|Any text or null (optional).|
|`<enabled>`|Can be: true or false (use true as default).|

Here's a sample xml file that you can use:

```xml
<?xml version="1.0"?>
<WardrobeSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">

	<!-- 
		JUMPKINGPLUS V1.6.0 by Phoenixx19
		 https://phoenixx19.github.io/JumpKingPlus/workshop
		 Wardrobe feature - Custom skins support.
	-->
  <isCollection>false</isCollection>
	<skin>NULL</skin>
	<name>forsenCD</name>
	<description>:tf: u mad?</description>
	<enabled>true</enabled>
</WardrobeSettings>
```

Save it as `(YOUR RESKIN NAME).xml`.

### Config file for collections
The config file is needed for collections to define the details of the collection and the list of reskins used in the collection.<br>
**One collections needs one single config file. Reskins part of collection SHOULD NOT have a config file.**

|tag|description|
|---|---|
|`<isCollection>`|This is mandatory, set to `true` for **collections**.|
|`<skin>`|Doesn't get read, but use `NULL` for coherence.|
|`<name>`|Any text (has to be the same name for the .xnb and .xml).|
|`<description>`|Any text or null (optional).|
|`<enabled>`|Can be: true or false (use true as default).|
|`<collection>`|All the details for the collection.|
|`<name>`|**Inside the collection tag:** Any text (has to be the same name for the .xml).|
|`<description>`|**Inside the collection tag:** Any text or null (optional).|
|`<enabled>`|**Inside the collection tag:** Can be: true or false (use true as default).|
|`<Reskins>`|Array of Reskin|
|`<Reskin>`|Contains the skin and name of a singular reskin inside the collection.|
|`<skin>`|Can be: Crown, Shoes, CrownNBP, GiantBoots, Cap, GnomeHat, Tunic, YellowShoes, CrownOwl, CapeOwl, NULL (for jump king bases).|
|`<name>`|Any text (has to be the same name for the .xnb).|

```xml
<WardrobeSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">

  <!-- 
		JUMPKINGPLUS V1.6.0 by Phoenixx19
		 https://phoenixx19.github.io/JumpKingPlus/workshop
		 Wardrobe feature - Custom skins support.
	-->
  <isCollection>true</isCollection>
  <skin>NULL</skin>
  <name></name>
  <description></description>
  <enabled>false</enabled>
  <collection>
    <name>red</name>
    <description>:tf: u mad?</description>
    <enabled>true</enabled>
    <Reskins>
      <Reskin>
        <skin>Tunic</skin>
        <name>red</name>
      </Reskin>
      <Reskin>
        <skin>NULL</skin>
        <name>forsenCD</name>
      </Reskin>
      <Reskin>
        <skin>CrownOwl</skin>
        <name>Celeste Cap</name>
      </Reskin>
    </Reskins>
  </collection>
</WardrobeSettings>
```
Make sure that you have the same filename as the collection name.

### Testing

To test a reskin or a collection in-game, you need to:

1. Convert the images to XNB like explained in the **following category**.
2. Make sure that all the .xnb and .xml files are inside `Jump King/Content/wardrobe`.
3. Start up Jump King.
4. Click "*Inventory*", then "*Reskins*" or "*Collections*" (based on what you are creating).
5. Click on the skin name you are creating.
6. Select "*Equip*".
7. Done!

**WARNING**:<br>The following reskins and collections won't work in custom levels:
- Base reskin
- Collection that contains a base skin