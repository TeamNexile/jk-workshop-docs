---
layout: default
title: Merchants
grand_parent: Level Making
parent: Props
nav_order: 4
last_modified_date: 2024-09-20 16:44
---

# Merchant
{: .no_toc }

extensions to normal NPCs. They can also barter items.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## How does a merchant work?

The merchant has three main values that gets used for the bargain:
- **the selling item** (the item is selling to you),
- **the currency** (the item used as currency),
- **the price** (the item quantity needed for the trade).

For example, the shroom guy in the Philosopher's Forest wants you to get **9 Shrooms**, this speech ([sale lines](#sale-lines-before-payment)) is usually presented right after the introduction.

![Merchant before]({{site.baseurl}}/images/level-making/props/merchant_before_2.png)

While you haven't collected the wanted amount of shrooms, the merchant will trigger the [not-enough-currency lines](#not-enough-currency-lines).

Once you got all the shrooms, the trading speech ([selling line](#selling-line-during-payment)) will show up.

![Merchant inv before]({{site.baseurl}}/images/level-making/props/merchant_before.png)
![Merchant after]({{site.baseurl}}/images/level-making/props/merchant_after_2.png)

Once finished with the selling line, that's finished you will get the [sold lines](#sold-lines-after-payment) and your item will be automatically worn on you (if the selling item is wearable).

![Merchant inv after]({{site.baseurl}}/images/level-making/props/merchant_after.png)
![Merchant after]({{site.baseurl}}/images/level-making/props/merchant_after_3.png)

## Adding a new merchant

1. Navigate to the **Content Manager** page.

   ![Content Manager]({{ site.baseurl }}/images/level-making/worldsmith_content_manager.png)

2. Scroll until you find an header "**NPCs**".
3. Click on the **Create a NPC** button found on the right side. A prompt will show up asking the necessary details for your merchant. The following image is how it should look like.

   ![Create a NPC]({{ site.baseurl }}/images/level-making/props/npc_add.png)

4. Select the appropriate type for your merchant (click on merchant) and write a recognizable name for your merchant, you **won't be able to change it later**!
5. Click on **Select sprite**.
7. A new prompt will show up asking you to select a sprite for your merchant.

   ![Add NPC]({{ site.baseurl }}/images/level-making/props/npc_add_preview.png)

8. After selecting your file, click **Open**.
9. Make sure the row and column count align with your sprite sheet.

   ![NPC adjust spritesheet]({{ site.baseurl }}/images/level-making/props/npc_adjust.png)

10. Click **Add NPC** and you should see your NPC below "Merchants".

   ![Merchant success]({{ site.baseurl }}/images/level-making/props/merchant_success.png)

## Changing a merchant' setting

1. Navigate to the **Content Manager** page.
2. Scroll until you find an header "**NPCs**".
3. Click on the merchant you'd like to edit its settings.

   ![Merchant success]({{ site.baseurl }}/images/level-making/props/merchant_success.png)

![Merchant settings]({{ site.baseurl }}/images/level-making/props/merchant_settings.png)

A prompt will show up with the merchant' settings, from here you can modify as you will.

## Changing a merchant' speech

1. Navigate to the **Content Manager** page.
2. Scroll until you find an header "**NPCs**".
3. On the NPC you are looking to modify, click on the blue button that contains a text bubble.

   ![Merchant success]({{ site.baseurl }}/images/level-making/props/merchant_success.png)

![Merchant speeches]({{ site.baseurl }}/images/level-making/props/merchant_quotes.png)

A prompt will show up with the merchant' quotes, from here you can modify as you will.

## Moving an merchant from a screen

Optionally, if you are on the **Screens** page. You can decide to add (move) to a specific screen.

2. Right-click onto the canvas on the left side of your screen (where you have your level preview) and select *Add on screen...*, then *NPCs and text*, then *Merchant*.

    ![Merchant right click]({{ site.baseurl }}/images/level-making/props/merchant_right_click.png)

3. Once clicked, a prompt will ask you to select the merchant that you want to move onto the current screen.

    ![Merchant details]({{ site.baseurl }}/images/level-making/props/merchant_prompt.png)

4. Once selected, click **Add**.<br>Your merchant should appear on your preview.

    ![Merchant added successfully]({{ site.baseurl }}/images/level-making/props/merchant_move_success.png)

## Removing a merchant completely

1. Navigate to the **Content Manager** page.
2. Scroll until you find an header "**NPCs**".
3. On the merchant you are looking to modify, click on the red button that contains a trash bin.

   ![Merchant success]({{ site.baseurl }}/images/level-making/props/merchant_success.png)

4. A prompt will show up asking for confirmation of your deletion. Click **Yes, delete** if you are completely sure.

   ![Merchant delete]({{ site.baseurl }}/images/level-making/props/merchant_delete.png)

After clicking it, your merchant will be removed completely. And you shouldn't see it both in the **Content Manager** and **Screens** pages.

<details class="expander">
   <summary markdown="1">
## Steps (without Worldsmith)
   </summary>
   <div markdown="1">

<!-- ## Types of merchant

Here's a list of 5 merchant NPC you can freely modify as you will:

|Name|Sprite sheet directory|Sprite sheet name|
|---|---|---|
|merchant|`props/textures/old_man`|`merchant`|
|merchant_nbp|`props/textures/old_man`|`merchant_nbp`|
|snake|`props/textures/old_man`|`snake`|
|owl_shroom_guy|`props/textures/old_man/owl_chars`|`owl_shroom_guy`|
|owl_mold_man|`props/textures/old_man/owl_chars`|`owl_mold_man`| -->

## Retexturing a merchant NPC
{: .no_toc }

To replace a spritesheet of a NPC:

1. Convert a new image into a packed XNB file.
2. Name it as the NPC you want to retexture.
3. Place the file in `props/textures/merchant` and replace the file.
4. If you modified the sprite sheet, you will need to modify the [sprite sheets]({{site.baseurl}}/level-making/props/npcs#sprite-sheet) and the [animation settings]({{site.baseurl}}/level-making/props/npcs#animation-settings) inside your NPC's configuration file (that you can find in `props/textures/old_man/merchant`).

## Merchant additions
{: .no_toc }

In addition the massive list of settings that the normal NPC brings, the merchant adds even more:

### Selling item settings
{: .no_toc }

#### Setting the merchant's selling item
{: .no_toc }

1. Search for the `sale_item` tag.
2. Modify the `sale_item` to the item you want to use give to the user.


#### Setting the merchant's selling currency
{: .no_toc }

1. Search for the `currency_type` tag.
2. Modify the `currency_type` to the item of currency you want to use. It is recommended that you use an [item]({{site.baseurl}}/api/items){: target="_blank"} that is **stackable**.

#### Setting the merchant's selling price
{: .no_toc }

1. Search for the `price_increase` tag.
2. Modify the `price_increase` to the payment value. If it's higher than 1, make sure your currency item is stackable, otherwise it can not be redeemable.

### Sale lines (before payment)
{: .no_toc }

#### Setting sale lines
{: .no_toc }

1. Search for the `sale_lines` tag.
2. Get rid of all the `string` tags that could be present.
3. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
4. Replace `YOUR_STRING_HERE` with your "selling this item" string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many quotes as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

### Selling line (during payment)
{: .no_toc }

#### Setting the selling line
{: .no_toc }

1. Search for the `sell_quote` tag.
2. Get rid of all the `string` tags that could be present.
3. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
4. Replace `YOUR_STRING_HERE` with your "im selling you this item as we speak" string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   {: .highlight }

### Sold lines (after payment)
{: .no_toc }

#### Setting sold lines
{: .no_toc }

1. Search for the `sold_lines` tag.
2. Get rid of all the `string` tags that could be present.
3. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
4. Replace `YOUR_STRING_HERE` with your "sold this item to you" string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many quotes as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

### Not-enough-currency lines
{: .no_toc }

#### Setting not-enough-currency lines
{: .no_toc }

1. Search for the `no_gold_lines` tag.
2. Get rid of all the `string` tags that could be present.
3. Copy the following snippet:
   ```xml
    <string>YOUR_STRING_HERE</string>
   ```
4. Replace `YOUR_STRING_HERE` with your "you don't have enough of this item" string.
   > You can add as many strings as you want, just copy the snippet in a line after your closing `string` tag and replace `YOUR_STRING_HERE` with your second, third... string.
   > 
   > You can even add as many quotes as you want by copying the `OldManQuote` tag and pasting it below the closing tag of the previous `OldManQuote`.
   {: .highlight }

</div>
</details>

## Speech extensions

If you want to display the price in-game through a speech, use `[gold_count]` as the value.

## Next up

[**Ravens**]({{site.baseurl}}/level-making/props/ravens).