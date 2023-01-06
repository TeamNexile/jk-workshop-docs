---
layout: default
title: Hitboxes
parent: Level Making
nav_order: 2
last_modified_date: 2021-12-19 14:05
---

# Hitbox file

is a PNG image with alpha channel (or **Texture2D**) that is used to determine the custom level gameplay.
{: .fs-6 .fw-300 }

The hitbox file, called `level.xnb`, has the size of **780x585 pixels**, every screen is ordered by column starting from top to bottom which means <u>every screen has 60x45 pixels</u>.<!-- more -->

![Hitbox Example](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/level.png)


## Block color table

Jump King uses a specific color to define what a block is inside of this file.

<table>
  <thead>
    <tr>
      <th>block</th>
      <th>description</th>
      <th>usage</th>
      <th>color</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Solid</td>
      <td>A normal block you can stand on</td>
      <td></td>
      <td><div class="rectangle" style="background:black;"></div>RGB(0,0,0)</td>
    </tr>
    <tr>
      <td>Slope</td>
      <td>The player will slide standing on it</td>
      <td>Needs two adjacent blocks</td>
      <td><div class="rectangle" style="background:red;"></div>RGB(255,0,0)</td>
    </tr>
    <tr>
      <td>Fake</td>
      <td>The player will fall through it</td>
      <td>Used also for slopes - alters wind, water and low gravity functionalities</td>
      <td><div class="rectangle" style="background:rgb(128,128,128);"></div>RGB(128,128,128)</td>
    </tr>
    <tr>
      <td>Ice</td>
      <td>The player will slide on it but can still stand on it</td>
      <td></td>
      <td><div class="rectangle" style="background:rgb(0,255,255);"></div>RGB(0,255,255)</td>
    </tr>
    <tr>
      <td>Snow</td>
      <td>The player cannot walk on it, but can still jump with enough power</td>
      <td>Snake Ring bypasses it</td>
      <td><div class="rectangle" style="background:rgb(255,255,0);"></div>RGB(255,255,0)</td>
    </tr>
    <tr>
      <td>Wind</td>
      <td>If placed on a screen, it will push the player slowly either left or right</td>
      <td>The wind polarity reverses every 5 seconds</td>
      <td><div class="rectangle" style="background:rgb(0,255,0);"></div>RGB(0,255,0)</td>
    </tr>
    <tr>
      <td>Sand</td>
      <td>The player will slowly fall through the block, while jumping and walking is still possible</td>
      <td></td>
      <td><div class="rectangle" style="background:rgb(255,106,0);"></div>RGB(255,106,0)</td>
    </tr>
    <tr>
      <td>No Wind</td>
      <td>The player will fall through it</td>
      <td>Alters wind, water and low gravity functionalities</td>
      <td><div class="rectangle" style="background:white;"></div>RGB(255,255,255)</td>
    </tr>
    <tr>
      <td>Water</td>
      <td>Velocity and gravity is halved</td>
      <td></td>
      <td><div class="rectangle" style="background:rgb(0,170,170);"></div>RGB(0,170,170)</td>
    </tr>
    <tr>
      <td>Quark</td>
      <td colspan="2"><a href="#quark-block">read in detail</a></td>
      <td><div class="rectangle" style="background:rgb(182,255,0);"></div>RGB(182,255,0)</td>
    </tr>
    <tr>
      <td>Teleport</td>
      <td>If placed on a screen, it teleports the player to a specific screen using the <b>RED</b> of the RGB scale as the screen number</td>
      <td>Works both left and right side of the screen</td>
      <td><div class="rectangle-gradient" style="background-image: linear-gradient(to right, rgb(1,0,255), rgb(255,0,255));"></div>RGB(1,0,255) to RGB(255,0,255)</td>
    </tr>
    <hr>
    <tr class="exclusive">
      <td>Low gravity</td>
      <td>Velocity and gravity is between water and normal, the Y distance is slightly higher</td>
      <td>(fixed all problems related with solid platforms in v1.3.1)</td>
      <td><div class="rectangle" style="background:rgb(128,255,255);"></div>RGB(128,255,255)</td>
    </tr>
    <tr class="exclusive">
      <td>Wind gradients</td>
      <td>16 values that determines the intensity of the wind</td>
      <td>From 12.5% to 200% of the original wind strength based on the gradient</td>
      <td><div class="rectangle-gradient" style="background-image: linear-gradient(to right, rgb(192,255,0), rgb(207,255,0));"></div>RGB(192,255,0) to RGB(207,255,0)</td>
    </tr>
    <tr class="exclusive">
      <td>One-way wind gradients (LEFT)</td>
      <td>16 values that determines the intensity of the wind, the wind will never change direction.</td>
      <td>From 12.5% to 200% of the original wind strength based on the gradient</td>
      <td><div class="rectangle-gradient" style="background-image: linear-gradient(to right, rgb(208,255,0), rgb(223,255,0));"></div>RGB(208,255,0) to RGB(223,255,0)</td>
    </tr>
    <tr class="exclusive">
      <td>One-way wind gradients (RIGHT)</td>
      <td>16 values that determines the intensity of the wind, the wind will never change direction.</td>
      <td>From 12.5% to 200% of the original wind strength based on the gradient</td>
      <td><div class="rectangle-gradient" style="background-image: linear-gradient(to right, rgb(224,255,0), rgb(239,255,0));"></div>RGB(224,255,0) to RGB(239,255,0)</td>
    </tr>
    <tr class="exclusive">
      <td>Semi-solid</td>
      <td>Block that is only solid on one side.</td>
      <td>Solid from Top (R: 65), Right (R: 66), Bottom (R: 67), Left (R: 68)</td>
      <td><div class="rectangle-gradient" style="background-image: linear-gradient(to right, rgb(65,65,65), rgb(68,65,65));"></div>RGB(65,65,65) to RGB(68,65,65)</td>
    </tr>
    <tr class="exclusive">
      <td>Warp</td>
      <td>(Like Teleport but on the same screen)</td>
      <td>The red channel equals to the X location on the screen, the green channel equals to the Y location on the screen.</td>
      <td><div class="rectangle-gradient" style="background-image: linear-gradient(to right, rgb(0,0,75), rgb(60,45,75));"></div>RGB(0,0,75) to RGB(60,45,75)</td>
    </tr>
  </tbody>
</table>

If the red channel is still a concept you don't understand, see it as the first RGB value (Red Green Blue) which is globally known on all image modification program.

### Quark block
is a block that rounds the player to the closer in-game pixel (8 pixel distance) the player's Y position to make falls less inconsistent.

In order to get the full potential of a quark block:
- It has to be used when player is in full falling velocity
- It has to be used on one of the side of the screen

#### Usage
![Usage](https://media.discordapp.net/attachments/623779998494490624/782275174916685864/unknown.png)
(thanks to Erkstock for the image and the explaination!)

<br>

## JumpKingPlus' blocks compatibility table
<table class="overflow-x">
  <thead>
    <tr>
      <th style="position: sticky;left: 0;">block</th>
      <td>JK+ v1.1.0 or older</td>
      <td>JK+ v1.2.0 to v1.3.0</td>
      <td>JK+ v1.3.1</td>
      <td>JK+ v1.4.0 to v1.6.1</td>
      <td>JK+ v1.7.0</td>
      <td>JK+ v1.7.1 or newer</td>
    </tr>
  </thead>
  <tbody>
    <!-- <tr>
      <td>Solid</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Slope</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Fake</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Ice</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Snow</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Wind</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Sand</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Wind</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>No Wind</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Water</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Quark</td>
      <td colspan="5">&check; (from vanilla game)</td>
    </tr>
    <tr>
      <td>Teleport</td>s
      <td colspan="5">&check; (from vanilla game)</td>
    </tr> -->
    <tr>
      <th>Low gravity</th>
      <td>&cross;</td>
      <td>? <a href="#block1">*¹</a></td>
      <td>&check;</td>
      <td>&check;</td>
      <td>&check;</td>
      <td>&check;</td>
    </tr>
    <tr>
      <th>Wind gradients</th>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&check;</td>
      <td>&check;</td>
      <td>&check;</td>
    </tr>
    <tr>
      <th>One-way wind gradients</th>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&check;</td>
      <td>&check;</td>
      <td>&check;</td>
    </tr>
    <tr>
      <th>Warp</th>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&check;</td>
      <td>&check;</td>
    </tr>
    <tr>
      <th>Semi-solid</th>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&check;</td>
      <td>&check;</td>
    </tr>
    <tr>
      <th>Double teleport</th>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&cross;</td>
      <td>&check;</td>
    </tr>
  </tbody>
</table>

> \*¹ - From version v1.2.0 to v1.3.0, there was a [**bug**](https://twitter.com/i/status/1358425873825734656) related to low gravity where the player standing on solid blocks would *graphically* jump. Later fixed on v1.3.1. 
{: #block1 }