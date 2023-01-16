---
layout: default
title: Audio
parent: Level Making
nav_order: 9
last_modified_date: 2022-12-19 14:05
---

# Audio folder
{: .no_toc }

contains all the sound related content.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Music warning
> If a copyright holder of a song/asset asks us to remove the copyrighted material due to not having a proper license for usage, download links to the level will be removed until the situation is resolved. Either by replacing the copyrighted material, or by acquiring the proper license/permission for its usage.

> Make sure you compress your music/audio enough so the **level** once compressed **doesn't have file size that's too large**! It's recommended that you try to keep the final **mods** folder below **1GB**. ([BoA]({{ site.baseurl }}/workshop/3/) and [IB]({{ site.baseurl }}/workshop/4/) are both **800MB**)

<br>

## Values configuration file
contains all the music, ambient inside each screen of the custom level.

### AmbienceInfo
<p class="do-i-need-it">optional</p>

Found inside `<special_info>`, contains all the information about a single sound file, such as:

|tag|description|
|---|---|
|`<name>`|Name of the music file|
|`<type>`|Should be always `Music`|
|`<restart>`|Boolean value. If true, the song will be looped|
|`<fade_out_length>`|Fade out length in seconds|
|`<fade_in_length>`|Fade in length in seconds|

### AmbienceSave
<p class="do-i-need-it">optional</p>

Found inside `<sections>`, contains generic information about the music in a section (number of screens).
**AmbienceSave** contains multiple instances of the `<Ambience>` tag.

#### Ambience
<p class="do-i-need-it">required</p>

Found inside `<AmbienceSave>`, contains name and volume of a sound.

|tag|description|
|---|---|
|`<name>`|Name of the file|
|`<volume>`|Volume from 0 to 1 (0-100%)|

### Screens counting warning
> The `<screens>` tag <u>doesnt work with the name logic of the screen number</u>. This is precisely made to avoid mixmatches.
**From the first `<AmbienceSave>` it keeps the `<screens>` number counting.**

So if you have two AmbienceSaves where the first one has 5 screens and the second has 2, you would have done already 7 screens of music.

### Ambient
The ambient music should be placed inside `audio/background` as an .xnb file.<br>To add this to a specific zone, simply edit the `audio/background/data/values.xml` and add on the AmbienceSave section like so:
```xml 
<sections>
  <AmbienceSave>
    <ambience>
      <Ambience>
        <name>Water</name>
        <volume>0.7</volume>
      </Ambience>
      <!-- more Ambience -->
    </ambience>
  </AmbienceSave>
  <!-- more AmbienceSaves -->

  <screens>5</screens>
</sections>
```

### Music
The music should be placed inside `audio/background` as an .xnb file.<br>To add this to a specific zone, simply edit the `audio/background/data/values.xml` and add on the AmbienceSave section like so:

```xml
<sections>
  <AmbienceSave>
    <ambience>
      <Ambience>
        <name>TheBogTwo</name>
        <volume>0.85</volume>
      </Ambience>
      <!-- more Ambience -->
    </ambience>
  </AmbienceSave>
  <!-- more AmbienceSaves -->

  <screens>5</screens>
</sections>
```

In the `values.xml` file mentioned above, this needs to be configured as an `AmbienceInfo` as well.

```xml 
<special_info>
  <AmbienceInfo>
    <name>TheBogTwo</name>
    <type>Music</type>
    <restart>true</restart>
  </AmbienceInfo>
  <!-- more AmbienceInfo -->
</special_info>
```

In the end you might end up with something like this:

<script src="https://gist.github.com/Phoenixx19/c82682702d57c61d3c276e87156486a9.js"></script>

<br>

## Music folder
contains many other files that can be changed such as:
- Babe ending songs
- Menu intro
- Event music 

### Babe ending songs
are songs that are played once the the player has beaten the game.

In order to add it:
1. Convert a sound file into XNB format.
2. Move the file inside `audio/music`.
3. Name it as following depending on your babe:
  - First babe: `ending.xnb`
  - Second babe: `ending2.xnb`
  - Third babe: `ending3.xnb`
4. Done!

### Menu intro
is a song that gets played once the game is on the title screen.

In order to add it:
1. Simply convert an audio file into XNB.
2. Move the file inside `audio/music`.
3. Name it `opening theme.xnb`.
4. Done!

### Event music
contains **music that can be triggered**, such as the sound on the last babe screen or the gargoyles.

Both the configuration file and the sound effect should be located in `audio/music/event_music`.
The configuration file is very straight forward in asking for the name of the song (in the folder) and the screen to trigger.