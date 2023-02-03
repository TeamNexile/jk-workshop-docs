---
layout: default
title: World Items
grand_parent: Level Making
parent: Props
nav_order: 2
last_modified_date: 2023-02-03 18:59
---

# World items
{: .no_toc }

are **items that the player can pick up** by triggering their hitbox<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Adding/replacing/removing a hidden wall (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

## Adding a world item (without Worldsmith)

1. Make sure your [item can be a worlditem]({{site.baseurl}}/api/items){: target="_blank"}.
2. Open the worlditems xml configuration file located in `props/worlditems`.
3. Copy the snippet below:
   ```xml
        <WorldItemState>
            <item>YOUR_ITEM_NAME</item>
            <screen>YOUR_WORLDITEM_SCREEN</screen>
            <_x>YOUR_WORLDITEM_X_POSITION</_x>
            <_y>YOUR_WORLDITEM_Y_POSITION</_y>
        </WorldItemState>
   ```
4. Paste it below the closing tag of an already existing `WorldItemState` or below the `items` tag.
5. Replace `YOUR_ITEM_NAME` with the **Item name** in the item's list.
6. Replace `YOUR_WORLDITEM_SCREEN` with the screen of your choice.
7. Replace `YOUR_WORLDITEM_X_POSITION` and `YOUR_WORLDITEM_Y_POSITION` with their own respective <u>relative</u> value.

## Removing a world item (without Worldsmith)

1. Open the worlditems xml configuration file located in `props/worlditems`.
2. Find the item you want to delete.
3. Remove the entire `WorldItemState` tag of the world item that you don't like.

## Personalizing a world item (without Worldsmith) (optional)

In the same folders where you found the worlditems xml configuration file you can find some packed XNB files. Each file corresponds to the texture of the world item.

By replacing any of these, you will change the look of your world item.

|Filename|Item|
|---|---|
|bug_note|Bug's note|
|cap|Cap|
|ghost_fragment|Ghost Fragment|
|gnome_hat|Philosopher's Hat|
|shoes_iron|Giant Boots|
|shroom|Mushroom|
|silver_coin|Silver Coin|
|tunic|Tunic|
|yellow_shoes|Yellow shoes|

## Next up

Enjoy scattering around your new world items!
Next up, [NPCs]({{site.baseurl}}/level-making/props/npcs).