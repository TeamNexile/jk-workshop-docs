---
layout: default
title: Tileset Making
has_children: false
has_toc: false
nav_order: 9
last_modified_date: 2024-08-30 17:42
---

# Tileset Making
{: .no_toc }

**everything** you need to know to make a tileset.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Introduction

Tilesets follow the ratio hitbox-to-screen which is 1 to 8; meaning one pixel in hitboxes equals to 8 pixels in screen detail (background, midground or foreground), therefore each tile consists of 8 by 8 pixels. [Reference to hitboxes ratio]({{site.baseurl}}/level-making/hitboxes/#common-similarities).

## Editing the tileset texture

To edit the tileset texture:

1. Open Worldsmith through Steam and open your tileset project from the recents or favorites list.

    > If you can't find your project in your recents/favorites list and you know where it's placed in your drive, click on **Load an existing project** and follow the instructions on screen.
    {: .note }

2. Once clicked, you'll see the title of your tileset in the header of Worldsmith, this means your project has been opened in Worldsmith. Some pages will show up on the sidebar now like in the image below.

    ![Opened project]({{ site.baseurl }}/images/tileset-making/worldsmith_selected_project.png)

3. From the left sidebar, enlarge the sidebar with the expand button and click on **Tileset Manager** or click on the second item below the tileset icon (*resembling a table with a cog*).

    ![Item details button]({{ site.baseurl }}/images/tileset-making/worldsmith_click_tileset_manager.png)

2. Click on the "*Open*" button with a folder icon on top-right.

    ![Open folder button]({{ site.baseurl }}/images/tileset-making/worldsmith_open_folder.png)

This will open your file explorer selecting the tileset. Here you can right-click the tileset > `Open with` and select your pixelart or photo-editing program of preference.

![Opened folder]({{ site.baseurl }}/images/tileset-making/worldsmith_open_folder_success.png)

## Tile tags

A tileset can have as many tiles as necessary, so it makes sense to have a filter between the tiles of one or multiple tilesets.

{: .warning }
> The tile tags are tied to the column and row of a certain tile.
> 
> Moving the tile settings to a new tile is currently not implemented, so you will need to delete and write the tags again if you move your tiles.

### Nomenclature for tile tags

Since anyone can create tile tags, its easy to have different tags that group the same category; so here as follows there are some guidelines you can use to share the best experience between you and the people that have subscribed to your tileset.

1.  **Use English** as the **language** for your tags.
    <br>Not everyone will understand your language, but most people will understand English.

2.  Make sure the **item tag is not ambiguous**. So future you and other people can easily understand it.
    <br>Instead of using something like `Detail` as a tag, which is generic and doesn't tell at first glance, specify it a bit better like `Foliage`.

2.  **Capitalize the first word only**, even if you have a tag that contains multiple words.
    <br>Use `Kitchen appliance` instead of `Kitchen Appliance`, `kitchen appliance` or `KITCHEN APPLIANCE`.

3.  **Use multiple tags**, if your tag count is growing big.
    <br>For example, if you have 14 tiles in your category `Nature`, might be a good to have a subcategory `Tree` and `Flower`. Or viceversa, with another supercategory.

Here's an example that follows the guidelines above:

![Example]({{site.baseurl}}/images/tileset-making/example_tile_tags.png)

### Adding a tile tag

To add a tag on a tile:

1. Click on the tile you are looking to add the tag on.
<br>Double click if the tile has not yet created.

    ![Click on tile]({{site.baseurl}}/images/tileset-making/worldsmith_click_tile.png)

2. Both on the sidebar and on the tile preview, you should see which tile is selected. Use your mouse or cursor to reselect the tile if it isn't the right one.

    ![Tile selected]({{site.baseurl}}/images/tileset-making/worldsmith_clicked_tile.png)

3. Once selected the right tile, click on the "+" button on the bottom right corner of the tile in the sidebar.

    ![Sidebar click button]({{site.baseurl}}/images/tileset-making/worldsmith_add_tag.png)

5. A popup will prompt you to type the tag type. Simply type the tag and click "*Add Tag*" once done.

You have successfully added a tag on your tile!

![Tile tag added]({{site.baseurl}}/images/tileset-making/worldsmith_tag_success.png)

### Removing a tile tag

To remove a tag on a tile:

 1. Click on the tile you are looking to remove the tag from.
 2. Click on the tag to remove it.

 Done! You have removed a tag from a tile.

## Next up

Once you are done with your tileset, read [**Publishing**]({{site.baseurl}}/publishing).