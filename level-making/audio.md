---
layout: default
title: Audio
parent: Level Making
nav_order: 9
last_modified_date: 2023-02-06 17:59
---

# Audio folder
{: .no_toc }

all the sound related content<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Copyrighted audios

> If a copyright holder of a song/asset asks us to remove the copyrighted material due to not having a proper license for usage, your item will be removed from the Workshop for copyright infringement. Only by replacing the copyrighted material or by acquiring the proper license/permission for its usage, the item can be reuploaded on the Workshop. If the user is found reuplading copyrighted content, it is *subject* to a Workshop ban.
{: .warning }

## File size

> Music and ambience sounds tend to be the most heavy files in Jump King. Make sure you compress your music/audio enough so the **level** once compressed **doesn't have file size that's too large**! It's recommended that you try to keep the final **mods** folder below **1GB**. The average map size is around **750-800 MB**.
{: .warning }

## Ambience or music?

All ambience can be all background sounds (bonfire, birds, rain or wind sounds) that can complete the immersion of the player. Meanwhile [music is already what you already know.](https://www.youtube.com/watch?v=90I3pWDfbxU){:target="_blank"}

To differentiate music from ambience, Jump King uses a special tag called `AmbienceInfo` that you will need to create. You can still add ambience pieces in the `AmbienceInfo` tag if you want to use the restart, fade-in or fade-out option but it will need to have its own `type` value to differentiate.

### Adding/replacing/removing music or ambience (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding music or ambience (without Worldsmith)

1. Convert your audio file into a packed XNB file [making sure it isn't too big](#file-size) (usually a song shouldn't go over 45-50 MB).
2. Place your packed file in `audio/background`.
3. Navigate into the `data` folder and open the `values.xml` file.
4. **If you are adding a generic ambience (doesn't need fade-in/out), you can [skip to the next steps](#adding-to-level)**.
5. Copy the following snippet:
   ```xml
   <AmbienceInfo>
    <name>YOUR_AUDIO_FILENAME</name>
    <type>Music</type>
   </AmbienceInfo>
   ```
6. In a new line after the opening tag of `special_info`, paste the snippet.
7. Replace `YOUR_AUDIO_FILENAME` with the filename of the audio file.
8. Being a song, you should leave the `type` as **Music**, otherwise use **Ambience**. [**API Reference**]({{site.baseurl}}/api/music){: target="_blank"}.
   
    > If you want the audio to stop and play from the start again once returned to the screens where it is added, add the following snippet below your `type` tag:
      ```xml
        <restart>true</restart>
      ```
    {: .highlight }
    > If you want to have fade in and/or fade out effect add the following snippet(s) below your `type` tag and replace `YOUR_FADE_OUT_SECONDS` and `YOUR_FADE_IN_SECONDS` with your customized values (4 seconds is usually recommended).
      ```xml
        <fade_out_length>YOUR_FADE_OUT_SECONDS</fade_out_length>
        <fade_in_length>YOUR_FADE_IN_SECONDS</fade_in_length>
      ```
    {: .highlight }

Good, you've set the properties for Jump King to understand that you added a Music piece, now let's add it on the first screen.
{: #adding-to-level }

1. Copy the following snippet:
   ```xml
    <AmbienceSave>
      <ambience>
        <Ambience>
          <name>YOUR_MUSIC_FILENAME</name>
          <volume>0.85</volume>
        </Ambience>
      </ambience>
      <screens>1</screens>
    </AmbienceSave>
   ```
2. Find the `sections` tag and paste the snippet right after it's opening tag on a new line.
3. Replace `YOUR_MUSIC_FILENAME` with the filename of your packed music file.
4. Change the value of the volume, if the music in-game it's too quiet or loud.
   > The minimum value for the volume is 0 and the maximum value is 1, but all the values in between works. The game is known to crash if the volume is higher than 1.
   {: .disclaimer }
5. Change the `screens` value to how many screens you want to have the music above.
   > The `<screens>` tag <u>doesnt work with the name logic of the screen number</u>. This is precisely made to avoid mixmatches.
    **From the first `<AmbienceSave>` it keeps the `<screens>` number counting.** So if you have two AmbienceSaves where the first one has screens with a value of 5 and the second has a value of 2, you would have done already 7 screens of music.
   {: .warning }

### Replacing a musical piece (without Worldsmith)

### Removing a musical piece (without Worldsmith)


## Event music
 
The event music is **music that can be triggered** and get **triggered once**, such as the sound on the last babe screen, the gargoyles in Ghost of the Babe, or the lightning sound in New Babe Plus.

### Adding/replacing/removing an event music (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding an event music (without Worldsmith)

To add an event music:

1. Convert your event music into a packed XNB file.
2. Place your file inside `audio/music/event_music`.
3. Open the `events.xml` file in the same folder.
4. Copy the following snippet:
   ```xml
    <Event>
      <screen>YOUR_SCREEN_NUMBER</screen>
      <song_name>YOUR_EVENT_MUSIC_NAME</song_name>
    </Event>
   ```
5. Paste the snippet a line after the starting tag of `events`.
6. Replace `YOUR_SCREEN_NUMBER` with the screen number where you want the event music to trigger.
7. Replace `YOUR_EVENT_MUSIC_NAME` with the name of your packed event music filename.

### Replacing an event music (without Worldsmith)

If you want to replace an existing event music's position, you will need to:

1. Open the `events.xml` file in the `audio/music/event_music` folder.
2. Change the current event music position to your new screen value.

If you want to replace an existing event music's song, you will need to:

1. Convert your event music into a packed XNB file.
2. Place your file inside `audio/music/event_music`. 
3. If it already exists, override it and you are done **otherwise**...
4. Open the `events.xml` file in the same folder.
5. Replace the old `song_name` value of your event with the new filename.

### Removing an ending music (without Worldsmith)

To remove an event music:

1. Write down the screen where your event music played.
2. Navigate to `audio/music/event_music` and open `events.xml`.
3. Delete the whole `Event` tag where `screen` equals to your screen.

## Ending music

The ending music is the audio played once the the player has beaten the game (reached the Babe). Depending on it's name, you can change the different babes ending music.

|Babe|Namefile|
|---|---|
|First babe|`ending`|
|Second babe|`ending2`|
|Third babe|`ending3`|


### Adding/replacing/removing an ending music (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding/replacing an ending music (without Worldsmith)

In order to add it:

1. Convert a sound file into XNB format.
2. Move the file inside `audio/music`.
3. Name it [depending on your babe](#ending-music).
   > If the file already exists, override it.
   {: .highlight }

### Removing an ending music (without Worldsmith)

You can only remove the second and third babe ending music, for the first ending, you will need to manually paste the original ending music from the gamefiles (can be found in `Jump King/Content/audio/music/ending.xnb`).

## Next up

You can finally add all the music you wanted to add on full-blast, let's take a final [look at particles]({{site.baseurl}}/level-making/particles) before publishing.

---

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