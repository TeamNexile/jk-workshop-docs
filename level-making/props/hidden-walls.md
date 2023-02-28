---
layout: default
title: Hidden Walls
grand_parent: Level Making
parent: Props
nav_order: 1
last_modified_date: 2023-02-28 12:21
---

# Hidden walls
{: .no_toc }

props that disappear by triggering a hitbox<!-- more -->
{: .fs-6 .fw-300 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What are they used for?

Hidden walls are used in-game to hide areas or make the screen more realistic, the hidden wall works as foreground until the player gets into its position where it becomes transparent.

### Before (without hidden wall)
![Before]({{site.baseurl}}/images/level-making/props/hidden_wall_before_example.png){:title="Before adding the hidden wall"}
### After (with hidden wall)
![After]({{site.baseurl}}/images/level-making/props/hidden_wall_after_example.png){:title="After adding the hidden wall"}


## Dealing with hidden walls

### Adding/replacing/removing a hidden wall (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding a hidden wall (without Worldsmith)

If you want to add a new hidden wall:

1. Convert an image file into a packed XNB file.
   > While there aren't any restrictions with how it should be named, avoid using spaces or special characters and it's suggested that you name it in a way that you can retroactively know which file is later on.
   > An example could be:
   ```
   `SCREEN`_[NAME]_[NUMBER] (e.g. 65_house_1)
   ```
   If you follow such, you can easily tell which screen the hidden wall is used in, what is the hidden wall, and a number if you have more than one hidden walls.
   {: .note }

2. Head to the following folder: `props/hidden_walls`.
3. You can put your new packed hidden wall image inside the `textures` folder. Write down your hidden wall image file name somewhere, this will be used later.
4. Check if you already have an existing xml file for the screen that you want to add your new hidden wall image, you can easily find it by searching "hidden_wall" and then the screen number (e.g. hidden_wall65.xml).
   > **If the file doesn't exists**, don't worry!
   > 1. Copy the following snippet:
      ```xml
        <?xml version="1.0"?>
        <RaymanCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
          <walls>
            <RaymanData> 
              <achievements>                                                <!-- leave this as is -->
                <AchievementCode>GO_THOUGH_ILLUSORY_WALL</AchievementCode>  <!-- leave this as is -->
              </achievements>                                               <!-- leave this as is -->
              <texture_name>YOUR_HIDDEN_WALL_NAME</texture_name>
              <Position>
                <X>YOUR_HIDDEN_WALL_X_POSITION</X>
                <Y>YOUR_HIDDEN_WALL_Y_POSITION</Y>
              </Position>
            </RaymanData>
          </walls>
        </RaymanCollection>
      ```
    > 2. Create a new xml file called `hidden_wall[SCREEN]` (e.g. hidden_wall65.xml), open it and paste the snippet above

    > **If the file already exists**:
    > 1. Copy the following snippet:
      ```xml
        <RaymanData> 
            <achievements>                                                <!-- leave this as is -->
              <AchievementCode>GO_THOUGH_ILLUSORY_WALL</AchievementCode>  <!-- leave this as is -->
            </achievements>                                               <!-- leave this as is -->
            <texture_name>YOUR_HIDDEN_WALL_NAME</texture_name>
            <Position>
              <X>YOUR_HIDDEN_WALL_X_POSITION</X>
              <Y>YOUR_HIDDEN_WALL_Y_POSITION</Y>
            </Position>
          </RaymanData>
      ```
    > 2. Inside the `walls` tag, below already existing `RaymanData`s, paste your snippet.

5. Replace `YOUR_HIDDEN_WALL_NAME` with the filename of your new packed hidden wall.
6. Replace the X and Y (`YOUR_HIDDEN_WALL_X_POSITION` and `YOUR_HIDDEN_WALL_Y_POSITION`) with the relative position of the top-left corner.

### Replacing a hidden wall (without Worldsmith)

To replace an already existing hidden wall image:

1. Convert the new hidden wall image into a packed XNB file.
2. Replace the old file with the new file in the `props/hidden_walls/textures`.
   > If your packed file isn't named the same as before, you will need to change the `texture_name` tag in the xml file(s) that previously had the old file or remove the layer completely.
   {: .highlight }

### Removing a hidden wall (without Worldsmith)

To remove a hidden wall image:

1. Find the hidden wall packed image of your choice and remove it.
2. You will need to remove each  `RaymanData` tag in the xml file(s) that contained your old file as `texture_name`.


## Hidden wall props
Hidden walls can have props too!<br>

Hidden walls props work in the same normal props work, but the xml configuration file is set on a different folder. Please [__read how to make normal props before continuing__]({{site.baseurl}}/level-making/props).

### Adding/replacing/removing a hidden wall prop (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding/replacing/removing wall prop (without Worldsmith)

Hidden wall props are just like [simple props]({{site.baseurl}}/level-making/props#simple-prop).

> The only difference from the simple prop is the directory of the xml configuration file, that is `props/hidden walls props` instead of `props`.
{: .warning }