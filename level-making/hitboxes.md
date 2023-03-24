---
layout: default
title: Hitboxes
parent: Level Making
nav_order: 1
last_modified_date: 2023-03-24 13:32
---

# Hitbox file
{: .no_toc }

is a PNG image with transparency that is used to determine the custom level gameplay.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Understanding the basics of hitboxes

The hitboxes are determined by the pixels that you will draw on the image file, each color has a different use and logic that can be used for plentiful of platforming or effects.

<figure class="mb-5">
   <img src="{{ site.baseurl }}/images/level-making/hitboxes.png" alt="Completion on tool">
   <figcaption class="text-grey-dk-000 text-epsilon">Blocks will be explained in the <a href="{{site.baseurl}}/level-making/blocks">Block</a> page. This is just an example of a platform.</figcaption>
</figure>

## Creating the hitboxes file

In order to have a full-functioning hitbox an image file you will need to create a file with the following details:

|Requirements|Details|
|---|---|
|File name|level|
|Resolution|**780** pixels (*width*) by **585** pixels (*height*)|
|File placement|Root of the level folder|

The hitbox file resolution needs to be right because the game needs a grid (13 columns by 13 rows) to determine the hitboxes for each screen, that means **each screen** is sized <u>60 by 45 pixels</u>.

> Therefore, that means that one pixel on the hitbox equals to 8 pixels in-game. And the total amount of possible screens is 169.

> Following this logic you can add an helper grid (with whatever tool you chose to draw hitboxes) to help you find easily the hitbox of your screen without overflowing into a new one.
{: .note }

Here's an visual example of how hitboxes work in Jump King:

![Hitbox Example](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/level.png)

> As you can see from the example, **every screen is ordered by column starting from top to bottom**.
> **Take in mind what the screen number is from the example, since this <u>will get heavily used</u> in the next chapters.**
{: .disclaimer }

## Dealing with hitboxes

<!-- ### Modifying the hitboxes (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Modifying the hitboxes

1. Open the file [you've created above](#understanding-the-basics-of-hitboxes) or unpack existing hitboxes and open it using your tool of choice.
2. Use the [**block page as a cheat sheet**]({{site.baseurl}}/level-making/blocks){:target="_blank"} or put it page aside your pixel-art program of your choice for reference (you should start with starter blocks only!).
3. Start drawing your hitboxes!
    > Don't forget to add a solid block bottom line on the first screen otherwise you will fall forever and you are basically forced to restart.
    {: .warning }
4. Once you are satisfied or you want to give it a test, save the image file.
5. Convert/Pack the image into XNB with the tool of your choice.
6. Place it in the folder of your level. If asked to replace the file, click **Yes**.
7. [Give it a test!]({{site.baseurl}}/getting-started/map-first-steps#testing).
   > If your game is already opened from testing it before, simply nagivate to the pause menu and click **Hard Update** and the new hitboxes should show up.
   {: .note }

## Disclaimer about hitboxes

Even if the details you have planned look good, what matters more is the quality and fair of your hitboxes. Please give a read to [some tricks and tips]({{site.baseurl}}/level-making/tips) from JumpKingPlus' veterans.

## Next up

Read up on [**Starter Blocks**]({{site.baseurl}}/level-making/blocks/#blocks-for-new-users) then head to [**Screens**]({{site.baseurl}}/level-making/screens/).