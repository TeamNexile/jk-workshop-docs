---
layout: default
title: Merchants
grand_parent: Level Making
parent: Props
nav_order: 4
last_modified_date: 2023-02-08 17:30
---

# Merchant
{: .no_toc }

extension of the normal NPCs, that can also barter items!
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Here's a list of 5 merchant NPC you can freely modify as you will:

|Name|Sprite sheet directory|Sprite sheet name|
|---|---|---|
|merchant|`props/textures/old_man`|`merchant`|
|merchant_nbp|`props/textures/old_man`|`merchant_nbp`|
|snake|`props/textures/old_man`|`snake`|
|owl_shroom_guy|`props/textures/old_man/owl_chars`|`owl_shroom_guy`|
|owl_mold_man|`props/textures/old_man/owl_chars`|`owl_mold_man`|

## Retexturing a merchant NPC (without Worldsmith)

To replace a spritesheet of an NPC:

1. Convert a new image into a packed XNB file.
2. Name it as the NPC you want to retexture.
3. Place the file in `props/textures/merchant` and replace the file.
4. If you modified the sprite sheet, you will need to modify the [sprite sheets]({{site.baseurl}}/level-making/props/npcs#sprite-sheet) and the [animation settings]({{site.baseurl}}/level-making/props/npcs#animation-settings) inside your NPC's configuration file (that you can find in `props/textures/old_man/merchant`).

## Merchant additions

In addition the massive list of settings that the normal NPC brings, the merchant adds even more:

### Selling item settings

#### Setting the merchant's selling item (without Worldsmith)
{: .no_toc }

1. Search for the `sale_item` tag.
2. Modify the `sale_item` to the item you want to use give to the user.

#### Setting the merchant's selling currency (without Worldsmith)
{: .no_toc }

1. Search for the `currency_type` tag.
2. Modify the `currency_type` to the item of currency you want to use. It is recommended that you use an [item]({{site.baseurl}}/api/items){: target="_blank"} that is **stackable**.

#### Setting the merchant's selling price (without Worldsmith)
{: .no_toc }

1. Search for the `price_increase` tag.
2. Modify the `price_increase` to the payment value. If it's higher than 1, make sure your currency item is stackable, otherwise it can not be redeemable.

### Sale lines (before payment)

#### Setting sale lines (without Worldsmith)
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

#### Setting the selling line (without Worldsmith)
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

#### Setting sold lines (without Worldsmith)
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

#### Setting not-enough-currency lines (without Worldsmith)
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


## Next up

You've finally done it! You've learned all you needed to know about NPCs! Let's move to something more easy like [ravens]({{site.baseurl}}/level-making/props/ravens).