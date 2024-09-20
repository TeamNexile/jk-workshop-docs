---
layout: default
title: Messages
grand_parent: Level Making
parent: Props
nav_order: 6
last_modified_date: 2024-09-20 16:38
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

## What are messages?

Messages are text that pop up from entering a trigger box such as the Billboard in Bargainburg, or the Stones in Bugstalk.

![Message example]({{site.baseurl}}/images/level-making/props/message_example.png)

## Dealing with a message

Adding a message has not been yet implemented inside Worldsmith. If you'd like to add a message, consider looking out the [**Steps (without Worldsmith)**](./#steps-without-worldsmith).
{: .disclaimer }

### Adding a message

1. Navigate to the **Screens** page.
2. Right-click onto the canvas on the left side of your screen (where you have your level preview) and select *Add on screen...*, then *NPCs and text*, then *Message*.

    ![Message right click]({{ site.baseurl }}/images/level-making/props/message_right_click.png)

3. Once clicked, a prompt will ask you a few details about your message. You will need to select which font style, text alignment and the message contents you want to display.

    ![Message details]({{ site.baseurl }}/images/level-making/props/message_prompt.png)

4. Once done setting it up, click **Add**.<br>Your message should appear on your preview or on your right sidebar.

    ![Message added successfully]({{ site.baseurl }}/images/level-making/props/message_add_success.png)

### Editing, moving or removing a message

1. Navigate to the **Screens** page.
2. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the weather you want to change/get rid of.
3. From the right side of the page, expand the **Messages** tab. Here you should find all your messages.

    > Click on a message or, using the left side of the page (preview), click on the message's hitbox to easily find the message you are looking for!
    >
    > ![Find message]({{ site.baseurl }}/images/level-making/props/message_find.png)
    {: .note }

    ![Change/delete message]({{ site.baseurl }}/images/level-making/props/message_modify.png)

Modify your message's font, text direction, quotes at your will. Click on the yellow button with an arrow to **move the message to another screen**. Click the red button with the trash bin to **delete the message completely**.

> Message's position, text position and text anchoring have not been yet implemented inside Worldsmith. If you'd like to modify them, consider looking out the [**Steps (without Worldsmith)**](./#steps-without-worldsmith).
{: .disclaimer }

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

## Add a message
{: .no_toc }

1. Copy the following snippet:
   ```xml
   <?xml version="1.0"?>
    <RattmanSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <screen>YOUR_MESSAGE_SCREEN</screen>
        <hitbox_center>
            <X>1</X>    <!-- 0: trigger alignment on the right 1: trigger alignment on the left -->
            <Y>1</Y>    <!-- 0: trigger alignment on the bottom 1: trigger alignment on the up -->
        </hitbox_center>
        <hitbox>
            <X>YOUR_HITBOX_ON_X_AXIS</X>
            <Y>YOUR_HITBOX_ON_Y_AXIS</Y>
            <Width>YOUR_HITBOX_WIDTH</Width>
            <Height>YOUR_HITBOX_HEIGHT</Height>
        </hitbox>
        <font>Default</font>
        <text_anchor>
            <X>YOUR_TEXT_START_X_POSITION</X>
            <Y>YOUR_TEXT_START_Y_POSITION</Y>
        </text_anchor>
        <bubble_format>
            <direction>YOUR_TEXT_BUBBLE_ALIGNMENT</direction>	<!-- alignment text -->
            <anchor>
                <X>YOUR_TEXT_BUBBLE_ANCHOR_X</X>
                <Y>YOUR_TEXT_BUBBLE_ANCHOR_Y</Y>
            </anchor>
            <width>YOUR_TEXT_BUBBLE_WIDTH</width>
        </bubble_format>
        <text>
            <lines>
                <!-- your lines here -->
                <string>This is a short string.</string>
                <string>This could be a long string which could be somewhat long to show.</string>
            </lines>
        </text>
    </RattmanSettings>
   ```

### Setting the screen
{: .no_toc }

Replace `YOUR_MESSAGE_SCREEN` with your screen number.<br>This will set so the message is available to the screen given.

### Setting the hitbox
{: .no_toc }

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
{: .no_toc }

You can also change the font if you would like.

If you search for the `font` tag, you can see it has a Default value.

Check all the available values for the font in the [OldManFont's API]({{site.baseurl}}/api/props#oldmanfont){: target="_blank"}.

### Setting the text anchor
{: .no_toc }

The text anchor is the starting point for your speech bubble. Inside the `text_anchor`, you have 2 tags:

Tag name|Value
---|---
X|`YOUR_TEXT_START_X_POSITION`
Y|`YOUR_TEXT_START_Y_POSITION`

Replace the X and Y values with relative values of your screen.

### Setting the bubble format
{: .no_toc }

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
{: .no_toc }

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
{: .no_toc }

1. Save your file by naming it properly so you can always retroactively tell which message is.
2. Place it in `props/messages` and you are set!

</div>
</details>

## Next up

Creating sprites for the [**King**]({{site.baseurl}}/level-making/king)  (player character).