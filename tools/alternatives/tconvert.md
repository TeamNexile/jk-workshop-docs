---
layout: default
title: TConvert
parent: Content packing tools
grand_parent: ✔ Tools
nav_order: 4
last_modified_date: 2023-01-13 11:47
---

# TConvert
{: #tconvert .title }

is an Windows Application for managing Terraria content resources, made by [**trigger-segfault**](https://github.com/trigger-segfault).
{: .fs-6 .fw-300 }
<!-- more -->


[Download tool](https://github.com/trigger-segfault/TConvert/releases/latest){: .btn .btn-blue }
[Go to repository](https://github.com/trigger-segfault/TConvert){: .btn }

![Preview](/images/TConvert.png)

---

### What does Terraria have to do with Jump King?
Being Terraria based on MonoGame (which is the same engine under Jump King), this works for Jump King too.

## Table of convertions

<table>
    <thead>
        <tr>
            <th>Type of file</th>
            <th>file to XNB</th>
            <th>XNB to file</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th style="font-weight: normal;">image</th>
            <th class="label-green">✔</th>
            <th class="label-green">✔</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">sound</th>
            <th class="label-green">✔</th>
            <th class="label-green">✔</th>
        </tr>
    </tbody>
</table>

## Supported types
Supported images formats are: `.png`, `.bmp`<br>
Supported sound formats are: `.wav`

## Usage

1. Select if you want to **Extract** (XNB to file) or **Convert** (file to XNB) content by clicking on the wanted tab.
2. Select if you want to extract/convert a folder or a file from the **Extract Mode** dropdown.
3. Choose the input file/folder using the folder icon on the right side of **Input**.
4. Choose the output file/folder using the folder icon on the right side of **Output**.
   
   {: .highlight }
   > If you are using a folder, make sure the types you are extracting/converting are selected (**Images, Sounds**).

5. Click "*Extract*" or "*Convert*".
6. Done!

### CLI support

There is no command line support for this program.