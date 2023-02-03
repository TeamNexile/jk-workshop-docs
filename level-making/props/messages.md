---
layout: default
title: Messages
grand_parent: Level Making
parent: Props
nav_order: 6
last_modified_date: 2023-02-03 12:21
---

# Messages
{: .no_toc }

text "bubbles" that spawn by triggering a hitbox<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Add a message (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

## Add a message (without Worldsmith)

1. Copy the following snippet:
   ```xml
   <?xml version="1.0"?>
    <RattmanSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <screen>YOUR_MESSAGE_SCREEN</screen>					<!-- screen number -->
        <hitbox_center>						  <!-- hitbox alignment -->
            <X>1</X>						      <!-- 0: trigger alignment on the right 1: trigger alignment on the left -->
            <Y>1</Y>						      <!-- 0: trigger alignment on the bottom 1: trigger alignment on the up -->
        </hitbox_center>
        <hitbox>							      <!-- trigger hitbox -->
            <X>YOUR_HITBOX_ON_X_AXIS</X>						    <!-- position on the X axis -->
            <Y>YOUR_HITBOX_ON_Y_AXIS</Y>						    <!-- position on the Y axis -->
            <Width>YOUR_HITBOX_WIDTH</Width>				  <!-- width of the hitbox -->
            <Height>YOUR_HITBOX_HEIGHT</Height>				<!-- height of the hitbox -->
        </hitbox>
        <font>Default</font>				<!-- (!) -->
        <text_anchor>					      <!-- (*) change only if necessary -->
            <X>YOUR_TEXT_START_X_POSITION</X>					  <!-- (*) change only if necessary -->
            <Y>YOUR_TEXT_START_Y_POSITION</Y>
        </text_anchor>
        <bubble_format>
            <direction>YOUR_TEXT_BUBBLE_ALIGNMENT</direction>	<!-- alignment text -->
            <anchor>						          <!-- anchoring text directions -->
                <X>YOUR_TEXT_BUBBLE_ANCHOR_X</X>					        <!-- anchoring to display horizontally; Left or Right -->
                <Y>YOUR_TEXT_BUBBLE_ANCHOR_Y</Y>					        <!-- anchoring to display horizontally; Up or Down -->
            </anchor>
            <width>YOUR_TEXT_BUBBLE_WIDTH</width>				    <!-- width of the bubble -->
        </bubble_format>
        <text>								            <!-- contains the texts for the message -->
            <lines>							            <!-- list of bubble text -->
                <string>This is a short string.</string>
                <string>This could be a long string which could be somewhat long to show.</string>
            </lines>
        </text>
    </RattmanSettings>
   ```

### Setting the screen

Replace `YOUR_MESSAGE_SCREEN` with your screen number.<br>This will set so the message is available to the screen given.

### Setting the hitbox

The hitbox is needed to trigger the message to show up.

Inside the `hitbox` tag, you will see 4 tags with their respetive values:

Tag name|Value
---|---
X|`YOUR_HITBOX_ON_X_AXIS`
Y|`YOUR_HITBOX_ON_Y_AXIS`
Width|`YOUR_HITBOX_WIDTH`
Height|`YOUR_HITBOX_HEIGHT`

1. Replace the X and Y values with relative values of your screen.
    > You can easily see the values in the build mode by changing it from Absolute to Relative from the Pause Menu. Also thanks to the "Hitbox first" toggle in the build mode, you can easily see where the hitbox is, and fix it with ease.
    {: .highlight }
2. Replace the Width and Height values with the size wanted.

> By default, your item will start from the X and Y values given and expand right and down. If you want your item to be centered, change both `hitbox_center`'s X and Y to `0.5`, or if you want it to start from the right, change it to `0`. If this sounds confusing, test it in-game!
{: .note }

### Setting a different font (optional)

You can also change the font if you would like.

If you search for the `font` tag, you can see it has a Default value.

Check all the available values for the font in the [OldManFont's API]({{site.baseurl}}/api/props#oldmanfont){: target="_blank"}.

### Setting the text anchor

The text anchor is the starting point for your speech bubble. Inside the `text_anchor`, you have 2 tags:

Tag name|Value
---|---
X|`YOUR_TEXT_START_X_POSITION`
Y|`YOUR_TEXT_START_Y_POSITION`

Replace the X and Y values with relative values of your screen.

### Setting the bubble format

The bubble format can help you format text the way you want it; by aligning it differently, setting the anchor for your text and deciding the maximum width of your message's speech.

Inside the `bubble_format`, you have 4 tags:

Tag name|Value
---|---
direction|`YOUR_TEXT_BUBBLE_ALIGNMENT`
X|`YOUR_TEXT_BUBBLE_ANCHOR_X`
Y|`YOUR_TEXT_BUBBLE_ANCHOR_Y`
width|`YOUR_TEXT_BUBBLE_ANCHOR_WIDTH`

1. Replace `YOUR_TEXT_BUBBLE_ALIGNMENT` with either Left or Right depending where you want the text to align.
2. Replace `YOUR_TEXT_BUBBLE_ANCHOR_X` and `YOUR_TEXT_BUBBLE_ANCHOR_X` values with their [respective values]({{site.baseurl}}/api/props#speechbubbleformat){: target="_blank"}.
3. Replace `YOUR_TEXT_BUBBLE_ANCHOR_WIDTH` with your speech maximum width.

### Setting the text

Depending by your speech bubble width, the text might get very long. So don't forget to cut them in more `string`s.

Just like the example above, here's how you can avoid long texts while maintaining the content the same:
```xml
<text>
    <lines>
        <string>This is a short string.</string>
        <!-- <string>This could be a long string which could be somewhat long to show.</string> -->
        <string>This could be a long string,</string>
        <string>which could be somewhat long to show.</string>
    </lines>
</text>
```

So if you want to add more text, simply add a new line with:
```xml
<string>My new text!</string>
```

### Once done...

1. Save your file by naming it properly so you can always retroactively tell which message is.
2. Place it in `props/messages` and you are set!

## Next up

That's all the props for you! Let's move on to setting new [**sprites for your king**]({{site.baseurl}}/level-making/king)!