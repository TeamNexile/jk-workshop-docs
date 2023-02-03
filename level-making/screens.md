---
layout: default
title: Screen
parent: Level Making
nav_order: 4
last_modified_date: 2022-02-03 14:00
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
    <a href="#masks">
        <img src="{{ site.baseurl }}/images/level-making/screens/masked.png" title="Mask" alt="mask">
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

## Background

At the lowest ground there's the background.<br>
The background is commonly used for **skies or gradients** to put on the back end of screens.

### Adding/replacing/removing a background (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding/replacing a background (without Worldsmith)

To add a new or replace an existing background:

1. Convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**nomenclature**|bg`SCREEN NUMBER`<br>(e.g. bg65)|

2. Place the new packed file in the `screens/background` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a background (without Worldsmith)

To remove an unwanted background:

1. Navigate to the `screens/background` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the background of your 5th screen, you will remove `bg65.xnb`.

<br>

## Scrolling images
{: #scrolling }

The scrolling texture is commonly used for **mist clouds or birds** flying in the distance [right before the player layer but above the background](#example).

The scrolling images are managed by an .xml file, that determines their texture, position, velocity, layer mode and possible additional frames. In order to have a working scrolling image, you will need to have both the xml file and the packed XNB file.

### Adding/replacing/removing a scrolling image (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding a scrolling image (without Worldsmith)

If you want to add a new scrolling image:

1. Convert an image file into a packed XNB file.
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
        </Layer>
    ```
    > 2. Inside the `layers` tag, below already existing `Layer`s, paste your snippet.

5. Replace `YOUR_SCROLLING_IMAGE_NAME_HERE` with the filename of your new packed scroll image.

### Replacing a scrolling image (without Worldsmith)

To replace an already existing scrolling image:

1. Convert the new scrolling image into a packed XNB file.
2. Replace the old file with the new file in the `screens/scrolling/textures`.
   > If your packed file isn't named the same as before, you will need to change the `texture` tag in the xml file(s) that previously had the old file or remove the layer completely.
   {: .highlight }

### Removing a scrolling image (without Worldsmith)

To remove a scrolling image:

1. Find the scrolling packed image of your choice and remove it.
2. You will need to remove each  `Layer` tag in the xml file(s) that contained your old file as `texture`.
   
If you want the scrolling image to start in a different X position, change the `position` tag into the X value you want. Same goes for the velocity of the scroll image, if you think it's too fast or too slow, change the `scroll_multiplier` to the value that you want. The higher is the number the faster it will go, and dont' worry, the number works both in positive and negative.
{: .note }

<br>

## Midground
Right after the scrolling images, there's the midground.<br>
The midground is usually used for **platforms and details** that are **behind the player** (the player can go over them).

### Adding/replacing/removing a midground (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding/replacing a midground (without Worldsmith)

To add a new or replace an existing midground:

1. Convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**nomenclature**|`SCREEN NUMBER`<br>(e.g. 65)|

2. Place the new packed file in the `screens/midground` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a midground (without Worldsmith)

To remove an unwanted midground:

1. Navigate to the `screens/midground` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the midground of your 5th screen, you will remove `5.xnb`.

<br>

## Masks for particles
{: #masks }

Masks (and so particles) are above the player layer-wise.<br>
Masks can be used to give more depth to the level.

The mask works just like the difference effect on Photoshop, which lets you **display the particles effect only on the blue/cyan mask you are creating**.

> The mask only takes effect if a **particle effect is enabled on a certain screen**. Head over in the [__particles section to learn how to add particles__]({{ site.baseurl }}/level-making/particles) on a screen before continuing.
{: .warning }

### Adding/replacing/removing a midground (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding/replacing a mask (without Worldsmith)

To add a new or replace an existing mask:

1. Make sure you've set the correct particle in your particle configuration file.
2. Convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**nomenclature**|`MASK NAME`mask`SCREEN NUMBER`<br>(e.g. ashmask65)|

3. Place the new packed file in the `screens/masks` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a mask (without Worldsmith)

To remove an unwanted mask:

1. Navigate to the `screens/masks` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the midground of your 5th screen, you will remove whatever file ends with "[...]mask5.xnb".

> Removing a mask inside a screen that has already a particle effect (written on `particles/weather.xml`) will display the effect on the whole screen. If you want to remove the particle effect, see [how you can remove it]({{ site.baseurl }}/level-making/particles).

<br>

## Foreground
The foreground work one layer above the masks and particles.<br>
The foreground is used for **details that are in front of the player**, such as vines or grass.

### Adding/replacing/removing a foreground (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding/replacing a foreground (without Worldsmith)

To add a new or replace an existing foreground:

1. Convert an image file into a packed XNB file with the following details:

    |**resolution**|480x360 pixels|
    |**nomenclature**|fg`SCREEN NUMBER`<br>(e.g. fg65)|

2. Place the new packed file in the `screens/foreground` folder.
    > If a file is already existing, replace it with the new file.
    {: .highlight }

### Removing a foreground (with Worldsmith)

To remove an unwanted foreground:

1. Navigate to the `screens/foreground` folder.
2. Simply delete the file that you don't want.<br>Following the logic, if you don't want the foreground of your 5th screen, you will remove `fg5.xnb`.

---

## Screens folder recap

Let's recap the main details for the packed files you will need.

Title|Resolution|Nomenclature|Folder|Needs XML?
---|---|---|---
Background|480x360 pixels|bg`SCREEN`<br>(e.g. bg65)|`screens/background/`|❌
Scrolling image|any|any|`screens/scrolling/textures/`|✔️
Midground|480x360 pixels|`SCREEN`<br>(e.g. 65)|`screeens/midground/`|❌
Mask|480x360 pixels|`MASK_NAME`mask`SCREEN`<br>(e.g. ashmask65)|`screens/masks/`|✔️
Foreground|480x360 pixels|fg`SCREEN`<br>(e.g. fg65)|`screens/foreground/`|❌

## Next up

You've learned all for what it takes to make a packed screen, let's learn [how to make props]({{ site.baseurl }}/level-making/props)!