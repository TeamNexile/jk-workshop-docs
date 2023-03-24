---
layout: default
title: World Items
grand_parent: Level Making
parent: Props
nav_order: 2
last_modified_date: 2023-03-24 13:32
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

<!-- ## Adding/replacing/removing a hidden wall (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

## Adding a world item


1. Make sure the [item]({{site.baseurl}}/api/items){: target="_blank"} you want to use can be a world item.
2. Choose where you would like to have the world item in-game, writing down the screen number, X and Y positions.
   
   ![Worlditem before]({{site.baseurl}}/images/level-making/props/worlditem_before_example.png)
3. Open the worlditems xml configuration file located in `props/worlditems`.
4. Copy the snippet below:
   ```xml
        <WorldItemState>
            <item>YOUR_ITEM_NAME</item>
            <screen>YOUR_WORLDITEM_SCREEN</screen>
            <_x>YOUR_WORLDITEM_X_POSITION</_x>
            <_y>YOUR_WORLDITEM_Y_POSITION</_y>
        </WorldItemState>
   ```
5. Paste it below the closing tag of an already existing `WorldItemState` or below the `items` tag.
6. Replace `YOUR_ITEM_NAME` with the **Item name** in the item's list.
7. Replace `YOUR_WORLDITEM_SCREEN` with the screen of your choice.
8. Replace `YOUR_WORLDITEM_X_POSITION` and `YOUR_WORLDITEM_Y_POSITION` with their own respective <u>relative</u> value.

The world item should be now available like so:

![Worlditem after]({{site.baseurl}}/images/level-making/props/worlditem_after_example.png)

> In the following example, the item name is **Silver**. Here's a preview of my silver's count before collecting the item:
>
> ![Inventory before]({{site.baseurl}}/images/level-making/props/worlditem_inv_before_example.png)
>
> After interacting with it, the item will disappear from the world and it should:
> - spawn a **Silver** coin in your inventory if you didn't have one beforehand
> - add one **Silver** coin to the Silver coin count
>
> ![Inventory after]({{site.baseurl}}/images/level-making/props/worlditem_inv_after_example.png)
> 
> If the item wouldn't it be stackable and you already had an item present in the inventory, nothing will change in the inventory.
{: .highlight }

## Removing a world item

1. Open the worlditems xml configuration file located in `props/worlditems`.
2. Find the item you want to delete.
3. Remove the entire `WorldItemState` tag of the world item that you don't like.

## Personalizing a world item (optional)

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

[NPCs]({{site.baseurl}}/level-making/props/npcs).