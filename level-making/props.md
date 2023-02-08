---
layout: default
title: Props
parent: Level Making
nav_order: 5
has_children: true
last_modified_date: 2023-02-08 10:51
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
> Avoid:
> - using props in the final screen to prevent slight visual bugs from the game after beating the level.
> - creating big sprite sheets, the game tends to crash if either the image width or height is over 4000 pixels, if you need to have big sprite sheets try to make a square-looking sprite sheet to lower the chances of crashing. (thanks to Abaddon for the tip!)
{: .note-title }

## Simple prop

The props in-game (such as the bonfire in the first screen) are stored in the `props/textures` folder. Inside this folder, there's a configuration file named `prop_settings.xml` which contains a list of `<PropSetting>` tags.

### Adding/replacing/removing a simple prop (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding a simple prop (without Worldsmith)

> For starters, you should try having a single sprite sheet (just an image).

1. Write down your image's sprite sheet size and its name.
2. Convert the sprite sheet image of your choice into a packed XNB file.
3. Place it inside `props/textures`.
4. In the same folder you should find a xml file called `prop_settings.xml`, open it.
5. Copy the snippet below:
   ```xml
   <PropSettings>
    <name>YOUR_PROP_FILENAME</name>
    <fps>YOUR_PROP_FRAMES_PER_SECOND</fps>
    <sheet_cells>
      <X>YOUR_PROP_SHEET_COLUMNS_NUMBER</X>
      <Y>YOUR_PROP_SHEET_ROWS_NUMBER</Y>
    </sheet_cells>
   </PropSettings>
   ```
6. Replace `YOUR_PROP_FILENAME` with the file name of your prop.
7. Replace `YOUR_PROP_FRAMES_PER_SECOND` to how many frames you want to see per second. If it's your first prop, set it to 10, later on you can always change it.
8. Replace `YOUR_PROP_SHEET_COLUMNS_NUMBER` and `YOUR_PROP_SHEET_ROWS_NUMBER` with the sprite sheet size you wrote down; if it's your first time change both to `1`.

> If you want to change the duration of your frames, you should copy the example below and customize it to your preference. You can add and remove as many `float` as you wish.
  ```xml
    <frames>
      <float>3.8</float>
    </frames>
  ```
{: .highlight }

> If you want to start with a random frame, simply add right before the closing `PropSettings` tag:
  ```xml
    <random_offset>true</random_offset>
  ```
{: .highlight }

Good, you've added a prop so the game can understand its various data. Now let's add it on a screen.

1. Navigate to `props` and check if a `prop[SCREEN].xml` file exists. (e.g., 65th screen = prop65.xml)
   
   > **If the file doesn't exist**, create it and paste the following snippet:
      ```xml
        <?xml version="1.0"?>
        <PropCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
          <Props>
            <PropData>
              <type>YOUR_PROP_NAME</type>
              <Position>
                <X>YOUR_PROP_X_POSITION</X>
                <Y>YOUR_PROP_Y_POSITION</Y>
              </Position>
            </PropData>
          </Props>
        </PropCollection>
      ```
    
   > **If the file exists**, paste the following snippet below an existing prop (below a line of the closing tag of `PropData`):
      ```xml
        <PropData>
          <type>YOUR_PROP_NAME</type>
          <Position>
            <X>YOUR_PROP_X_POSITION</X>
            <Y>YOUR_PROP_Y_POSITION</Y>
          </Position>
        </PropData>
      ```
2. Replace `YOUR_PROP_NAME` with the filename of your prop.
3. Replace `YOUR_PROP_X_POSITION` and `YOUR_PROP_Y_POSITION` to the relative position of your prop.


### Replacing a simple prop (without Worldsmith)

If you want to keep the same prop but change its texture:

1. Convert your new file into a packed XNB file.
2. Place it in `props/textures` and replace the item keeping the same name.
3. If you have changed the sprite sheet, you will need to modify the sprite sheet sizes in the `prop_settings.xml` file inside the same folder of your packed prop.

If you want to replace a prop in a specific screen with another:

1. Write down which screen you'd like to replace the prop.
2. Navigate to the `props` folder and open the `prop[SCREEN].xml` file with [SCREEN] as your screen number (e.g., 65th screen = prop65.xml).
3. Find the prop you want to replace by searching its name, change the `type` value to your new prop.

### Removing a simple prop (without Worldsmith)

To remove a prop:

1. Write down every screen that prop is used from.
2. Navigate to the `props` folder and open the `prop[SCREEN].xml` file with [SCREEN] as your first screen number (e.g., 65th screen = prop65.xml).
3. Find your prop you want to remove by searching its name.
4. Remove the whole `PropData` tag containing the `type` that equals the name of your prop.
5. Repeat Step 2 for each screen that the prop is used from.
6. Once completed, navigate to `props/textures` and open `prop_settings.xml`.
7. Find your prop you want to remove by searching its name again.
8. Remove the whole `PropSettings` tag containing the `name` that equals the name of your prop. 
9. Remove the prop packed XNB file from the same folder.

## Next up

The bonfire has been lit! Let's continue with [**hidden walls**]({{site.baseurl}}/level-making/props/hidden-walls).