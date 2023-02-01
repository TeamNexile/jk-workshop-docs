---
layout: default
title: Blocks
parent: Level Making
nav_order: 2
last_modified_date: 2023-02-01 15:19
---

<style>
  .main-content h3 {
    margin-top: 3rem;
  }

  #markdown-toc input[type="color"] {
    height: 1rem;
    vertical-align: middle;
  }

  input[type="color"] {
    padding: 0;
    width: 2rem;
    height: 2rem;
    margin-right: .75rem;
    vertical-align: -.5rem;
    cursor: pointer;
  }

  table.vertical thead th {
    writing-mode: vertical-lr;
    text-orientation: sideways;
    padding: 0.25rem;
    font-weight: 600;
    vertical-align: bottom;
  }

  table.vertical thead th:first-child {
    writing-mode: unset;
    text-orientation: unset;
  }

  table.vertical th,
  table.vertical td {
    min-width: 0;
  }
</style>

# Block types
{: .no_toc }

every color defines a block, a mechanic and more!<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Blocks for starters

If you are just getting started creating levels, you should learn what each block is cabable of. These are the most simple blocks, since they dont have any implication or real big understanding behind them.
You could call hese blocks, the foundation for Jump King levels.

> Pro-tip!
> 
>If you are starting out, you should take some time tinkering with each, see what you can do with it!
{: .note-title }

By clicking or hovering the color box you can see the RGB color that you will need to use in the hitbox.

### <input type="color" title="RGB(0,0,0)" value="#000000">Solid block

The solid block is a normal block you can stand on.

- It is solid,
- you can walk on it [^1],
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(255,0,0)" value="#FF0000">Slope block

The slope block is the block used for slopes. It needs two adjacent any-solid or fake blocks to exist. These two
adjacent blocks needs to be:
1. one on the left or right side of the slope
2. one on the top or bottom side of the slope

- It is usually solid [^4],
- you can't walk on it,
- you will slide on it no matter what,
- it can affect your direction [^3].

### <input type="color" title="RGB(128,128,128)" value="#808080">Fake block

The fake block is a block that is not solid and the sole purpose is to create a slope without surrounding blocks.

- It is not solid,
- you can't walk on it,
- you can't slide on it [^5],
- it can affect your direction [^3].

### <input type="color" title="RGB(0,255,255)" value="#00FFFF">Ice block

The ice block is a solid block that will make the player slide if it's standing on it.

- It is solid,
- you can walk on it [^1],
- you will slide on it no matter what,
- it can affect your direction [^3].


### <input type="color" title="RGB(255,255,0)" value="#FFFF00">Snow block

The snow block is a solid block that will make the player stand in one position, needs at least 7 frames to jump.

- It is solid,
- you can't walk on it,
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(255,255,128)" value="#FFFF80">Thin snow block

The snow block is a solid block that will make the player stand in one position, you can jump any jump charge.

- It is solid,
- you can't walk on it,
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(255,106,0)" value="#FF6A00">Sand block

The sand block, is pretty much what quicksand is, by landing on it you will immediately sink.

- It is solid,
- you can walk on it [^1],
- you can't slide on it,
- it affects your direction (you will sink down).

### <input type="color" title="RGB(0,255,0)" value="#00FF00">Wind block

The wind block, if present on a screen, it will activate an infinite loop where it will slowly push the player left and
right. The wind polarity changes direction every 5 seconds.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

### <input type="color" title="RGB(255,255,255)" value="#FFFFFF">No wind block

The no wind block does exactly what it sounds like. It's called "no wind" block because it's main use was to stop the
wind, but can be used for water and low gravity too!

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it cancels out the wind, water and low gravity (not affecting your direction).

### <input type="color" title="RGB(0,170,170)" value="#00AAAA">Water block

The water block is an area block that slows you down.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (velocity, gravity and jump charge).

### <input type="color" title="RGB(128,255,255)" value="#80FFFF">Low gravity block

The low gravity block is an area block that slows you down but amplifies your jump range.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (velocity, gravity and jump curve).

---

## Blocks for intermediate users

These aren't inherently hard for starters, but it's better to not put too much at once especially when you have over ten blocks to start with, it can start to be messy... once you feel more confident with the starter blocks, you should check out the following blocks.

### <input type="color" title="RGB(182,255,0)" value="#B6FF00">Quark block

The quark block is a block that rounds the player to the closer in-game pixel (8 pixel distance) the player's Y position
to make falls less inconsistent.

In order to get the full potential of a quark block:
1. It has to be used when player is in full falling velocity
2. It has to be used on one of the side of the screen

![Usage](https://media.discordapp.net/attachments/623779998494490624/782275174916685864/unknown.png)
(thanks to Erkstock for the image and the explanation!)

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (player Y position).

### <input type="color" title="RGB(1,0,255)" value="#0100FF"><input type="color" title="RGB(255,0,255)" value="#FF00FF">Teleport block

The teleport block has a range of values that goes from 1 to 255, if placed on a screen, when the player crosses the
side of the screen, it teleports the player to the specific screen number given by the red channel number.

> For example if on the screen you place one teleport block colored RGB(9,0,255), once the player walks/jumps/falls in
either side of the screens, it will get teleported to the 9th screen of your hitbox file.

> By default works both ways, adding another teleport to the other side of the screen will allow you to have two
different side teleports per screen.
{: .disclaimer }

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (player Y position).

### <input type="color" title="RGB(192,255,0)" value="#C0FF00"><input type="color" title="RGB(207,255,0)" value="#CFFF00">Wind gradient block

The wind gradient block has a range of 16 intesities of [wind](#wind-block), from 12.5% or RGB(192,255,0) to 200% or
RGB(207,255,0) of the original strength of the wind.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

### <input type="color" title="RGB(208,255,0)" value="#D0FF00"><input type="color" title="RGB(223,255,0)" value="#DFFF00">Left one-way wind gradients

The wind gradient block has a range of 16 intesities of the left one-way wind, from 12.5% or RGB(208,255,0) to 200% or
RGB(223,255,0) of the original strength of the wind. The one-way wind will never change direction.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

### <input type="color" title="RGB(224,255,0)" value="#E0FF00"><input type="color" title="RGB(239,255,0)" value="#EFFF00">Right one-way wind gradients

The wind gradient block has a range of 16 intesities of the right one-way wind, from 12.5% or RGB(208,255,0) to 200% or
RGB(223,255,0) of the original strength of the wind. The one-way wind will never change direction.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

---

## Blocks for experts only

Once you've mastered all the previous blocks, you should learn the two missing.

> You should follow the following blocks only if you really know what you are doing!
{: .warning }

### <input type="color" title="RGB(65,65,65)" value="#414141"><input type="color" title="RGB(68,65,65)" value="#444141">Semi-solid block

The semi-solid block is a solid block that is solid only in one side.

Solid side|Red channel value
Top|65
Right|66
Bottom|67
Left|68

- It is solid [^6],
- you can walk on it [^1],
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(0,0,75)" value="#00004B"><input type="color" title="RGB(60,45,75)" value="#3C2D4B">Warp block

The warp block warps the player into the coordinates given by the Red and Green channel.

To get warp color working:
1. Use the test mode with Relative Coordinates,
2. write down the coordinates you want to teleport to,
3. divide the number by 8, round if necessary.
4. Use the new numbers for the Red and Green value.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

## Blocks recap

Remembering all blocks can be hard

<table class="vertical">
  <thead>
    <tr>
      <th>Title</th>
      <th>Solid</th>
      <th>Slope</th>
      <th>Fake</th>
      <th>Ice</th>
      <th>Snow and thin snow</th>
      <th>Sand</th>
      <th>Wind</th>
      <th>No wind</th>
      <th>Water</th>
      <th>Low gravity</th>
      <th>Quark</th>
      <th>Teleport</th>
      <th>Wind gradient</th>
      <th>One-way wind gradient</th>
      <th>Semi-solid</th>
      <th>Warp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>is solid?</td>
      <td class="label-green">✔</td>
      <td class="label-yellow"><a href="#fn:4">~<sup role="doc-noteref">4</sup></a></td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-yellow"><a href="#fn:6">~<sup role="doc-noteref">6</sup></a></td>
      <td class="label-red">✖</td>
    </tr>
    <tr>
      <td>walkable? <sup role="doc-noteref"><a href="#fn:1">1</a></sup></td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
    </tr>
    <tr>
      <td>slideable? <sup role="doc-noteref"><a href="#fn:2">2</a></sup></td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-yellow"><a href="#fn:5">~<sup role="doc-noteref">5</sup></a></td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
    </tr>
    <tr>
      <td>affects player?</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
    </tr>
    <tr>
      <td>affected by other blocks?</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
    </tr>
  </tbody>
</table>

### Notes

[^1]: You can walk on it until you are not wearing Giant Boots.
[^2]: You can slide on it if you are wearing Snake Ring.
[^3]: It can affect your position if a type of wind, water or low gravity is in the screen, this can be avoided with the use of the [no wind block](#no-wind-block).
[^4]: The slope can be not solid if the one or all adjacent blocks are missing.
[^5]: You can't slide on a fake block unless it's connected to a slope block.
[^6]: The one-way block is solid only on one side, depending on the color chosen.