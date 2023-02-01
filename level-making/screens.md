---
layout: default
title: Screen
parent: Level Making
nav_order: 4
last_modified_date: 2022-02-01 17:47
---

# Screens folder
{: .no_toc }

contains textures such as background, foreground, midground, scrolling images and masks.<!-- more -->
{: .fs-6 .fw-300 }

All of the layers of a screen can be merged to make a result like the example below (*without counting the hidden wall because that's a type of prop*). Every layer has its own name, format and folder; hover on the image below and click on the image you want to know more about!

## Image of contents
{: .no_toc .text-delta }

<div class="skewd">
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

|resolution|480x360 pixels|
|nomenclature|bg`SCREEN NUMBER`|

This size of the file should be **480x360** pixels, the name of the file should be `bg(SCREEN NUMBER).xnb`, or as an example, `bg1.xnb`.

![BG](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/background.png)

<br>

## Scrolling images

<a class="button transparent small" href="https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/scroll.xml"><ion-icon name="code-slash"></ion-icon> Example scroll.xml</a>

The scrolling texture is usually used for **clouds or birds** flying in the distance (*behind the player*).

The scrolling images are managed by an .xml file, that determines their texture, position, velocity and layer mode (see example scroll.xml above). The texture name should be the same as the name file. Which means if you created a new scrolling texture called `clouds.xnb` the name of the texture inside the scroll setting file should be `<texture>clouds</texture>`.

![Scrolling](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/scroll.png)

<br>

## Midground
Right after the scrolling images, there's the midground.
The midground is usually used for **platforms and details** that are **behind the player** (the player can go over them).
This size of the file should be **480x360** pixels, the name of the file should be `(SCREEN NUMBER).xnb`, or as an example, `1.xnb`.

![MG](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/midground.png)

<br>

## Masks
Masks (and so particles) are above the player layer-wise.
Masks can be used to give more depth to the level, some examples of masks are ash, rain and snow. The mask lets you **display the particles effect only on the blue/cyan mask you are creating**.

The animated backgrounds are stored inside the default `particles` folder, to add a particle effect [**head over the particles section**](../particles/#weather-configuration).

This size of the file should be **480x360** pixels, the name of the file should be `(MASK NAME)mask(SCREEN NUMBER).xnb`, or as an example `light_snow_bgmask1.xnb`.

![Mask](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/mask.png)

> Removing a mask inside a screen that has already a particle effect (written on `particles/weather.xml`) will display the effect on the whole screen.

<br>

## Foreground
The foreground work one layer above the masks and particles.
The foreground is used for **details that are in front of the player**, such as vines or grass.
This size of the file should be **480x360** pixels, the name of the file should be `fg(SCREEN NUMBER).xnb`, or as an example, `fg1.xnb`.

![FG](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/foreground.png)

## Screens folder recap

Let's recap the main details for the packed files you will need.

Title|Resolution|Nomenclature|Folder
---|---|---|---
Background|480x360 pixels|bg[SCREEN]<br>(e.g. bg65)|`screens/background/`
Scrolling image|any|any|`screens/scrolling/textures/`
Midground|480x360 pixels|[SCREEN]<br>(e.g. 65)|`screeens/midground/`
Mask|480x360 pixels|[MASK_NAME]mask[SCREEN]<br>(e.g. ashmask65)|`screens/masks/`
Foreground|480x360 pixels|fg[SCREEN]<br>(e.g. fg65)|`screens/foreground/`

## Next up

You've learned all for what it takes to make a packed screen, let's learn [how to make props]({{ site.baseurl }}/level-making/props)!