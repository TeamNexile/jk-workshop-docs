---
layout: default
title: Getting started
has_children: true
has_toc: false
nav_order: 2
last_modified_date: 2023-02-22 18:07
---

# Introduction to the Workshop
{: .no_toc }

details you need to know before you starting on your first steps.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

<style>
    div.img-group {
        display: flex;
        gap: 1.5rem;
        position: relative;
    }

    div.img-group img {
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

> The example above shows a portion of a screen from the level "*Babe of the Heavens*" by Meea.

### The level hierarchy

A level is made up by a folder with a bunch of files and folders inside of it.

> The structure is too complex to show, since it's over 50 files in their own folders.<br>Believe me here, you don't want to see it. Everything will be explained later anyway.

> If you **really want** to see the structure, navigate inside all the [**Sample custom level**]() folders.

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

A downloaded level shows up in Jump King like the following from the Workshop menu.

![Level menu example]({{ site.baseurl }}/images/getting-started/level_set.png)


## What is a skin?

A skin is a cosmetic that replaces one or multiple existing item's texture. 

<div class="img-group">
    <img src="{{ site.baseurl }}/images/getting-started/skin.png" alt="Skin example" title="Single skin example">
    <img src="{{ site.baseurl }}/images/getting-started/set.png" alt="Set example" title="Skin set example">
</div>

### Single skin or set?

If you are looking to skin **one** single **item**, you should do a [**single skin**](#single-skin-hierarchy).<br>
Otherwise if you are looking to skin **multiple items**, what you need is a [**skin set**](#skin-set-hierarchy).

### Single skin hierarchy

A single skin is made up by a folder with group of files:

- a configuration file **always called** `cosmetic_settings.xml` that tells the game, which item skins, its enable state and the filename;
- the packed/converted XNB file that contains the skin, the name should the same as stated as the filename in the configuration file above;
- the steam thumbnail; *(optional, for ease of use)*{: .text-grey-dk-000 }

Following the example, this could be a possible outcome for a single skin:

```
📂 Brown Tunic
 ┣ 📜 cosmetic_settings.xml
 ┣ 📦 Brown Tunic.xnb
 ┗ 🖼 banner.png
```

### Skin set hierarchy

A skin set is made up by a folder with group of files:

- a configuration file **always called** `set_settings.xml` that tells the game, which items are skinned, its enable state and the filenames of all skins;
- all the packed/converted XNB files that contains the set, the names should the same as stated as the filename in the configuration file above; *(for ease of use you should use a format to easily find which packed file is a skin, just like the following example)*{: .text-grey-dk-000 }
- the steam thumbnail; *(optional, for ease of use)*{: .text-grey-dk-000 }

Following the example, this could be a possible outcome for a skin set:

```
📂 Jing
 ┣ 📜 set_settings.xml
 ┣ 📦 Jing_Crown.xnb
 ┣ 📦 Jing_Shoes.xnb
 ┣ 📦 Jing_Cape.xnb
 ┗ 🖼 banner.png
```

> You could think of this as multiple single skins with one unified configuration file.

<!-- ## Custom levels

### Disclaimer
When it comes to Custom levels, folders that this document refer to are meant to be inside `Jump King/Content/mods`. 

<br>

## Reskins/collections
### Disclaimer
If you are working on a Jump King Base reskin, enabling and disabling it will work only in the title screen (currently) and they won't be working on custom levels since it would overlay the already existing base for the custom level.

### Reskin or collection?
Before getting started you need to know the difference between a reskin and a collection.

- A **reskin** is a *single custom skin* that can be toggled singularly in the `Reskins` menu.
- A **collection** is a *group of skins* that can be toggled together in the `Collections` menu. -->

## Next up

[Get all your requirements]({{ site.baseurl }}/getting-started/requirements) before starting fresh and don't forget to [read the guidelines]({{ site.baseurl }}/getting-started/guidelines).