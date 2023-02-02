---
layout: default
title: Messages
grand_parent: Level Making
parent: Props
nav_order: 6
last_modified_date: 2023-02-01 17:56
---

# Messages
{: .no_toc }

text "bubbles" that spawn by triggering a hitbox<!-- more -->
{: .fs-6 .fw-300 }

### Add a message (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer }

### Add a message (without Worldsmith)

1. Copy the following snippet:
   ```xml
   <?xml version="1.0"?>
    <RattmanSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <screen>7</screen>					<!-- screen number -->
        <hitbox_center>						  <!-- hitbox alignment -->
            <X>0</X>						      <!-- 0: trigger alignment on the right 1: trigger alignment on the left -->
            <Y>0</Y>						      <!-- 0: trigger alignment on the bottom 1: trigger alignment on the up -->
        </hitbox_center>
        <hitbox>							      <!-- trigger hitbox -->
            <X>304</X>						    <!-- position on the X axis -->
            <Y>272</Y>						    <!-- position on the Y axis -->
            <Width>32</Width>				  <!-- width of the hitbox -->
            <Height>32</Height>				<!-- height of the hitbox -->
        </hitbox>
        <font>Default</font>				<!-- (!) -->
        <text_anchor>					      <!-- (*) change only if necessary -->
            <X>290</X>					  <!-- (*) change only if necessary -->
            <Y>316</Y>
        </text_anchor>
        <bubble_format>
            <direction>Right</direction>	<!-- alignment text -->
            <anchor>						          <!-- anchoring text directions -->
                <X>Left</X>					        <!-- anchoring to display horizontally; Left or Right -->
                <Y>Down</Y>					        <!-- anchoring to display horizontally; Up or Down -->
            </anchor>
            <width>160</width>				    <!-- width of the bubble -->
        </bubble_format>
        <text>								            <!-- contains the texts for the message -->
            <lines>							            <!-- list of bubble text -->
                <string>Message.</string>
                <string>Hi.</string>
            </lines>
        </text>
    </RattmanSettings>
   ```
The messages can be found inside `props/messages`.