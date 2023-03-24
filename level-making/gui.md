---
layout: default
title: GUI
parent: Level Making
nav_order: 5
last_modified_date: 2023-03-24 13:32
---

# Gui folder
{: .no_toc }

list of locations and the *earthquake* effect<!-- more -->
{: .fs-6 .fw-300 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

> 🚧 If you do not understand how the text works in the example below. Go back to [File Types]({{site.baseurl}}/getting-started/filetypes) and read up on XML. 🏗
{: .disclaimer }

## Locations

The locations (also known as areas) are a group of screens that usually represent a specific gameplay or style. Each location have a name, start, end, introduction trigger screen.

![Location example]({{site.baseurl}}/images/level-making/location.png)

<!-- ### Adding/replacing/removing a location (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Adding a location

To add a location:

1. Write down the screen numbers that you want to be part on a location.
2. Nagivate to `gui` and open `location_settings.xml`.
3. If this is the first time, should see something like this:
    ```xml
    <?xml version="1.0"?>
    <LocationSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <locations>

            <Location>
                <start>1</start>
                <end>1</end>
                <unlock>1</unlock>
                <name>YOUR_LOCATION_NAME</name>
            </Location>

        </locations>
    </LocationSettings>
    ```
    > **If this is not the first time**, paste the following snippet below the closing tag of the latest location.
    ```xml
        <Location>
            <start>1</start>
            <end>1</end>
            <unlock>1</unlock>
            <name>YOUR_LOCATION_NAME</name>
        </Location>
    ```
4. Replace the `start` value with the first screen of your location.
5. Replace the `unlock` value with the screen that you want to trigger the location title to show up.
    > If you don't  want the location title to show up, simply put `0` as a value.
    {: .highlight }

6. Replace the `end` value with the last screen of your location.
7. Replace `YOUR_LOCATION_NAME` with the name of your new location.

> Since this is supposed to be a linear location grouping method, if you trigger a later present location, the middle locations won't be triggered.
{: .disclaimer }

> Make sure your location always ends before starting another one! This can cause problems later on if ignored.
{: .warning }

### Removing a location

To remove a location:

1. Find what is the name of the location you are looking to remove.
2. Nagivate to `gui` and open `location_settings.xml`.
3. Remove the entire `Location` tag where the name equals to the location you want to remove.


## Earthquake effect

This allows you to replicate the earthquake effect used by Jump King in correspondence of the towers. This is effect consists of moving the screen left and right by one pixel.

<!-- ### Adding/replacing/removing the earthquake effect on a screen (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Adding and removing the earthquake effect on a screen

To add the earthquake effect on a screen:

1. Write down the screen number(s) where you want to have the earthquake effect.
2. Nagivate to `gui` and open `earthquake_settings.xml`.
3. > By default there's only one screen set to 0, so it will never trigger. Like the following example:
    ```xml
    <?xml version="1.0"?>
        <EarthquakeSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
            <screens>
                <int>0</int>
            </screens>
        </EarthquakeSettings>
    ```
    {: .highlight }
   
   To add earthquake effects, you will need to paste the following and replace `SCREEN_NUMBER` with each screen number.
    ```xml
    <int>SCREEN_NUMBER</int>
    ```

To remove an earthquake effect on a screen:

1. Find the screen that you want to remove the effect.
2. write down the screen number.
3. Nagivate to `gui` and open `earthquake_settings.xml`.
4. Remove the entire line where the screen number is present.

## Next up

Go to [**props**]({{ site.baseurl }}/level-making/props).