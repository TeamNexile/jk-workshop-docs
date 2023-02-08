---
layout: default
title: NPCs
grand_parent: Level Making
parent: Props
nav_order: 3
last_modified_date: 2023-02-08 16:53
---

# NPCs
{: .no_toc }

the entities that talk and barter with you.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

> **NPCs are hardcoded** in the game, so they *can not be removed*; but they **can be modified and/or moved** to a screen you are not using (like 0, 169 or 255).
{: .warning }

## Types of NPCs

NPCs can be of two types:
1. `old man`, a normal entity that **only speaks**.
2. `merchant`, an extension of the `old man` that can also barter items with the player.

# Normal NPCs

Normal NPCs (or by their technical name Old Man NPCs) are a normal entity in-game that speaks once you trigger its hitbox.

Here's a list of 27 normal NPC you can freely modify as you will:

|Name|Sprite sheet directory|Sprite sheet name|
|---|---|---|
|archaeologist|`props/textures/old_man`|`archaeologist`|
|fairy1|`props/textures/old_man`|`fairy1`|
|fairy2|`props/textures/old_man`|`fairy2`|
|fairy3|`props/textures/old_man`|`fairy3`|
|gnome|`props/textures/old_man`|`gnome`|
|hermit|`props/textures/old_man`|`hermit`|
|imp|`props/textures/old_man`|`imp`|
|old_man|`props/textures/old_man`|`old_man`|
|skeleton|`props/textures/old_man`|`skeleton`|
|stoneman1|`props/textures/old_man`|`stoneman1`|
|stoneman2|`props/textures/old_man`|`stoneman2`|
|stoneman3|`props/textures/old_man`|`stoneman3`|
|stoneman4|`props/textures/old_man`|`stoneman4`|
|stoneman5|`props/textures/old_man`|`stoneman5`|
|stoneman6|`props/textures/old_man`|`stoneman6`|
|trollking|`props/textures/old_man`|`trollking`|
|cat_outsider|`props/textures/old_man/owl_chars`|`cat_outsider`|
|cat1|`props/textures/old_man/owl_chars`|`cat1`|
|cat2|`props/textures/old_man/owl_chars`|`cat2`|
|cat3|`props/textures/old_man/owl_chars`|`cat3`|
|cat4|`props/textures/old_man/owl_chars`|`cat4`|
|cat5|`props/textures/old_man/owl_chars`|`cat5`|
|cat6|`props/textures/old_man/owl_chars`|`cat6`|
|cat7|`props/textures/old_man/owl_chars`|`cat7`|
|cat8|`props/textures/old_man/owl_chars`|`cat8`|
|owl_bogman|`props/textures/old_man/owl_chars`|`owl_bogman`|
|owl_boss_gargoyle|`props/textures/old_man/owl_chars`|`owl_boss_gargoyle`|
|owl_gargoyles|`props/textures/old_man/owl_chars`|`owl_gargoyles`|

## Retexturing a normal NPC (without Worldsmith)

To replace a spritesheet of an NPC:

1. Convert a new image into a packed XNB file.
2. Name it as the NPC you want to retexture.
3. Place the file in `props/textures/old_man` and replace the file.
4. If you modified the sprite sheet, you will need to modify the [sprite sheets](#sprite-sheet) and the [animation settings](#animation-settings) inside your NPC's configuration file.

While the textures for both needs to be inside `props/textures/old_man`, the quotes and settings of each NPC is stored based of their type:
- `old man`, is stored inside `props/textures/old_man/lines`
- `merchant`, is stored inside `props/textures/old_man/merchant`

## General settings

Settings related to the principal details of the NPC such as:

- name of the NPC (leave as is),
- sprite sheet,
- position,
- home screen, 
- font,
- text layer,
- npc layer,
- random count

### Sprite sheet

The sprite sheet (or sprite cells) is the combination of the rows and columns count.

#### Setting the sprite sheet (without Worldsmith)
{: .no_toc }

1. Search for the `sprite_cells` tag.
2. Modify the X value with the column count in your packed XNB file.
3. Modify the Y value with the row count in your packed XNB file.

### Position and home screen

The following settings are related to the position of your NPC. The home screen will set the NPC to a specific screen, meanwhile the position will set the position inside the screen of your choice with X and Y coordinates.

#### Setting the position (without Worldsmith)
{: .no_toc }

1. Search for the `position` tag.
2. Modify the X and Y values with the relative values of your choice.

#### Setting the home screen (without Worldsmith)
{: .no_toc }

1. Search for the `home_screen` tag.
2. Modify its value to the screen of your choice.

### Other settings (optional)

Other settings can be:

|tag name|what does it change|possible values|
|---|---|---|
|font|The font of the text|[OldManFont API]({{site.baseurl}}/api/props#oldmanfont){:target="_blank"}|
|text_layer|The layer of the text|[OldManRenderingLayer API]({{site.baseurl}}/api/props#OldManRenderingLayer){:target="_blank"}|
|npc_layer|The layer of the NPC|[PersonRenderingLayer API]({{site.baseurl}}/api/props#PersonRenderingLayer){:target="_blank"}|
|random_count|Randomizes the order of the frames|a integer number between 0 and total number of frames in the sprite sheet|

#### Setting one of the settings above (without Worldsmith)
{: .no_toc }

1. Check if the tag you are looking exists.
2. If the tag doesnt exist, create it like this example below:
   ```xml
    <text_layer>VALUE_HERE</text_layer>
   ```
3. Replace `VALUE_HERE` with the possible values following the table above.

## Speech bubble and trigger box, talk-related settings

All settings that will about triggering the NPC, its talk speed, talk delay and speech bubble size.

### Speech bubble format

The bubble format can help you format text the way you want it; by aligning it differently, setting the anchor for your text and deciding the maximum width of the NPC's speech.

#### Setting the speech bubble format (without Worldsmith)
{: .no_toc }

1. Search for the `bubble_format` tag.
2. Replace the `direction` value with either **Left** or **Right**, depending where you want the text to align.
2. Replace the `X` and `Y` values with their [respective values]({{site.baseurl}}/api/props#speechbubbleformat){: target="_blank"}.
3. Replace the `width` value with your speech maximum width.

### Trigger box

The `trigger_box` tag is needed to trigger the NPC to speak.

#### Setting the trigger box (without Worldsmith)
{: .no_toc }

1. Search for the `trigger_box` tag.
2. Modify the `X` and `Y` **values** with relative values of your screen.
    > You can easily see the values in the build mode by changing it from Absolute to Relative from the Pause Menu. Also thanks to the "Hitbox first" toggle in the build mode, you can easily see where the hitbox is, and fix it with ease.
    {: .highlight }
3. Modify the `Width` and `Height` **values** with the size wanted.

> By default, your item will start from the X and Y values given and expand right and down. If you want your item to be centered, change both `hitbox_center`'s X and Y to `0.5`, or if you want it to start from the right, change it to `0`. If this sounds confusing, test it in-game!
{: .note }

### Talk delay and talking speed

You can also change:
- **the talk delay**, which is the delay from when you enter the NPC's hitbox and when the NPC start talking;
- **the talking speed**, which is the speed of which every letter spawns on-screen

#### Setting the talk delay (without Worldsmith)
{: .no_toc }

1. Search for the `talk_delay` tag.
2. Modify the `talk_delay` to whatever value you want.
   > The value equals in seconds.

#### Setting the talking speed (without Worldsmith)
{: .no_toc }

1. Search for the `talking_speed` tag.
2. Modify the `talking_speed` to whatever value you want.
   > Higher is faster.

## Animation settings

With the following settings you can set the main two animation cycles: talking and busy (time-out/pause) animations. In order to set this, it is recommended that you have your sprite image opened on the side so you can check while adding them.

### Talk animation

#### Setting the talk frames (without Worldsmith)
{: .no_toc }

To add new talk frames:

1. Search for the `talk_animation` tag.
2. Remove the all existing `AnimationFrame`.
1. Copy the following snippet:
   ```xml
    <AnimationFrame>
      <sprite_index>YOUR_SPRITE_INDEX</sprite_index>
      <duration>YOUR_SPRITE_DURATION</duration>
    </AnimationFrame>
   ```
2. If it's the first frame, paste it one line below the opening tag on `frames` otherwise add it after the ending tag of the previous `AnimationFrame`.
3. Replace `YOUR_SPRITE_INDEX` with the [index of the frame]({{site.baseurl}}/level-making/props#animation-index){:target="_blank"}.
4. Replace `YOUR_SPRITE_DURATION` with the duration (in seconds) of the frame. 
5. Repeat step 3 for each talking frames.

> The talk frame will be looped from the first to the last `AnimationFrame`.
{: .disclaimer }

To remove a talk frame:

1. Find the [index of the frame]({{site.baseurl}}/level-making/props#animation-index){:target="_blank"} you don't want to be part of the animation.
2. Search for the `talk_animation` tag.
3. Remove the whole `AnimationFrame` that contains the `sprite_index` that equals to your frame index.

### Busy animation

#### Setting the busy frames (without Worldsmith)
{: .no_toc }

The process is the same as the [talk animation](#talk-animation) but you need to search for the `busy_animation` instead.

## Speeches

The speeches are the text that will show on screen (what will the NPC say).

There are 6 different types of speeches which can be used and their use can vary:

|Type|Usage|Will they get repeated?|
|---|---|---|
|Intro quote|Used to introduce the NPC to the player, it is the first thing an NPC will say if it has any and if there isn't any flag quotes|No.|
|Flag quotes|Used to determine if the player has beaten an existing map (such as Main Babe, NB+ or GotB), it will not be looped.|No.|
|Looping quotes|Generic quotes and speeches.|Yes.|
|Screen quotes|Unlocks new quotes by reaching a specific screen.|Yes.|
|Item quotes|Unlocks new quotes if the user is wearing an item.|Yes.|
|Fall quotes|Unlocks new quotes by reaching a range of falls.|Yes.|

Before starting you should understand the difference between quote and strings. Strings are usually made of a phrase or portions or a phrase (depending on the size of the speech bubble); a group of strings will play one string after another without big pauses. A quote is a group of strings that the NPC will read through before being quiet for some seconds.

### Intro quote

#### Setting an intro quote (without Worldsmith)
{: .no_toc }

1. Search for the `intro_quote` tag.
   > If you are missing `intro_quote` paste the following snippet below `talking_speed`.
      ```xml
        <intro_quote>
          <lines>
            <string>My first speech!</string>
            <string>What what? Did I say that?</string>
          </lines>
        </intro_quote>
      ```
    {: .disclaimer }

2. Get rid of all the `string` tags that could be present.
3. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
4. Replace `YOUR_STRING_HERE` with your intro string.
   > You can add as many string as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   {: .highlight }

### Flag quotes

#### Setting flag quotes (without Worldsmith)
{: .no_toc }

1. Search for the `flag_quotes` tag.
   > If you are missing `flag_quotes` paste the following snippet below `talking_speed`.
      ```xml
        <flag_quotes>
          <OldManFlagQuote>
            <flag>CompletedNormalGame</flag>
            <quotes>
              <lines>
                <string>So tell me...</string>
                <string>is the Babe any good?</string>
              </lines>
            </quotes>
          </OldManFlagQuote>
        </flag_quotes>
      ```
    {: .disclaimer }

2. Replace the `flag` value with a [possible flag value]({{site.baseurl}}/api/props#StoryEventFlags){: target="_blank"}.
3. Get rid of all the `string` tags that could be present.
4. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
5. Replace `YOUR_STRING_HERE` with your flag string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many group of strings as you want by copying the `lines` tag and pasting it below the closing tag of the previous `lines`.
   {: .highlight }

> You can even add more flags!
> 
> By copying the existing entire `OldManFlagQuote` (or copying it from above) and pasting it right after the closing tag (in a new line) of the `OldManFlagQuote` you've just done, you can add another flag and a bunch of new speeches!
{: .note-title }

### Looping quotes

#### Setting looping quotes (without Worldsmith)
{: .no_toc }

1. Search for the `looping_lines` tag.
   > If you are missing `looping_lines` paste the following snippet below `talking_speed`.
      ```xml
        <looping_lines>
          <OldManQuote>
            <lines>
              <string>This is looped.</string>
              <string>Did I say that already?</string>
            </lines>
          </OldManQuote>
        </looping_lines>
      ```
    {: .disclaimer }

2. Get rid of all the `string` tags that could be present.
3. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
4. Replace `YOUR_STRING_HERE` with your flag string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many quotes as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

### Screen quotes

#### Setting screen quotes (without Worldsmith)
{: .no_toc }

1. Search for the `screens` tag.
   > If you are missing `screens` paste the following snippet below `talking_speed`.
      ```xml
        <screens>
          <OldManScreen>
            <screen>YOUR_SCREEN_NUMBER</screen>
            <quotes>
              <OldManQuote>
                <lines>
                  <string>Finally you got there!</string>
                  <string>It took you some time, huh...</string>
                </lines>
              </OldManQuote>
            </quotes>
          </OldManScreen>
        </screens>
      ```
    {: .disclaimer }

2. Replace `YOUR_SCREEN_NUMBER` with the screen number where you want the quote(s) to unlock.
3. Get rid of all the `string` tags that could be present.
4. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
5. Replace `YOUR_STRING_HERE` with your string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many group of strings as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

> You can even add more screen checks!
> 
> By copying the existing entire `OldManScreen` (or copying it from above) and pasting it right after the closing tag (in a new line) of the `OldManScreen` you've just done, you can add another screen check and a bunch of new speeches!
{: .note-title }

### Item quotes

#### Setting item quotes (without Worldsmith)
{: .no_toc }

1. Search for the `items` tag.
   > If you are missing `items` paste the following snippet below `talking_speed`.
      ```xml
        <items>
          <OldManItem>
            <item>YOUR_ITEM_TRIGGER</item>
            <quotes>
              <OldManQuote>
                <lines>
                  <string>What have you got there?</string>
                  <string>Can I also have those shiny boots?</string>
                </lines>
              </OldManQuote>
            </quotes>
          </OldManItem>
        </items>
      ```
    {: .disclaimer }

2. Replace `YOUR_ITEM_TRIGGER` with the [wearable item]({{site.baseurl}}/api/items){:target="_blank"} you want the quote(s) to unlock with.
3. Get rid of all the `string` tags that could be present.
4. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
5. Replace `YOUR_STRING_HERE` with your string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many group of strings as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

> You can even add more screen checks!
> 
> By copying the existing entire `OldManItem` (or copying it from above) and pasting it right after the closing tag (in a new line) of the `OldManItem` you've just done, you can add another item check and a bunch of new speeches!
{: .note-title }

### Fall quotes

#### Setting fall quotes (without Worldsmith)
{: .no_toc }

1. Search for the `falls` tag.
   > If you are missing `falls` paste the following snippet below `talking_speed`.
      ```xml
        <falls>
          <OldManItem>
            <fallStart>YOUR_FALL_NUMBER_START</fallStart>
            <fallEnd>YOUR_FALL_NUMBER_END</fallEnd>
            <quotes>
              <OldManQuote>
                <lines>
                  <string>Oh hey you again! Haha!</string>
                  <string>I've seen you fall here at least five times already!</string>
                </lines>
              </OldManQuote>
            </quotes>
          </OldManItem>
        </falls>
      ```
    {: .disclaimer }

2. Replace `YOUR_FALL_NUMBER_START` with the starting number of falls you want the quote(s) to unlock with.
3. Replace `YOUR_FALL_NUMBER_END` with the ending number of falls you want the quote(s) to unlock with.
4. Get rid of all the `string` tags that could be present.
5. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
6. Replace `YOUR_STRING_HERE` with your string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many group of strings as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

> You can even add more screen checks!
> 
> By copying the existing entire `OldManFall` (or copying it from above) and pasting it right after the closing tag (in a new line) of the `OldManFall` you've just done, you can add another fall check and a bunch of new speeches!
{: .note-title }

# Next up
{: .text-beta }

The NPC hell is not over yet! [**Merchants**]({{site.baseurl}}/level-making/props/merchants) are missing!