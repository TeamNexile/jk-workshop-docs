---
layout: default
title: PNG to XNB
parent: Content packing tools
grand_parent: Tools
nav_order: 3
last_modified_date: 2023-01-11 16:26
---

# PNG to XNB
{: #png-to-xnb .title }

is a tool for packing images (specifically PNG files) into XNB format, made by [**sullerandras**](https://github.com/sullerandras).
{: .fs-6 .fw-300 }

[Download tool](https://github.com/sullerandras/png_to_xnb/releases/latest){: .btn .btn-blue }
[Go to repository](https://github.com/sullerandras/png_to_xnb){: .btn }

![Preview](/images/PNGtoXNB.png)

---

Supports batch conversion, but has an executable for ease of use.<!-- more -->

> Command line usage is:
    <br>`/path/to/png_to_xnb.exe item.png item.xnb` to convert the image into XNB

## Supported types
Supported images formats are: .png

## Table of usage
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
            <th class="label-red">✖</th>
            <th class="label-red">✖</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">font</th>
            <th class="label-red">✖</th>
            <th class="label-red">✖</th>
        </tr>
    </tbody>
</table>

## Usage
1. Open the "*png_to_xnb.exe*".
2. It will pop up a program with two input boxes, with two buttons each.
3. **Select "*File...*"** if you want to convert one image only, then navigate to your file and click on it; or **Select "*Folder...*"** if you want to convert multiple pngs from a folder, then navigate to your folder and click "OK".
4. Choose an output folder. If you have chosen a file instead, copy the filename and paste it in the "Output file" input boxes and change it the ending into `.xnb`.
5. Leave the `reach` radiobox.
6. Click "*Convert*".
7. Done!