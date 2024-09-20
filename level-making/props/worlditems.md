---
layout: default
title: World Items
grand_parent: Level Making
parent: Props
nav_order: 2
last_modified_date: 2024-09-20 16:48
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

### Adding a world item on a screen

1. Navigate to the **Screens** page.
2. Right-click onto the canvas on the left side of your screen (where you have your level preview) and select *Add on screen...*, then *Worlditem*.

    ![Worlditem right click]({{ site.baseurl }}/images/level-making/props/worlditem_right_click.png)

3. Once clicked, a prompt will ask you to select the Worlditem that you want to add onto the current screen.

    ![Worlditem details]({{ site.baseurl }}/images/level-making/props/worlditem_prompt.png)

4. Once selected, click **Add**.<br>Your Worlditem should appear on your preview.

    ![Worlditem added successfully]({{ site.baseurl }}/images/level-making/props/worlditem_add_success.png)

### Changing/removing a world item from a screen

1. Navigate to the **Screens** page.
2. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the background you want to change/get rid of.
3. From the right side of the page, expand the **World items** tab.

    > Click on a world item or, using the left side of the page (preview), click on the world item's sprite to easily find the world item you are looking for!
    {: .note }

    ![Props]({{ site.baseurl }}/images/level-making/props/worldsmith_worlditem_tab.png)

Modify the world items's position using the input boxes, or flip the prop's texture. Click on the red button with the X to **remove** the world item instance **from the current screen**.

### Customize a world item

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Worlditems".
3. Expand both the **Customized** and the **Default** tabs to find your world item.
4. Once found, hover on its name/sprite to show up further settings:

   ![Hover on worlditem]({{ site.baseurl }}/images/level-making/props/worlditem_hover.png)

5. Click on **Replace**. A prompt will show up asking you to select the new worlditem's texture.

   ![Replace worlditem texture]({{ site.baseurl }}/images/level-making/props/worlditem_add_preview.png)

6. After clicking **Open**, your worlditem should have changed sprite!

   ![Successfully changed worlditem]({{ site.baseurl }}/images/level-making/props/worlditem_success.png)

<details class="expander">
   <summary markdown="1">
## Steps (without Worldsmith)
   </summary>
   <div markdown="1">

## Adding a world item
{: .no_toc }

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
{: .no_toc }

1. Open the worlditems xml configuration file located in `props/worlditems`.
2. Find the item you want to delete.
3. Remove the entire `WorldItemState` tag of the world item that you don't like.

## Personalizing a world item (optional)
{: .no_toc }

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

</div>
</details>

## Next up

[NPCs]({{site.baseurl}}/level-making/props/npcs).