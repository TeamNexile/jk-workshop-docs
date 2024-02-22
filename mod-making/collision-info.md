---
layout: default
title: Collision Info
parent: Mod Making
nav_order: 2
last_modified_date: 2024-02-20 18:03
---

# Collision Info
{: .no_toc}

## Player Collision

The state of a player's collision is represented by an `AdvCollisionInfo` instance. 
This object at a base level is constructed of the following parts:

- Whether the player is in wind or not - accessed via the `IsInWind()` property, which checks if wind is enabled and if the player isn't colliding with a `NoWindBlock`
- A `SlopeType` property, indicating the type of slope the player is colliding with. `SlopeType.None` by default.
- A `SlopeNormal` property, indicating the normal vector of the slope the player is colliding with. `Vector2.Zero` by default.
- A collection of blocks that the player is colliding with. A specific block type can be checked using the `IsCollidingWith<T>()` function (eg, `IsCollidingWith<SandBlock>()`). A list of all collided blocks can be accessed via the `GetCollidedBlocks()` and the `GetCollidedBlocks<T>()` functions (eg. `GetCollidedBlocks<SandBlock>()`)

There are a number of helper functions to allow easy checking of base block types, such as the `Snow`, `Sand`, or `Water` properties.

A collision info object can be accessed a number of ways, but the most easily achieved is the `CheckCollision` or `GetCollisionInfo` functions of the `ICollisionQuery` interface. This can be obtained through the `LevelManager.Instance` singleton.

```cs
// Get the info about the current collision
ICollisionQuery collisionQuery = LevelManager.Instance;
AdvCollisionInfo collision = collisionQuery.GetCollisionInfo(bodyComp.GetHitbox());

// or alternatively check if there's a collision then respond to the info
if (collisionQuery.CheckCollision(bodyComp.GetHitbox(), out Rectangle overlap, out AdvCollisionInfo info))
{
    // Do something
}
```