---
layout: default
title: Props
parent: API
last_modified_date: 2023-02-08 16:09
---

# Fonts for props (NPCs and messages)
{: #OldManFont }

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

# NPC text rendering layer
{: #OldManRenderingLayer }

```cs
namespace JumpKing.MiscEntities.OldMan
{
    public enum OldManRenderingLayer
}
```

Values:
- Foreground
- Midground

---

# NPC rendering layer
{: #PersonRenderingLayer }

```cs
namespace JumpKing.MiscEntities.OldMan
{
    public enum PersonRenderingLayer
}
```

Values:
- Default
- Foreground
- Midground

---

# Speech bubble directions (NPCs and messages)
{: #SpeechBubbleFormat }

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

---

# Flags for NPCs
{: #StoryEventFlags }

```cs
namespace JumpKing.SaveThread
{
    public enum StoryEventFlags
}
```

|Value|Meaning|
|---|---|
|CompletedNormalGame|The player has completed the Main Babe at least once|
|CompletedNBP|The player has completed New Babe Plus at least once|
|StartedNBP|This current attempt is New Babe Plus|
|CompletedGhost|The player has completed Ghost of the Babe at least once|
|StartedNBP|This current attempt is Ghost of the Babe|