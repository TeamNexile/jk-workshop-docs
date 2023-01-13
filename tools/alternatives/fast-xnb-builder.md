---
layout: default
title: ✔ Fast XNB Builder
parent: Content packing tools
grand_parent: Tools
nav_order: 1
last_modified_date: 2023-01-13 11:10
---

# Fast XNB Builder 
{: #fast-xnb-builder .title }

is a quick tool to convert files to .XNB, made by [**NicusorN5**](https://github.com/NicusorN5).
{: .fs-6 .fw-300 }

[Download tool](https://github.com/Phoenixx19/Fast-XNB-Builder/releases/latest){: .btn .btn-blue }
[Go to repository](https://github.com/NicusorN5/Fast-XNB-Builder){: .btn }

![Preview](/images/FastXNBConverter.png)

---

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
            <th class="label-red">✖</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">sound</th>
            <th class="label-green">✔</th>
            <th class="label-red">✖</th>
        </tr>
    </tbody>
</table>

## Supported types

Supported image formats are: `.dds`, `.png`, `.bmp`<br>
Supported sound formats are: `.ogg`, `.mp3`, `.wav`

## Usage

1. Create a folder with all the pictures and sounds you want to pack.
2. Open `Fast XNB Builder.exe` and select the folder you previously created.
3. If succeded, you will find your compiled files inside `/Final` folder.

### CLI support

If you prefer dealing with conversion using command line, *Fast XNB Builder* got you covered. Here are the following command line arguments you can use:

|Argument|Description|
|---|---|
|`/ui`|Shows an interface to select the folder containing the .X and it's textures.|
|`/f`|Converts a folder.|
|`/?`|Shows help.|