---
layout: default
title: Tools
has_children: true
nav_order: 4
last_modified_date: 2023-01-10 17:59
---

# Tools overhaul
{: .fs-9 }

Before going on detail on every tool's detail in the next pages; it's fair that every person chooses their software based on what they think it's better for their own productivity.

The following table explains every image/sound conversion tool on their pros and cons.<!-- more -->

|tool|pros|cons|
|---|---|---|
|Our tool|it is amazing|none|
|Fast XNB Builder|✔ Also **converts sound files**<br>✔ Pretty fast (3rd in speed)<br>✔ Works with command line|❌ Doesn't convert from XNB to file<br>❌ Doesn't have an easy UI<br>❌ Will **always export in the default folder**|
|XNBCLI|✔ **Packs/unpacks** images<br>✔ Really fast (2nd in speed)<br>✔ Can export in a different folder [\*¹](#detail1)<br>✔ Works with command line|❌ Can't convert anything else<br>❌ **Needs some dependencies** to be installed|
|PNG to XNB|✔ **Blazing fast** (1st in speed)<br>✔ Easy to use<br>✔ Can export images anywhere|❌ Converts images only|
|TConvert|✔ Easy to use<br>✔ **Converts** almost **everything**<br>|❌ Slightly **unstable** [\*²](#detail2)<br>❌ Not so fast (4th in speed)<br>❌ Doesn't have any command line support|
|VS2019 + MonoGame|✔ **Converts everything** [\*³](#detail3)|❌ Needs **way too many dependencies**<br>❌ Not fast at all (5th in speed)<br>❌ Hard and long process|

> \*¹ - *XNBCLI* can export in a different folder if set by editing the "pack.bat" and "unpack.bat" files. This *might* require a bit of command line knowledge.
{: #detail1 }

> \*² - *TConvert* sometimes can be unstable both on the "Extract" tab (XNB to file) but also "Convert" tab (file to XNB), especially with sounds.
{: #detail2 }

> \*³ - *VS2019 + MonoGame*'s process hasn't been fully tested, so might not be fully working.
{: #detail3 }

At the bottom of the list there are **additional helper tools**; these tools are optional but can enhance your productivity on creating a custom level.