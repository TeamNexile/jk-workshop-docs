---
layout: default
title: Props
parent: API
last_modified_date: 2023-02-03 10:48
---

# Fonts for props (NPCs and messages)
{: #oldmanfont }

```cs
namespace JumpKing.MiscEntities.OldMan
{
    public enum OldManFont
}
```

|Value|Used by|
|---|---|
|Default|Default font|
|Gargoyle|Font used by all Gargoyles (NB+ Entrance and Halted Ruins)|

---

# Speech bubble directions (NPCs and messages)
{: #speechbubbleformat }

```cs
namespace JumpKing.MiscEntities.OldMan.SpeechBubbleFormat
{
    public enum DirectionX
    public enum DirectionY
}
```

## Speech bubble horizontal direction and anchor
can be `Left` or `Right`.

## Speech bubble vertical anchor
can be `Up` or `Down`.