---
layout: default
title: Screen
parent: Modding
nav_order: 4
last_modified_date: 2021-12-19 14:05
---

# Screens folder
{: .no_toc }

contains textures such as background, foreground, midground, scrolling images and masks.<!-- more -->
{: .fs-6 .fw-300 }

All of the layers of a screen can be merged to make a result like this (*without counting the hidden wall because that's a type of prop*):

![Example Image](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/final.jpg)

Every layer has its own name, format and folder.<br>The following list will go from back to front.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Background
At the lowest ground there's the background.
The background is usually used for **skies or gradients** to put on the back end of screens.<br>
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