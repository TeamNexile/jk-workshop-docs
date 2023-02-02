---
layout: default
title: NPCs
grand_parent: Level Making
parent: Props
nav_order: 3
last_modified_date: 2023-02-01 17:29
---

## NPCs
are the entities that talk and barter with you.

> **NPCs are hardcoded** in the game, so they *can not be removed*; but they **can be reskinned and moved** to a screen you are not using (like 169, the last screen possible in the game limitations).

NPCs can be of two types:
1. `old man`, a normal entity that only speaks
2. `merchant`, an extension of the `old man` but can also barter items with the player.

While the textures for both needs to be inside `textures/old_man`, the quotes and settings of each NPC is stored based of their type:
- `old man`, is stored inside `textures/old_man/lines`
- `merchant`, is stored inside `textures/old_man/merchant`

### Old Man

This following XML file explains one of the Old Man NPC-types, `hermit_quotes.xml`.

<script src="https://gist.github.com/Phoenixx19/44ac06687463a5ba28c6489948dba576.js"></script>


### Item trigger

Implemented from <span class="badge-pill">**v1.5.0**</span>, you can create quotes that trigger when wearing an item.

|tag|description|
|---|---|
|`<items>`|multiple instances of `<OldManItem>`|
|`<OldManItem>`|Contains the info for every item trigger|
|`<item>`|Item name|

An example of item trigger:
```xml
<items>
  <OldManItem>
    <item>Cap</item>
    <quotes>
      <OldManQuote>
        <lines>
          <string>Sick hat, bro!</string>
        </lines>
      </OldManQuote>
    </quotes>
  </OldManItem>
  <!-- add another OldManItem, if you want another trigger -->
</items>
```

### Fall trigger

Implemented from <span class="badge-pill">**v1.5.0**</span>, you can create quotes that triggers when the amount of falls is reached.

|tag|description|
|---|---|
|`<falls>`|multiple instances of `<OldManFalls>`|
|`<OldManFalls>`|Contains the info for every item trigger|
|`<fallStart>`|Minimal fall number (number included!)|
|`<fallEnd>`|Maximum fall number|

An example of a fall trigger:
```xml
<falls>
  <OldManFall>
    <fallStart>15</fallStart> <!-- you can use 15 for fallEnd for the next OldManFall -->
    <fallEnd>20</fallEnd> <!-- you can use 20 for fallStart for the next OldManFall -->
    <quotes>
      <OldManQuote>
        <lines>
          <string>Just stop falling to get the babe!</string>
        </lines>
      </OldManQuote>
    </quotes>
  </OldManFall>
  <!-- add another OldManFall, if you want another trigger -->
</falls>
```