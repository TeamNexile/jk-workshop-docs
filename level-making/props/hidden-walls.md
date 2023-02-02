---
layout: default
title: Hidden Walls
grand_parent: Level Making
parent: Props
nav_order: 2
last_modified_date: 2023-02-01 17:28
---

## Hidden walls
are used in-game to hide areas or make the screen more realistic, the hidden wall works as foreground until the player gets into its position where it becomes transparent.

The hidden walls textures are located in `props/hidden_walls/textures`, they are managed by a configuration file called `hidden_wall(SCREEN NUMBER).xml`.

```xml
<?xml version="1.0"?>
<RaymanCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <walls>

    <RaymanData> 
    	<achievements>              <!-- leave this as is -->
        <AchievementCode>GO_THOUGH_ILLUSORY_WALL</AchievementCode>  <!-- leave this as is -->
      </achievements>             <!-- leave this as is -->

      <texture_name>1_hidden_wall</texture_name>  <!-- name of the texture inside props/hidden_wall/texture -->
      <Position>                  <!-- contains the details on the X and Y coordinates -->
        <X>0</X>                  <!-- X coordinate on the screen -->
        <Y>169</Y>                <!-- Y coordinate on the screen -->
      </Position>
    </RaymanData>

  </walls>
</RaymanCollection>
```

### Hidden wall prop
Hidden walls can have props too; these can be added creating a different prop configuration file inside `props/hidden walls props` called `prop(SCREEN NUMBER).xml`.

```xml
<?xml version="1.0"?>
<PropCollection xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <screen>133</screen> <!-- screen number -->

  <Props>
    <PropData>
      <type>ghost_platform</type>   <!-- texture inside props/textures -->
      <Position>                    <!-- contains the details on the X and Y coordinates -->
        <X>358</X>                  <!-- X coordinate on the screen -->
        <Y>206</Y>                  <!-- Y coordinate on the screen -->
      </Position>
      <flipped>false</flipped>      <!-- flip texture -->
    </PropData>
  </Props>
</PropCollection>
```