---
layout: default
title: Configuration
parent: Level Making
nav_order: 1
last_modified_date: 2022-12-19 14:05
---

# Mod configuration file
{: .no_toc }

is a file that JumpKingPlus reads to know the basic information about the custom level.
{: .fs-6 .fw-300 }

In this file, you will set up the following basic information of your level using the [blank `mod.xml`](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/mod.xml).<!-- more -->

<!-- <a class="button transparent small" href="https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/mod.xml">
        <ion-icon name="code"></ion-icon>
        Blank mod.xml
    </a> -->

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## About
<p class="do-i-need-it">required</p>

contains all the general details about the custom level, such as the following:

|name|description|type|required|
|`<title>`|Title of the custom level (will show up in the Stats Display and Discord RPC)|string|Yes|
|`<image_key>`|Image for Discord RPC of the custom level (this will be added on the level's workshop release)|string|No|
|`<LevelColor>`|[Read more about the level color here.](#levelcolor)|LevelColor|No|
|`<ending_screen>`|Screen where the first babe spawns (Main Babe)|int|Yes|
|`<ending_screen_nbp>`|Screen where the second babe spawns (New Babe Plus)|int|No|
|`<ending_screen_owl>`|Screen where the third babe spawns (Ghost of the Babe)|int|No|
|`<disableProgress>`|Disable level percentage|boolean|No|
|`<StartingPosition>`|[Read more about the starting position here.](#startposition)|StartPosition|No|

The title will show up only when the game started is Main Babe / Normal Game.

### LevelColor
<p class="do-i-need-it">optional</p>

Added from <span class="badge-pill">v1.7.1</span>, this setting can be found inside `<About>` and contains all the data for a custom title color for the custom level.

|name|description|type|required|
|`<red>`|Contains the value (0 to 255) for the Red channel|byte|Yes|
|`<green>`|Contains the value (0 to 255) for the Green channel|byte|Yes|
|`<blue>`|Contains the value (0 to 255) for the Blue channel|byte|Yes|
|`<alpha>`|Contains the value (0 to 255) for the Alpha channel|byte|Yes|

### StartPosition
<p class="do-i-need-it">optional</p>

Can be found inside `<About>`, this contains all the data for the custom start position.

|name|description|type|required|
|`<positionX>`|Starting X positon of the player|float|Yes|
|`<positionY>`|Starting Y positon of the player|float|Yes|
|`<velocityX>`|Starting X speed of the player|float|No|
|`<velocityY>`|Starting Y speed of the player|float|No|
|`<isOnGround>`|**True**, if the player is on ground|boolean|No|

The StartPosition tag is optional, while the tags inside of it aren't. Which means that if the StartPosition is present, the tags marked as mandatory need to be in there.

<br>

## Compatibility
<p class="do-i-need-it">optional (!)</p>

contains all the details to check if a level is compatible with the running Jump King Plus version.

As of now, this is optional, but it's strongly recommended to write this too since <strong>this might become mandatory in the future</strong>.

|name|description|type|required|
|`<minimum_version>`|Minimum version (example 1.2.0)|Version|No|
|`<maximum_version>`|Maximum version (example 1.6.1)|Version|No|

<br>

## Fonts
<p class="do-i-need-it">required</p>

contains all the custom fonts that could be used globally on Jump King for the custom level.

|name|description|type|required|
|`<MenuFont>`|Font for the menu|string|No|
|`<MenuFontSmall>`|Font for smaller texts in the menu|string|No|
|`<StyleFont>`|The font used for styling|string|No|
|`<OptimusUnderline>` and `<Tangerine>`|???|string|No|
|`<LocationFont>`|Font used for the location name popup|string|No|
|`<GargoyleFont>`|Font usually used for the Gargoyles in the game|string|No|

While the `<Fonts>` tag is required, every tag inside `<Fonts>` is optional so can be left as following:
```xml
<!-- Custom fonts, leave blank if default -->
	<Fonts>
		<MenuFont></MenuFont>
		<MenuFontSmall></MenuFontSmall>
		<StyleFont></StyleFont>
		<OptimusUnderline></OptimusUnderline>
		<Tangerine></Tangerine>
		<LocationFont></LocationFont>
		<GargoyleFont></GargoyleFont>
	</Fonts>
```

Custom fonts are optional as specified, if left blank, JumpKingPlus will automatically pick the default fonts.

<br>

## Ending
<p class="do-i-need-it">required</p>

contains the custom images after beating/ending the custom level.<br>The images need be located inside `mods/ending`.

|name|description|type|required|
|`<MainBabe>`|Image name for beating the first babe custom game|string|Yes|
|`<MainShoes>`|Image name for beating the first babe custom game with the Giant Boots|string|Yes|
|`<NBPBabe>`|Image name for beating the second babe custom game|string|Yes, if the second babe is used|
|`<NBPShoes>`|Image name for beating the second babe custom game with the Giant Boots|string|Yes, if the second babe is used|
|`<OwlBabe>`|Image name for beating the third babe custom game|string|Yes, if the third babe is used|
|`<OwlBird>`|Image name for beating the third babe custom game with triggering all the positions of the tsuchinoko bird (the bird with feet)|string|Yes, if the third babe is used|

Both MainBabe and MainShoes are supposed to be called as such, as the .xnb files located in `/mods/ending`. **Do not** include
the extensions in the name, the game is automatically set to find the .xnb files.

<br>

## EndingLines
<p class="do-i-need-it">required</p>

contains the ending lines/credits for finishing the custom level.
Ending lines is an array of `<Credit>`, an array means that there could possibly be multiple `<Credit>` tags.

### Credit
<p class="do-i-need-it">optional</p>

Can be found inside `<EndingLines>`, this contains a header as the title, an array of strings called `<People>`.

#### People 
<p class="do-i-need-it">optional</p>

Can be found inside `<Credit>`, this contains a list of `<string>` for every person credited (or text per line). Try not to add more than 5 strings per credit since it might look bad or even not work.

If you have done this correctly, it might end up like this:
```xml
<!-- Ending lines for finishing the mod -->
	<EndingLines>
		<Credit>
			<header>Babe of Ascension</header>
			<People>
				<string>Created by</string>
				<string>IntroCar</string>
				<string>Lord of Cheeses</string>
                <string>Kebb</string>
                <string>Zebresh</string>
			</People>
		</Credit>
		<Credit>
			<header>Creators of JK+ and JK+ Assistance from</header>
			<People>
				<string>Phoenixx19</string>
				<string>MERNY</string>
			</People>
		</Credit>
	</EndingLines>
```
>Inside the Ending Lines, it's possible to use the default library for translations included in the game. LanguageJK
includes all the possible text in Jump King based by your localization language. Check out all the possible combinations
[**here**](./files/LanguageJK.xml).

---

And finally, once you're done you'll end up with something like this:

<script src="https://gist.github.com/Phoenixx19/63f78ddf4834140eb30dbdde8031e6ed.js"></script>
