---
layout: default
title: Getting started
has_children: true
has_toc: false
nav_order: 2
last_modified_date: 2024-09-02 15:21
---

# Introduction to the Workshop
{: .no_toc }

what you need to know to get started.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

<style>
    div.group {
        display: flex;
        gap: 1.5rem;
        position: relative;
    }

    div.group > * {
        flex: 1 1 0px;
        width: 0;
    }
</style>

---

## What is the Workshop?

The Steam Workshop is designed as a place for all Jump King fans and community members to participate in the **creation and use** of content such as **levels, skins and so on** for Jump King!

![Workshop Image]({{ site.baseurl }}/images/WorkshopImage.png)

## What is a level?

A level is additional content that can be played just like New Babe Plus and Ghost of the Babe.

![Level example]({{ site.baseurl }}/images/getting-started/level.png)

> The example above shows a portion of a screen from the level [*Babe of the Heavens* by Meea](https://steamcommunity.com/sharedfiles/filedetails/?id=3143173374).

### The level hierarchy

A level is made up by a folder with a bunch of folders and files inside of them.

> The structure is too complex to show, since it's over 50 files and folders combined.<br>Everything will be explained later so there's no need to see the structure as of now.

<!-- > If you **really want** to see the structure, navigate inside all the [**Sample custom level**]({{ site.baseurl }}/files/%5BLEVEL%5D%20Sample%20Level.zip) folders. -->

<!-- ```
📂 Sample Level
 ┣ 📂 audio
 ┃ ┣ 📂 background
 ┃ ┃ ┣ 📂 data
 ┃ ┃ ┃ ┗ 📜 values.xml
 ┃ ┃ ┗ 📦 towers 1.xnb
 ┃ ┗ 📂 music
 ┃ ┃ ┣ 📂 event_music
 ┃ ┃ ┃ ┣ 📦 ending_jingle.xnb
 ┃ ┃ ┃ ┗ 📜 events.xml
 ┃ ┃ ┣ 📂 menu loop
 ┃ ┃ ┗ 📦 ending.xnb
 ┣ 📂 ending
 ┃ ┣ 📦 imagecrown.xnb
 ┃ ┗ 📦 imageshoes.xnb
 ┣ 📂 gui
 ┃ ┣ 📜 earthquake_settings.xml
 ┃ ┗ 📜 location_settings.xml
 ┣ 📂 king
 ┃ ┣ 📦 base.xnb
 ┃ ┗ 📜 skin_settings.xml
 ┣ 📂 particles
 ┃ ┣ 📜 snow_settings.xml
 ┃ ┗ 📜 weather.xml
 ┣ 📂 props
 ┃ ┣ 📂 hidden wall props
 ┃ ┣ 📂 hidden_walls
 ┃ ┃ ┣ 📂 textures
 ┃ ┃ ┃ ┗ 📦 1_hidden_wall.xnb
 ┃ ┃ ┗ 📜 hidden_wall1.xml
 ┃ ┣ 📂 messages
 ┃ ┃ ┗ 📜 1_diary.xml
 ┃ ┣ 📂 new babe plus props
 ┃ ┣ 📂 owl props
 ┃ ┣ 📂 textures
 ┃ ┃ ┣ 📂 old_man
 ┃ ┃ ┃ ┣ 📂 lines
 ┃ ┃ ┃ ┃ ┣ 📜 archaeologist_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 fairy2_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 fairy3_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 fairy_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 gnome_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 hermit_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 imp_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 old_man_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_bogman_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat1_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat2_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat3_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat4_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat5_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat6_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat7_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat8_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_cat_outsider_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 owl_gargoyles_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 skeleton_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 stoneman1_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 stoneman2_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 stoneman3_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 stoneman4_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 stoneman5_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜 stoneman6_quotes.xml
 ┃ ┃ ┃ ┃ ┗ 📜 trollking_quotes.xml
 ┃ ┃ ┃ ┣ 📂 merchant
 ┃ ┃ ┃ ┃ ┣ 📜merchant_nbp.xml
 ┃ ┃ ┃ ┃ ┣ 📜merchant_quotes.xml
 ┃ ┃ ┃ ┃ ┣ 📜owl_mold_man.xml
 ┃ ┃ ┃ ┃ ┣ 📜owl_shroom_guy.xml
 ┃ ┃ ┃ ┃ ┗ 📜snake.xml
 ┃ ┃ ┃ ┣ 📂 owl_chars
 ┃ ┃ ┃ ┃ ┗ 📦 owl_shroom_guy.xnb
 ┃ ┃ ┃ ┣ 📦 hermit.xnb
 ┃ ┃ ┃ ┣ 📜 owl_cat2_quotes.xml
 ┃ ┃ ┃ ┣ 📜 owl_cat3_quotes.xml
 ┃ ┃ ┃ ┣ 📜 owl_cat4_quotes.xml
 ┃ ┃ ┃ ┣ 📜 owl_cat5_quotes.xml
 ┃ ┃ ┃ ┣ 📜 owl_cat6_quotes.xml
 ┃ ┃ ┃ ┣ 📜 owl_cat7_quotes.xml
 ┃ ┃ ┃ ┣ 📜 owl_cat8_quotes.xml
 ┃ ┃ ┣ 📂 raven
 ┃ ┃ ┃ ┣ 📜 fly.ravset
 ┃ ┃ ┃ ┣ 📦 fly.xnb
 ┃ ┃ ┃ ┣ 📦 gold_ring.xnb
 ┃ ┃ ┃ ┣ 📜 raven.ravset
 ┃ ┃ ┃ ┣ 📦 raven.xnb
 ┃ ┃ ┃ ┣ 📦 raven_crown.xnb
 ┃ ┃ ┃ ┣ 📦 ruby.xnb
 ┃ ┃ ┃ ┣ 📜 tsuchinoko.ravset
 ┃ ┃ ┃ ┣ 📦 tsuchinoko.xnb
 ┃ ┃ ┃ ┣ 📜 white_raven.ravset
 ┃ ┃ ┃ ┗ 📦 white_raven.xnb
 ┃ ┃ ┣ 📦 Bonfire.xnb
 ┃ ┃ ┣ 📦 fairy.xnb
 ┃ ┃ ┣ 📦 grammofon.xnb
 ┃ ┃ ┗ 📜 prop_settings.xml
 ┃ ┣ 📂 worlditems
 ┃ ┃ ┣ 📦 silver_coin.xnb
 ┃ ┃ ┗ 📜 worlditems.xml
 ┃ ┗ 📜 prop1.xml
 ┣ 📂 screens
 ┃ ┣ 📂 background
 ┃ ┃ ┗ 📦 bg1.xnb
 ┃ ┣ 📂 foreground
 ┃ ┃ ┗ 📦 fg2.xnb
 ┃ ┣ 📂 masks
 ┃ ┃ ┗ 📦 light_snow_bgmask1.xnb
 ┃ ┣ 📂 midground
 ┃ ┃ ┗ 📦 1.xnb
 ┃ ┗ 📂 scrolling
 ┃ ┃ ┣ 📂 textures
 ┃ ┃ ┃ ┗ 📦 1_clouds.xnb
 ┃ ┃ ┗ 📜 scroll1.xml
 ┣ 📜 level_settings.xml
 ┣ 📦 level.xnb
 ┗ 🖼 banner.png
``` -->

## What is a skin?

A skin is a cosmetic that replaces one or multiple existing item's texture. 

<div class="group">
    <img src="{{ site.baseurl }}/images/getting-started/skin.png" alt="Skin example" title="Single skin example">
    <img src="{{ site.baseurl }}/images/getting-started/set.png" alt="Set example" title="Skin set example">
</div>

> The examples above show a single skin and a skin set, respectively Dunce Hat by IntroCar and Old Man by Volcanic.

### Difference between single skin and skin set

If you are looking to skin **one** single **item**, you should do a [**single skin**](#single-skin-hierarchy).<br>
Otherwise if you are looking to skin **multiple items**, what you need is a [**skin set**](#skin-set-hierarchy).

### Single skin hierarchy

A single skin is made up by a folder with group of files:

- a configuration file **always called** `cosmetic_settings.xml` that tells the game, which item skins, its enable state and the filename;
- a PNG[^xnb] file that contains the skin, the name should the same as stated as the filename in the configuration file above

Following the example, this could be a possible outcome for a single skin:

```
📂 Brown Tunic
 ┣ 📜 cosmetic_settings.xml
 ┗ 🖼 Brown Tunic.png
```

### Skin set hierarchy

A skin set is made up by a folder with group of files:

- a configuration file **always called** `set_settings.xml` that tells the game, which items are skinned, its enable state and the filenames of all skins;
- all the PNG[^xnb] files that contains the set, the names should the same as stated as the filename in the configuration file above; *(for ease of use you should use a text format on each file name to easily identify which packed file is a skin, just like the following example)*{: .text-grey-dk-000 }

Following the example, this could be a possible outcome for a skin set:

```
📂 Jing
 ┣ 📜 set_settings.xml
 ┣ 🖼 Jing_Crown.png
 ┣ 🖼 Jing_Shoes.png
 ┗ 🖼 Jing_Cape.png
```

{: .note-title }
> Tip
>
> You could think of this as multiple single skins with one unified configuration file.

## What is a tileset?

Making a level can be quite long and tedious, tilesets can help you and everyone else in the community to speed the detailing process further, therefore a tileset is a collection of tiles that can be used to design and create a level faster.

### Tileset hierarchy

A tileset is made up by a folder with 2 files:

1. a configuration file **always called** `tileset_settings.xml` that tells Worldsmith (not the game), where each tile is located and which tags it contains;
2. a PNG file **always called** `tileset.png` that contains the tileset

Following the example, this should be the outcome for a tileset:


```
📂 Bricks and Plants Pack
 ┣ 📜 tileset_settings.xml
 ┗ 🖼 tileset.png
```

[^xnb]:
    This file will need to be packed into the XNB format in order for the game to be able to read it, this will be mentioned later.

## What is a mod?

A mod is a C# (programming language) code library that can change core mechanics of the game.

{: .highlight }
> In order to make a mod you need to have at least a good knowledge of programming.

A few examples of mods:

<div class="group">
    <a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3197746608">
        <img src="https://steamuserimages-a.akamaihd.net/ugc/2461853153296780135/C248C5A0D00BFEA06D4A38A3C639D938121B279B/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false"
        alt="Chat Ravens by PhantomBadger">
        <b>Chat Ravens</b> by PhantomBadger
    </a>
    <a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3217622959">
        <img src="https://steamuserimages-a.akamaihd.net/ugc/2505765138563901327/3F1198649860CB5C75B54C135C7F7DFB858805A0/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false" 
        alt="King vs Fly by Zebra">
        <b>King vs Fly</b> by Zebra
    </a>
    <a href="https://steamcommunity.com/sharedfiles/filedetails/?id=3180199536">
        <img src="https://steamuserimages-a.akamaihd.net/ugc/2440459605704352221/44EF8D822BBD41439C7DE8D745B6ED76CBF90D45/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false"
        alt="HitboxChanger by Phoenixx19">
        <b>HitboxResizer</b> by Phoenixx19
    </a>
</div>

### Mod hierarchy

The root folder of your mod should look like this:

```
📂 Random Jump Charge
 ┣ 📂 Properties
 ┃ ┗ 📜 AssemblyInfo.cs
 ┣ 📜 ModEntry.cs
 ┗ 📜 RandomJumpCharge.csproj
```

When building/testing your mod, new folders will appear:

```
📂 Random Jump Charge
 ┣ 📂 bin
 ┃ ┣ 📂 Debug
 ┃ ┗ 📂 Release
 ┗ 📂 obj
```

The `bin/Debug` folder is the default folder for when you build in "Debug", this folder might include more files since it includes additional debug files that can help your editor/IDE to find bugs easily. The `bin/Release` folder is the default folder for when you build in "Release", this folder defines when a mod is ready to be uploaded. The `obj` contents is necessary to build the mod.

#### Compiled

When compiled (whatever the configuration is between Debug or Release), the mod folder should look like a list of DLL (compiled library) files which should be your code and your additional dependencies if you have any.

## Next up

[Get all your requirements]({{ site.baseurl }}/getting-started/requirements) before starting and [read the guidelines]({{ site.baseurl }}/getting-started/guidelines).

---

### Footnotes
{: .no_toc }