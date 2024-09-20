---
layout: default
title: Screens
parent: Level Making
nav_order: 4
last_modified_date: 2024-09-20 16:59
---

# Screens folder
{: .no_toc }

contains textures such as background, foreground, midground, scrolling images and masks.<!-- more -->
{: .fs-6 .fw-300 }

All of the layers of a screen can be merged to make a result like the example below (*without counting the hidden wall because that's a type of prop*). Every layer has its own name, format and folder; hover on the image below and click on the image you want to know more about!

## Image of contents
{: .no_toc .text-delta }

<div class="skewd" id="example">
    <a href="#background">
        <img src="{{ site.baseurl }}/images/level-making/screens/background.png" title="Background" alt="bg">
    </a>
    <a href="#scrolling">
        <img src="{{ site.baseurl }}/images/level-making/screens/scroll.png" title="Scrolling image" alt="scrolling">
    </a>
    <a href="#midground">
        <img src="{{ site.baseurl }}/images/level-making/screens/midground.png" title="Midground" alt="mg">
    </a>
    <a href="#weather-and-mask">
        <img src="{{ site.baseurl }}/images/level-making/screens/masked.png" title="Weather & Mask" alt="mask">
    </a>
    <a href="#foreground">
        <img src="{{ site.baseurl }}/images/level-making/screens/foreground.png" title="Foreground" alt="fg">
    </a>
</div>

---

<style>
    .skewd {
        position: relative;
        width: 100%;
        padding-bottom: calc(75% + 4px);
        transition: 0.5s;
        overflow: hidden;
    }
    .skewd:not(:hover) a {
        opacity: 1;
    }
    .skewd:hover a:not(:hover) {
        opacity: 0.1;
        filter: grayscale(0.6);
        border-left-color: black;
    }
    .skewd a {
        position: absolute;
        width: 100%;
        transition: .5s;
        opacity: 1;
        border: solid 2px transparent;
        text-decoration: none!important;
        line-height: 0;
    }
    .skewd a img {
        width: 100%;
    }
    .skewd a:hover {
        opacity: 1;
        border-color: red;
    }
    .skewd:hover a:nth-child(2) {
        transform: translate(11.1%);
    }
    .skewd:hover a:nth-child(3) {
        transform: translate(22.2%);
    }
    .skewd:hover a:nth-child(4) {
        transform: translate(33.3%);
    }
    .skewd:hover a:nth-child(5) {
        transform: translate(44.4%);
    }
</style>

> **All the following details can be found inside the Screen page**, therefore the documentation is omitting the unnecessary **Screens** page navigation on each step.
{: .disclaimer }

## Background

At the lowest ground there's the background.<br>
The background is commonly used for **skies or gradients** to put on the back end of screens.

### Adding a background

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add a background.
2. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

    ![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

3. Navigate into **Add on screen...**, then **Grounds**, then click on **Background**.

    ![Add background]({{ site.baseurl }}/images/level-making/screens/background_add.png)

4. Select your background image and click **Open**.

    ![Select background]({{ site.baseurl }}/images/level-making/screens/background_add_preview.png)

5. After clicking Open, you should be able to see your new background inside Worldsmith!

    ![New background]({{ site.baseurl }}/images/level-making/screens/background_success.png)

### Replacing or removing a background

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the background you want to change/get rid of.
3. From the right side of the page, expand the **Grounds** tab.

    ![Replace/delete background]({{ site.baseurl }}/images/level-making/screens/background_replace_delete.png)

From here, you can click **Replace** (the yellow button) to replace an existing background with another one, or click **Delete** (the red button) to delete the background.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">
   
### Adding/replacing a background

To add a new or replace an existing background:

1. If you are not using Worldsmith, convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**File name**|bg`SCREEN NUMBER`<br>(e.g. bg65)|

2. Place the new packed file in the `screens/background` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a background

To remove an unwanted background:

1. Navigate to the `screens/background` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the background of your 5th screen, you will remove `bg65.xnb`.

</div>
</details>

<br>

## Scrolling images
{: #scrolling }

The scrolling texture is commonly used for **mist clouds or birds** flying in the distance [right before the player layer but above the background](#example).

### Adding a scrolling image

1. Navigate to the **Screens** page.
2. Right-click onto the canvas on the left side of your screen (where you have your level preview) and select *Add on screen...*, then *Scrolling image*.

    ![Scrolling image right click]({{ site.baseurl }}/images/level-making/screens/scrolling_right_click.png)

3. Once clicked, a prompt will ask you a few details; mainly the scrolling image name and the scrolling image itself.

    ![Scrolling image details]({{ site.baseurl }}/images/level-making/screens/scrolling_prompt.png)

4. After choosing a recognizable scrolling image name, click on **Add texture**. A new prompt will ask you to select your scrolling image file. Once done, click **Open**.

    ![Scrolling image texture]({{ site.baseurl }}/images/level-making/screens/scrolling_select_image.png)

5. Added your texture, you could add additional details by opening the dropdown labeled as such.
6. Once done, click **Add**. Your scrolling image should be moving right away inside your preview.

    ![Scrolling image added successfully]({{ site.baseurl }}/images/level-making/screens/scrolling_success.png)

### Replacing or deleting a scrolling image

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the scrolling image you want to change/get rid of.
3. From the right side of the page, expand the **Scrolling images** tab.

    ![Scrolling image tab]({{ site.baseurl }}/images/level-making/screens/scrolling_tab.png)

4. Click on the scrolling image you are looking for helping you by viewing the preview on the left side.

    ![Click scrolling image]({{ site.baseurl }}/images/level-making/screens/scrolling_click.png)

From here, you can click **Replace** (the two arrows yellow button) to replace an existing scrolling image with another one, or click **Delete** (the red button) to delete the scrolling image.

![Scrolling image settings]({{ site.baseurl }}/images/level-making/screens/scrolling_settings.png?v=0)

Use the Position inputbox to move your scrolling image through the screen, change its direction (horizontal or vertical) with the dropdown labelled as Direction, change its scroll multiplier (to make it faster or slower and changing directions) with the dedicated scroll bar or change its layer to make your scrolling image more immersive inside your screen.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

The scrolling images are managed by an XML file, that determines their texture, position, velocity, layer mode and possible additional frames. In order to have a working scrolling image, you will need to have both the XML file and the packed XNB file.

> If this is the first time hearing about XMLs, [find out what they are and how to use them]({{ site.baseurl }}/getting-started/filetypes).
{: .highlight }

### Adding a scrolling image

If you want to add a new scrolling image:

1. If you are not using Worldsmith, convert an image file into a packed XNB file.
   > While there aren't any restrictions with how it should be named, avoid using spaces or special characters and it's suggested that you name it in a way that you can retroactively know which file is later on.
   > An example could be:
   ```
   `SCREEN`_[NAME]_[NUMBER] (e.g. 65_clouds_1)
   ```
   If you follow such, you can easily tell which screen the scrolling image is used from, what is in the scrolling image, and a number if you have more than one scrolling images.
   {: .note }

2. Head to the following folder: `screens/scrolling`.
3. You can put your new packed scrolling image inside the `textures` folder. Write down your scrolling image file name somewhere, this will be used later.
4. Check if you already have an existing xml file for the screen that you want to add your new scrolling image, you can easily find it by searching "scroll" and then the screen number (e.g. scroll65.xml).
   > **If the file doesn't exists**, don't worry!
   > 1. Copy the following snippet:
    ```xml
        <?xml version="1.0"?>
        <ScrollingBGdata xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
            <scroll_speed>10</scroll_speed>
            <layers>
                <Layer>
                    <texture>YOUR_SCROLLING_IMAGE_NAME_HERE</texture>
                    <position>0</position>
                    <scroll_multiplier>1</scroll_multiplier>
                    <direction>Horizontal</direction>
                </Layer>
            </layers>
        </ScrollingBGdata>
    ```
   > 2. Create a new xml file called `scroll[SCREEN]` (e.g. scroll65.xml), open it and paste the snippet above

   > **If the file already exists**:
   > 1. Copy the following snippet:
    ```xml
        <Layer>
            <texture>YOUR_SCROLLING_IMAGE_NAME_HERE</texture>
            <position>0</position>
            <scroll_multiplier>1</scroll_multiplier>
            <direction>Horizontal</direction>
        </Layer>
    ```
    > 2. Inside the `layers` tag, below already existing `Layer`s, paste your snippet.

5. Replace `YOUR_SCROLLING_IMAGE_NAME_HERE` with the filename of your new packed scroll image.
6. Replace `Horizontal` with `Vertical` if you'd like your scrolling image to display vertically.

### Replacing a scrolling image

To replace an already existing scrolling image:

1. Convert the new scrolling image into a packed XNB file.
2. Replace the old file with the new file in the `screens/scrolling/textures`.
   > If your packed file isn't named the same as before, you will need to change the `texture` tag in the xml file(s) that previously had the old file or remove the layer completely.
   {: .highlight }

### Removing a scrolling image

To remove a scrolling image:

1. Find the scrolling packed image of your choice and remove it.
2. You will need to remove each  `Layer` tag in the xml file(s) that contained your old file as `texture`.
   
If you want the scrolling image to start in a different X position, change the `position` tag into the X value you want. Same goes for the velocity of the scroll image, if you think it's too fast or too slow, change the `scroll_multiplier` to the value that you want. The higher is the number the faster it will go, and dont' worry, the number works both in positive and negative.
{: .note }

</div>
</details>

<br>

## Midground
Right after the scrolling images, there's the midground.<br>
The midground is usually used for **platforms and details** that are **behind the player** (the player can go over them).

### Adding a midground

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add a midground.
2. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

    ![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

3. Navigate into **Add on screen...**, then **Grounds**, then click on **Midground**.

    ![Add midground]({{ site.baseurl }}/images/level-making/screens/midground_add.png)

4. Select your midground image and click **Open**.

    ![Select midground]({{ site.baseurl }}/images/level-making/screens/midground_add_preview.png)

5. After clicking Open, you should be able to see your new midground inside Worldsmith!

    ![New midground]({{ site.baseurl }}/images/level-making/screens/midground_success.png)

### Replacing or removing a midground

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the midground you want to change/get rid of.
3. From the right side of the page, expand the **Grounds** tab.

    ![Replace/delete midground]({{ site.baseurl }}/images/level-making/screens/midground_replace_delete.png)

From here, you can click **Replace** (the yellow button) to replace an existing midground with another one, or click **Delete** (the red button) to delete the midground.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

### Adding/replacing a midground

To add a new or replace an existing midground:

1. If you are not using Worldsmith, convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**File name**|`SCREEN NUMBER`<br>(e.g. 65)|

2. Place the new packed file in the `screens/midground` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a midground

To remove an unwanted midground:

1. Navigate to the `screens/midground` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the midground of your 5th screen, you will remove `5.xnb`.

</div>
</details>

<br>

## Weather
{: #weather-and-mask }

Weather is above the player layer-wise.<br>The weather is a particle effect that can help to create depth in your level.

> We are planning to change the weather to make it more customizable in the future. As of now, it works in the same way JumpKingPlus did.
{: .new }

### Adding a weather

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add a weather.
2. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

    ![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

3. Navigate into **Add on screen...**, then **Weather and mask**, then click on **Weather**.

    ![Add weather]({{ site.baseurl }}/images/level-making/screens/weather_add.png)

4. A new prompt will show up asking to you select a weather.

    ![Select weather]({{ site.baseurl }}/images/level-making/screens/weather_add_select.png)

5. After selecting a weather, click Clise and you should be able to see your new weather inside Worldsmith!

    ![New weather]({{ site.baseurl }}/images/level-making/screens/weather_success.png)

### Replacing or removing a weather

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the weather you want to change/get rid of.
3. From the right side of the page, expand the **Weather and mask** tab.

    ![Replace/delete weather]({{ site.baseurl }}/images/level-making/screens/weather_replace_delete.png)

From here, you can click **Replace** (the yellow button with the arrows) to replace an existing weather with another one, click **Delete** (the red button) to **remove the weather** from the current screen or **change the weather settings** (with the yellow button with the cog).

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

The `weather.xml` file can be found inside the `particles` folder of your level.

### Adding/removing weather 

1. Make a list of the screens where you want to add a specific weather.
   
   ![List screens]({{site.baseurl}}/images/level-making/particles/weather_screen.png)
2. Navigate to `particles` and open `weather.xml`.
   
   ![Navigate]({{site.baseurl}}/images/level-making/particles/weather_folder.png)
3. Inside this file you should see plenty of pre-existing particles that can be used for your level. Find [**which weather to use**]({{site.baseurl}}/api/particles){: target="_blank"}.
4. Navigate to the `Weather` tag that contains your chosen value.
   
   ![Find]({{site.baseurl}}/images/level-making/particles/weather_find_tag.png)
5. Inside `screens`, add the following snippet and replace `YOUR_HITBOX_SCREEN` with the screen number for each screen you want to have the weather in:
   ```xml
    <int>YOUR_HITBOX_SCREEN</int>
   ```

   ![Done]({{site.baseurl}}/images/level-making/particles/weather_done.png)
6. If you want to modify the velocity, you can tinker with the `fps` value.
   
   ![FPS]({{site.baseurl}}/images/level-making/particles/weather_fps.png)

    > Despite the weather is behind the player by default, the **weather can be on the foreground** by adding the following snippet in the `Weather` tag.
      ```xml
        <foreground>true</foreground>
      ```
    {: .disclaimer }

To remove the weather from one or multiple screens:

1. Write down the screen(s) you want to remove the weather.

   ![List screens]({{site.baseurl}}/images/level-making/particles/weather_remove_screen.png)
2. Navigate to `particles` and open `weather.xml`.
   
   ![Navigate]({{site.baseurl}}/images/level-making/particles/weather_folder.png)
3. Search for each screen number and remove their entire `int` tag.
   
   ![Navigate]({{site.baseurl}}/images/level-making/particles/weather_remove_done.png)

</div>
</details>

> If you wanted to show the weather only in a portion of the screen, continue reading about weather masks.
{: .highlight }

## Mask for weather

The weather, being an effect that repeats on the whole screen, can be rather annoying or obstructing other details on screen, that's there the mask comes in. Masks can be used to give more depth to the level by cutting out the unnecessary particle (for example, inside a building like [shown above](./#example)).

![Mask]({{site.baseurl}}/images/level-making/screens/mask.png)

The mask works just like the difference effect on Photoshop, which lets you **display the particles effect only on the blue/cyan (<input type="color" value="#0094FF"> #0094FF) mask you are creating**.

> The mask only takes effect if a **weather is present on a certain screen**. Check out [__how to add a weather__](./#adding-a-weather) on a screen before continuing.
{: .warning }

### Adding weather mask

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add a weather mask.
2. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

    ![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

3. Navigate into **Add on screen...**, then **Weather and mask**, then click on **Mask**.

    ![Add mask]({{ site.baseurl }}/images/level-making/screens/mask_add.png)

4. Select your mask image and click **Open**.

    ![Select mask]({{ site.baseurl }}/images/level-making/screens/mask_add_preview.png)

5. After clicking Open, you should be able to see your new mask inside Worldsmith!

    ![New mask]({{ site.baseurl }}/images/level-making/screens/mask_success.png)

### Replacing or removing a weather mask

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the weather mask you want to change/get rid of.
3. From the right side of the page, expand the **Weather and mask** tab.

    ![Replace/delete mask]({{ site.baseurl }}/images/level-making/screens/mask_replace_delete.png)

From here, you can click **Replace** (the yellow button) to replace an existing weather mask with another one, or click **Delete** (the red button) to delete the mask.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

### Adding/replacing a mask

To add a new or replace an existing mask:

1. Make sure you've set the correct particle in your particle configuration file.
2. If you are not using Worldsmith, convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**File name**|`MASK NAME`mask`SCREEN NUMBER`<br>(e.g. ashmask65)|

3. Place the new packed file in the `screens/masks` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a mask

To remove an unwanted mask:

1. Navigate to the `screens/masks` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the midground of your 5th screen, you will remove whatever file ends with "[...]mask5.xnb".

> Removing a mask inside a screen that has already a particle effect (written on `particles/weather.xml`) will display the effect on the whole screen. If you want to remove the particle effect, see [how you can remove it]({{ site.baseurl }}/level-making/particles).

</div>
</details>

<br>

## Foreground
The foreground work one layer above the masks and particles.<br>
The foreground is used for **details that are in front of the player**, such as vines or grass.

### Adding a foreground

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add a foreground.
2. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

    ![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

3. Navigate into **Add on screen...**, then **Grounds**, then click on **Foreground**.

    ![Add foreground]({{ site.baseurl }}/images/level-making/screens/foreground_add.png)

4. Select your foreground image and click **Open**.

    ![Select foreground]({{ site.baseurl }}/images/level-making/screens/foreground_add_preview.png)

5. After clicking Open, you should be able to see your new foreground inside Worldsmith!

    > Your foreground might be disabled in the preview by default. To show it, from the right side of the page, expand the **Grounds** tab and click on the **Eye** icon to show/hide your foreground.
    {: .highlight }

    ![New foreground]({{ site.baseurl }}/images/level-making/screens/foreground_success.png)


### Replacing or removing a foreground

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the foreground you want to change/get rid of.
3. From the right side of the page, expand the **Grounds** tab.

    ![Replace/delete foreground]({{ site.baseurl }}/images/level-making/screens/foreground_replace_delete.png)

From here, you can click **Replace** (the yellow button) to replace an existing foreground with another one, or click **Delete** (the red button) to delete the foreground.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

### Adding/replacing a foreground

To add a new or replace an existing foreground:

1. If you are not using Worldsmith, convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**File name**|fg`SCREEN NUMBER`<br>(e.g. fg65)|

2. Place the new packed file in the `screens/foreground` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a foreground

To remove an unwanted foreground:

1. Navigate to the `screens/foreground` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the foreground of your 5th screen, you will remove `fg5.xnb`.

</div>
</details>

---

## Screens folder recap

Let's recap the main details for the packed files you will need.

Title|Resolution|File name|Folder|Needs XML?
---|---|---|---
Background|480x360 pixels|bg`SCREEN`<br>(e.g. bg65)|`screens/background/`|❌
Scrolling image|any|any|`screens/scrolling/textures/`|✔️
Midground|480x360 pixels|`SCREEN`<br>(e.g. 65)|`screeens/midground/`|❌
Mask|480x360 pixels|`MASK_NAME`mask`SCREEN`<br>(e.g. ashmask65)|`screens/masks/`|❌
Foreground|480x360 pixels|fg`SCREEN`<br>(e.g. fg65)|`screens/foreground/`|❌

## Next up

Go to [**GUI**]({{site.baseurl}}/level-making/gui) to learn where to put the screens in the GUI folder.