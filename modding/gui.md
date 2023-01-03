---
layout: default
title: GUI
parent: Modding
nav_order: 7
last_modified_date: 2021-12-19 14:05
---

# Gui folder
{: .no_toc }

contains the list of locations and the *earthquake* effect settings.<!-- more -->
{: .fs-6 .fw-300 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Locations settings
is a configuration file used both by the game and the Discord Rich Presence that contains the list of locations in the custom level. This can be changed editing the `gui/location_settings.xml` file.

### Locations
<p class="do-i-need-it">required</p>

contains every location. Locations is an array of `<Location>`, an array means that there could possibly be multiple `<Location>` tags.

#### Location
contains every detail about the single location such as:

|tag|description|type|required|
|`<start>`|Screen number where location starts|int|Yes|
|`<end>`|Screen number where location ends|int|Yes|
|`<unlock>`|Screen number where location name pops up|int|Yes|
|`<name>`|Location name|string|Yes|
|`<ignore>`|Disables percentage for a location (from <span class="badge-pill">v1.7.1</span>)|bool|No|

If you've done it correctly, it should end up something like this:

<script src="https://gist.github.com/Phoenixx19/611fccf2f09494f19c5b2b031a94e467.js"></script>

<br>

## Earthquake effect

Implemented from <span class="badge-pill">**v1.4.0**</span>, this permits to disable/enable the earthquake effect used by Jump King in correspondence of the towers. This is effect consists of moving the screen left and right by one pixel. The earthquake effect can be changed using the `gui/earthquake_settings.xml` file.

By default there's only one screen set to 0, so it will never trigger. In case you want to use it, you will need to name every screen number with:
```xml
<int>SCREEN_NUMBER</int>
```

It should look like the following example: 

<script src="https://gist.github.com/Phoenixx19/1c52c7517faf5b92ffa2367b3082b5c9.js"></script>