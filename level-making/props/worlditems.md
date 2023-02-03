---
layout: default
title: World Items
grand_parent: Level Making
parent: Props
nav_order: 2
last_modified_date: 2023-02-01 17:22
---

## World items

are **items that the player can pick up** by walking on them. These world items have their own texture inside `/mods/props/worlditems`. 


In order to have the world items working in-game, the game reads a file called `worlditems.xml` inside the folder specified above. This file contains an `<items>` tag which is an array (multiple instances) of the `<WorldItemState>` tag.

### WorldItemState
<p class="do-i-need-it">optional</p>

contains the information of a single world item.

`<WorldItemState>` contains:
- the name of the item (using the `<item>` tag)
- the number of the screen (using the `<screen>` tag)
- the position on the screen (using the `<_x>` and `<_x>` tags)

Following the logic, you'll end up with a `worlditems.xml` file like this:

<script src="https://gist.github.com/Phoenixx19/79522e0b5424f17bc8f5821e65885306.js"></script>