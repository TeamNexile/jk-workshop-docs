---
layout: default
title: Content packing tools
has_children: true
parent: Tools
nav_order: 2
last_modified_date: 2023-03-24 10:46
---

<!-- 
# Alternatives to Worldsmith
-->

# Content packing tools

<!-- While Worldsmith can be helpful for starters, it might be not the case for you especially if you would like to do everything by yourself. And that's fine because we got this aspect covered too, that's why we made a list of alternative tools to achieve the same result. -->

Choose your software based on what you think it’s better for your goals.

The following table explains every image/sound conversion tool on their pros and cons.<!-- more -->

|tool|pros|cons|
|---|---|---|
|[Fast XNB Builder]({{ site.baseurl }}/tools/alternatives/fast-xnb-builder)<br>The ol' reliable|✔ Also **converts sound files**<br>✔ Pretty fast (3rd in speed)<br>✔ Works with command line|❌ Doesn't have an easy UI<br>❌ Will **always export in the default folder**|
|[PNG to XNB]({{ site.baseurl }}/tools/alternatives/png-to-xnb)<br>MVP for updating hitboxes|✔ **Blazing fast** (1st in speed)<br>✔ Easy to use<br>✔ Can export images anywhere<br>✔ Works with command line|❌ Not made for mass-converting<br>❌ Converts one PNG only at a time|
|[XNBCLI]({{ site.baseurl }}/tools/alternatives/xnbcli)<br>The mass-converting tool|✔ **Packs/unpacks** images<br>✔ Really fast (2nd in speed)<br>✔ Can export in a different folder [\*¹](#detail1)<br>✔ Works with command line|❌ Can't convert anything else than images|
|[TConvert]({{ site.baseurl }}/tools/alternatives/tconvert)<br>One tool that does everything|✔ Easy to use<br>✔ **Converts everything**|❌ Can be **unstable** [\*²](#detail2) at times<br>❌ Not so fast (4th in speed)<br>❌ Doesn't have any command line support|
|[MonoGame Pipeline]({{ site.baseurl }}/tools/alternatives/monogame-pipeline)<br>Roleplay as Nexile|✔ **Converts everything**|❌ Needs **way too many dependencies**<br>❌ Not fast at all (5th in speed)<br>❌ Hard and long installation process|

> \*¹ - *XNBCLI* can export in a different folder if set by editing the "pack.bat" and "unpack.bat" files. This *might* require a bit of command line knowledge.
{: #detail1 }

> \*² - *TConvert* sometimes can be unstable both on the "Extract" tab (XNB to file) but also "Convert" tab (file to XNB), especially with sounds.
{: #detail2 }