---
layout: default
title: Audio
parent: Level Making
nav_order: 9
last_modified_date: 2024-09-20 16:34
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

## Copyrighted music pieces

> If a copyright holder of a song/asset asks us to remove the copyrighted material due to not having a proper license for usage, your item will be removed from the Workshop for copyright infringement. Only by replacing the copyrighted material or by acquiring the proper license/permission for its usage, the item can be reuploaded on the Workshop. If the user is found reuplading copyrighted content, it is *subject* to a Workshop ban.
{: .warning }

## File size

> Music and ambience sounds tend to be the most heavy files in Jump King. Make sure you compress your music/audio enough so the **level** once compressed **doesn't have file size that's too large**! It's recommended that you try to keep the final **mods** folder below **1GB**. The average map size is around **750-800 MB**.
{: .warning }

## Audio pieces (Ambience/Music)
### Difference between ambience and music

All ambience can be all **background sounds** (bonfire, birds, rain or wind sounds).<br>Music is a **soundtrack** on a different layer.

### Adding an audio piece (with Worldsmith)

1. Navigate to the **Content Manager** page.

   ![Content Manager]({{ site.baseurl }}/images/level-making/worldsmith_content_manager.png)

2. Scroll until you find an header "**Audio files**".
3. Click on the **Import audio files** button found on the right side. A prompt will show up asking the necessary information for your audio file. The following image is how it should look like.

   ![Import audio files]({{ site.baseurl }}/images/level-making/audio/audio_add.png)

5. Select the appropriate type for your audio file and write a name of your audio file that you can identify later.
6. Click on **Select audio**.
7. A new prompt will show up asking to you select an audio file.

    ![Add audio]({{ site.baseurl }}/images/level-making/audio/audio_add_preview.png)
   
8. After selecting your file, click **Open**.
9. After clicking **Add audio**, you should see your audio piece below "Audio files".

   ![Audio successfully added]({{ site.baseurl }}/images/level-making/audio/audio_success.png)

### Replacing or removing an audio piece

Replacing and removing an audio piece have not been yet implemented inside Worldsmith. If you'd like to replace or remove them, consider looking out the [**Steps (without Worldsmith)**](./#steps-without-worldsmith).
{: .disclaimer }

### Adding an audio piece on a screen

1. Navigate to the **Screens** page.
2. Right-click onto the canvas on the left side of your screen (where you have your level preview) and select *Add on screen...*, then *Sound*.

    ![Sound right click]({{ site.baseurl }}/images/level-making/audio/sound_right_click.png)

3. Once clicked, a prompt will ask you to select an audio piece. After choosing an audio piece, you can decide to higher or lower the volume of the piece.

    ![Sound details]({{ site.baseurl }}/images/level-making/audio/sound_prompt.png)

4. Once done tinkering with the audio settings, click **Add**.<br>Your audio piece should appear on the right sidebar like so.

    ![Sound added successfully]({{ site.baseurl }}/images/level-making/audio/sound_success.png)

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

To differentiate music from ambience, Jump King uses a special tag called `AmbienceInfo` that you will need to create. You can still add ambience pieces in the `AmbienceInfo` tag if you want to use the restart, fade-in or fade-out option but it will need to have its own `type` value to differentiate.

### Adding music or ambience
{: .no_toc }

1. Convert your audio file into a packed XNB file [making sure it isn't too big](#file-size) (usually a song shouldn't go over 45-50 MB).
2. Place your packed file in `audio/background`.
   
   ![File]({{site.baseurl}}/images/level-making/audio/audio_file.png)
3. Navigate into the `data` folder and open the `values.xml` file.
   
   ![Folder]({{site.baseurl}}/images/level-making/audio/audio_folder.png)
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
   
   ![Basic]({{site.baseurl}}/images/level-making/audio/audio_ambienceinfo_basic.png)
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

   ![Completed]({{site.baseurl}}/images/level-making/audio/audio_ambienceinfo_completed.png)

After having added references to your sound files in the Jump King properties you can now add it to the first screen (or any screen).
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
5. Change the `screens` value to how many screens you want to have the audio settings above.
   > The `<screens>` tag <u>doesnt work with the name logic of the screen number</u>. This is precisely made to avoid mixmatches.
    **From the first `<AmbienceSave>` it keeps the `<screens>` number counting.** So if you have two AmbienceSaves where the first one has screens with a value of 5 and the second has a value of 2, you would have done already 7 screens of music.
   {: .warning }
   
   ![Logic]({{site.baseurl}}/images/level-making/audio/audio_ambiencesave_logic.png)
6. You can add as many `Ambience` tags as you wish in a `AmbienceSave`, below a line of `ambience` tag of your wanted `AmbienceSave` add the following snippet:
   ```xml
    <Ambience>
      <name>YOUR_MUSIC_FILENAME</name>
      <volume>0.85</volume>
    </Ambience>
   ```
   
   ![Multiple]({{site.baseurl}}/images/level-making/audio/audio_ambiencesave_multiple.png)

### Replacing music or ambience
{: .no_toc }

To replace your musical piece's audio (if it has the same name), you need to replace the packed audio file found in `audio/background`.

If your file has a different name, you will need to:
1. Move your new audio packed XNB file in `audio/background`.
2. Delete the old audio file.
3. Navigate to `data` and open `values.xml`.
4. Replace all the references to the old filename with your new filename.

### Removing music or ambience
{: .no_toc }

1. Navigate to `audio/background/data` and open `values.xml`.
2. Remove the `AmbienceInfo` and all `Ambience`s that contains the name that equals to the audio you want to remove.
3. And finally, remove the file in `audio/background`.

</div>
</details>

## Event music
 
The event music is **music that can be triggered** and get **triggered once**, such as the sound on the last babe screen, the gargoyles in Ghost of the Babe, or the lightning sound in New Babe Plus.

### Adding/replacing/removing an event music

Adding, replacing and removing an event music have not been yet implemented inside Worldsmith. If you'd like to add, replace or remove them, consider looking out the [**Steps (without Worldsmith)**](./#steps-without-worldsmith-1).
{: .disclaimer }

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

### Adding an event music
{: .no_toc }

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

### Replacing an event music
{: .no_toc }

If you want to replace an existing event music's position, you will need to:

1. Open the `events.xml` file in the `audio/music/event_music` folder.
2. Change the current event music position to your new screen value.

If you want to replace an existing event music's song, you will need to:

1. Convert your event music into a packed XNB file.
2. Place your file inside `audio/music/event_music`. 
3. If it already exists, override it and you are done **otherwise**...
4. Open the `events.xml` file in the same folder.
5. Replace the old `song_name` value of your event with the new filename.

### Removing an ending music
{: .no_toc }

To remove an event music:

1. Write down the screen where your event music played.
2. Navigate to `audio/music/event_music` and open `events.xml`.
3. Delete the whole `Event` tag where `screen` equals to your screen.

</div>
</details>

## Ending music

The ending music is the audio played once the the player has beaten the game (reached the Babe). Depending on it's name, you can change the different babes ending music.

|Babe|Namefile|
|---|---|
|First babe|`ending`|
|Second babe|`ending2`|
|Third babe|`ending3`|


### Adding/replacing/removing an ending music

Adding, replacing and removing an ending music have not been yet implemented inside Worldsmith. If you'd like to add, replace or remove them, consider looking out the [**Steps (without Worldsmith)**](./#steps-without-worldsmith-2).
{: .disclaimer }

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

### Adding/replacing an ending music
{: .no_toc }

In order to add it:

1. Convert a sound file into XNB format.
2. Move the file inside `audio/music`.
3. Name it [depending on your babe](#ending-music).
   > If the file already exists, override it.
   {: .highlight }

### Removing an ending music
{: .no_toc }

You can only remove the second and third babe ending music, for the first ending, you will need to manually paste the original ending music from the gamefiles (can be found in `Jump King/Content/audio/music/ending.xnb`).

</div>
</details>

## Next up

You have gone through all steps for level making. If you want suggestions from the community, read [**Tips & Tricks**]({{site.baseurl}}/level-making/tips). For publishing a finished level, go to [**Publishing**]({{site.baseurl}}/publishing).