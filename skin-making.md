---
layout: default
title: Skin Making
nav_order: 8
last_modified_date: 2023-02-21 16:51
---

# Skin Making
{: .no_toc }

**everything** you need to know for your skin or set!<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Setting the environment to make any skin

First of all, open the software of your choice and set two layers.

1. The first (or top) layer should be the layer you use for drawing your skin,
2. the second (or bottom) layer should be the [**base file**]({{site.baseurl}}/images/level-making/king/base.png){:target="_blank"}; this second layer will help you building a fully working skin.

> A simple trick while making a skin is setting the second (or bottom) layer to a lower opacity, like 50%.
{: .note }

### Once satisfied with the texture(s)

1. Disable or hide the last (bottom) layer. 
2. > **If you are doing a single skin**, export the image file but save the filename somewhere since you will need it later.
   {: .highlight }

   > Otherwise, **if you are doing a skin set** save them with the following format and save the filenames somewhere since you will need them later.
   ```md
   (YOUR COLLECTION NAME)_(YOUR ITEM NAME).png
   ```
   > This format is not mandatory but can help you identify the items inside your set, in case you need to update something.
   {: .highlight }

## Why does Jump King need a configuration file?

In order for get the basic data about your skin or set, Jump King (and in the past with JumpKingPlus) uses a configuration file.

This configuration file contains your skin or set: 
- the boolean that tells you **if the skin/set is enabled**
- one (if a skin) or multiple (if a set) **filenames** of your packed images
- one (if a skin) or multiple (if a set) **item** you want to override

## Single skins

The configuration in sigle skins is called `cosmetic_settings.xml`.<br>Open the file and proceed with the settings below. A single skin's configuration file looks like this:

```xml
<?xml version="1.0"?>
<ReskinSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <skin>Cap</skin>
  <name>Propeller Hat</name>
  <enabled>false</enabled>
</ReskinSettings>
```

### Setting everything (using Worldsmith)
🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Setting the skin's item (without Worldsmith)

1. Search for "skin" in your XML file.
   You should find something like this:
   ```xml
   <skin>YOUR_SKIN_HERE</skin>
   ```
2. Replace `YOUR_SKIN_HERE` with the [**wearable item**]({{site.baseurl}}/api/items){:target="_blank"} of your choice.
3. Done!

### Setting the skin's filename (without Worldsmith)

1. Search for "name" in your XML file.
   You should find something like this:
   ```xml
   <name>YOUR_NAME_HERE</name>
   ```
2. Replace `YOUR_NAME_HERE` with the packed file name of your skin (no extension in the name).
3. Done!

## Skin sets

The configuration in skin sets is called `set_settings.xml`.<br>Open the file and proceed with the settings below. A skin set's configuration file looks like this:

```xml
<?xml version="1.0"?>
<SetSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <enabled>false</enabled>
  <Reskins>
    <Reskin>
      <skin>Crown</skin>
      <name>RedHorns</name>
    </Reskin>
    <Reskin>
      <skin>NULL</skin>
      <name>RedBaseSkin</name>
    </Reskin>
  </Reskins>
</SetSettings>
```

### Setting everything (using Worldsmith)
🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Adding a new skin to the set (without Worldsmith)

1. Search for "Reskins" in your XML file.
2. Add the following snippet below the opening tag of `Reskins` in a new line:
   ```xml
    <Reskin>
      <skin>YOUR_SKIN_HERE</skin>
      <name>YOUR_FILENAME_HERE</name>
    </Reskin>
   ```
3. Replace `YOUR_SKIN_HERE` with a [**wearable item**]({{site.baseurl}}/api/items){:target="_blank"} of your choice.
4. Replace `YOUR_FILENAME_HERE` with the file name of your packed XNB file for your skin.
5. Repeat step 2 for each skins you want to add. 
6. Done!

### Removing a skin from the set (without Worldsmith)

1. Search for "Reskins" in your XML file and find the [item that you want to remove]({{site.baseurl}}/api/items){:target="_blank"}.
2. Remove the whole `Reskin` tag that contains `skin` as your unwanted item.
3. Done!

## Testing

> Testing your skin is currently not available since you can see your skin in the pixel art/image editor of your choice.
{: .highlight }

<!-- **WARNING**:<br>The following reskins and collections won't work in custom levels:
- Base reskin
- Collection that contains a base skin -->

## Next up

You are set (pun not intended)!<br>Give a read on how to [**publish your single set or skin set**]({{site.baseurl}}/publishing)!