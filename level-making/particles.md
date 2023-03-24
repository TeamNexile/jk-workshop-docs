---
layout: default
title: Particles
parent: Level Making
nav_order: 10
last_modified_date: 2023-03-24 13:32
---

# Particles folder
{: .no_toc }

contains the details about the particles on screen<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The particles folder includes two .xml configuration files which are:
- `weather.xml`
- `snow_settings.xml`

## Weather

The weather is a particle effect that can help to create depth in your level.

> We are planning to change the weather to make it more customizable in the future. As of now, it works in the same way JumpKingPlus did.
{: .new }

<!-- ### Adding/removing weather (with Worldsmith) 

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

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

### Custom sized weather

To crop a particle on a screen, you need to use masks. Check [***Masks* in the Screen section**]({{site.baseurl}}/level-making/screens/#masks) on its usage.

## Snow types

The snow hitbox/mechanic can let you decide which type of snow particles you would like to have in a particular area.

> This is an optional, therefore if you don't want a different snow type you can leave it as is and it will default to no particles used.
{: .highlight }

<!-- ### Adding/removing a snow particle (with Worldsmith) 

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Adding/removing a snow particle 

To add a snow particle:

1. Write down the first and last screen where you want your particle to present.
2. Decide [__what type of snow particle you want__]({{site.baseurl}}/api/particles){: target="_blank"}.
3. Copy the following snippet:
   ```xml
   <SpriteSpan>
    <start>YOUR_FIRST_SCREEN</start>
    <end>YOUR_LAST_SCREEN</end>
    <sprite>YOUR_SNOW_PARTICLE_TYPE</sprite>
   </SpriteSpan>
   ```
4. Navigate to `particles` and open `snow_settings.xml`.
5. If this is your first time dealing with snow particles, remove the already existing `SpriteSpan`s.
6. Paste in a new line below the `sprite_spans` opening tag.
7. Replace `YOUR_FIRST_SCREEN` with your first screen.
8. Replace `YOUR_LAST_SCREEN` with your last screen.
9. Replace `YOUR_SNOW_PARTICLE_TYPE` with the value of the particle chosen.

To remove a snow particle:

1. Find the screen(s) where the snow particle is present.
2. Navigate to `particles` and open `snow_settings.xml`.
3. Find the `SpriteSpan` that contains your screens (between start and end) and delete it.
4. If your `sprite_spans` is without any `SpriteSpan`, add the following SpriteSpan:
   ```xml
   <SpriteSpan>
      <start>0</start>
      <end>0</end>
      <sprite>0</sprite>
    </SpriteSpan>
    ```

## Next up

You have gone through all steps for level making. If you want suggestions from the community, read [**Tips & Tricks**]({{site.baseurl}}/level-making/tips). For publishing a finished level, go to [**Publishing**]({{site.baseurl}}/publishing).