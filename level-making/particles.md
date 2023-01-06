---
layout: default
title: Particles
parent: Level Making
nav_order: 10
last_modified_date: 2021-12-19 14:05
---

# Particles folder

contains the details about the particles on screen.<!-- more -->
{: .fs-6 .fw-300 }

The particles folder should include two .xml configuration file which are:
- weather.xml (which sets the weather)
- snow_settings.xml (experimental)

## Weather configuration
The weather configuration `weather.xml` contains a list of pre-existing particles that can be used for your level. Inside `<weathers>`, you will find multiple instances of the `<Weather>` tag.

### Weather
<p class="do-i-need-it">required</p>

contains the name of the weather, fps and screens it is in.

|tag|description|
|---|---|
|`<name>`|Name of the weather (**leave as default**)|
|`<fps>`|Frames per second|
|`<screens>`|Contains multiple instances of int (screen numbers)|
|`<int>`|Screen number|

To add a particle effect to a screen:
1. Edit the `weather.xml` file
2. At the `<Weather>` wanted, identifiable by the name tag being snow, snow_slow, etc. Inside the `<screens>` tag add a new int tag with the screen number you'd like the particles to be present.

For example, on screen 5 there will be the particle effect *snow*.

```xml 
<Weather>
  <name>snow</name>
  <fps>12</fps>
  <screens>
    <int>5</int>
  </screens>
</Weather>
```

To crop a particle on a screen, you need to use masks. Check [***Masks* in the Screen section**](../screens/#masks) on its usage.

<br>

## Snow settings
is a setting still in development.

~~This needs to be configured, if the `snow` particle is used.~~

There's no need for it to be configured, you should leave it as the example below:

```xml
<?xml version="1.0"?>
<SnowSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <sprite_spans>

    <SpriteSpan>
      <start>0</start>
      <end>0</end>
      <sprite>0</sprite>
    </SpriteSpan>
	
  </sprite_spans>
</SnowSettings>
```