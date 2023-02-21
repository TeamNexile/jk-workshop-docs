---
layout: default
title: Items
parent: API
last_modified_date: 2023-02-21 16:18
---

# Items list

```cs
namespace JumpKing.MiscEntities.WorldItems
{
    public enum Items
}
```

|Item|In-game name|Stackable|Wearable and<br>[customizable]({{ site.baseurl }}/level-making/king)|Worlditem|
|---|---|
|Crown|Crown (Main Babe)|❌|✔️|❌|
|Shoes|Shoes|❌|✔️|❌|
|GoldRing|Gold Ring|✔️|❌|❌|
|CrownNBP|Magic Crown (New Babe Plus)|❌|✔️|❌|
|Ruby|Ruby|✔️|❌|✔️|
|SnakeRing|Snake Ring|❌|✔️|❌|
|GiantBoots|Giant Boots|❌|✔️|✔️|
|Silver|Silver Coins|✔️|❌|✔️|
|Cap|Cap|❌|✔️|✔️|
|GnomeHat|Scholar's Hat|❌|✔️|✔️|
|Tunic|Tunic|❌|✔️|✔️|
|YellowShoes|Yellow Shoes|❌|✔️|✔️|
|CrownOwl|Golden Cap (Ghost of the Babe)|❌|✔️|❌|
|CapeOwl|Cape|❌|✔️|❌|
|BabeGhostItem|||||
|GhostFragment|Ghost Fragments|✔️|❌|✔️|
|Shroom|Mushrooms|✔️|❌|✔️|
|BugNote|Bug's Note|❌|❌|✔️|
|NULL|||||

> The `NULL` item is used for **all skins** (single skins AND skin sets) as the base for retexturing the king.
{: .note }