---
layout: default
title: Hidden Walls
grand_parent: Level Making
parent: Props
nav_order: 1
last_modified_date: 2024-09-20 16:28
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

Hidden walls are graphics placed in front of other layers to hide them. They become transparent when the player touches them.

### Before colliding the hidden wall
![Before]({{site.baseurl}}/images/level-making/props/hidden_wall_before_example.png){:title="Before colliding the hidden wall"}
### After colliding the hidden wall
![After]({{site.baseurl}}/images/level-making/props/hidden_wall_after_example.png){:title="After colliding the hidden wall"}


## Dealing with hidden walls

### Adding a hidden wall

1. Navigate to the **Screens** page.
2. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add a weather.
2. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

	![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

4. Navigate into **Add on screen...** and click on **Hidden wall**.

	![Add hidden wall]({{ site.baseurl }}/images/level-making/props/hidden_wall_context_menu.png)

5. A new prompt will show up asking you some details about your new hidden wall. Write a recognizable name for you, and click **Select sprite**.

	![Add hidden wall]({{ site.baseurl }}/images/level-making/props/hidden_wall_add.png)

6. A new prompt will show up asking to you select a sprite for your hidden wall.

	![Select hidden wall sprite]({{ site.baseurl }}/images/level-making/props/hidden_wall_add_preview.png)

7. After selecting **Open**, click **Add** and your hidden wall should be present in your preview!

	![Hidden wall added]({{ site.baseurl }}/images/level-making/props/hidden_wall_success.png)

### Changing or removing a hidden wall

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the weather you want to change/get rid of.
2. From the right side of the page, expand the **Hidden walls** tab.

    ![Hidden wall settings]({{ site.baseurl }}/images/level-making/props/hidden_wall_settings.png)

3. Change the hidden wall position, SFX trigger and hitboxes as you wish.

    > This might be unstable/working being that it has not been yet completed.
    {: .highlight }

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

### Adding a hidden wall
{: .no_toc }

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

### Replacing a hidden wall
{: .no_toc }

To replace an already existing hidden wall image:

1. Convert the new hidden wall image into a packed XNB file.
2. Replace the old file with the new file in the `props/hidden_walls/textures`.
   > If your packed file isn't named the same as before, you will need to change the `texture_name` tag in the xml file(s) that previously had the old file or remove the layer completely.
   {: .highlight }

### Removing a hidden wall
{: .no_toc }

To remove a hidden wall image:

1. Find the hidden wall packed image of your choice and remove it.
2. You will need to remove each  `RaymanData` tag in the xml file(s) that contained your old file as `texture_name`.


</div>
</details>

## Hidden wall props
Hidden walls can have props too!<br>

Hidden walls props work in the same way normal props work, but the xml configuration file is set on a different folder. Please [__read how to make normal props before continuing__]({{site.baseurl}}/level-making/props).

### Adding a hidden wall prop

2. Right-click onto the canvas on the left side of your screen (where you have your level preview) and select *Add on screen...*, then *Props*, then *Hidden wall prop*.

    ![Prop right click]({{ site.baseurl }}/images/level-making/props/hprop_right_click.png)

3. Once clicked, a prompt will ask you a few details. You will need to select which prop you want to add, choose its position and if you want to prop to be horizontally flipped.

    ![Prop details]({{ site.baseurl }}/images/level-making/props/hprop_prompt.png)

4. Once done setting it up, click **Add**.<br>Your hidden prop should appear on your preview.

    ![Prop added successfully]({{ site.baseurl }}/images/level-making/props/hprop_success.png)

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

### Adding/replacing/removing hidden wall prop
{: .no_toc }

Hidden wall props are just like [simple props]({{site.baseurl}}/level-making/props#simple-prop).

> The only difference from the simple prop is the directory of the xml configuration file, that is `props/hidden walls props` instead of `props`.
{: .warning }

</div>
</details>

## Next up

Go to [**World Items**]({{site.baseurl}}/level-making/props/worlditems).