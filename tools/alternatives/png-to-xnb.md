---
layout: default
title: PNG to XNB
parent: Content packing tools
grand_parent: Tools
nav_order: 2v
last_modified_date: 2023-01-13 11:14
---

# PNG to XNB
{: #png-to-xnb .title }

is a tool for packing images (specifically PNG files) into XNB format, made by [**sullerandras**](https://github.com/sullerandras).<!-- more -->
{: .fs-6 .fw-300 }

[Download tool](https://github.com/sullerandras/png_to_xnb/releases/latest){: .btn .btn-blue }
[Go to repository](https://github.com/sullerandras/png_to_xnb){: .btn }

![Preview]({{ site.baseurl }}/images/PNGtoXNB.png)

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
            <th class="label-red">✖</th>
            <th class="label-red">✖</th>
        </tr>
    </tbody>
</table>

## Supported types
Supported images formats are: .png

## Usage
1. Open the "*png_to_xnb.exe*".
2. It will pop up a program with two input boxes, with two buttons each.
3. **Select "*File...*"** if you want to convert one image only, then navigate to your file and click on it; or **Select "*Folder...*"** if you want to convert multiple pngs from a folder, then navigate to your folder and click "OK".
4. Choose an output folder. If you have chosen a file instead, copy the filename and paste it in the "Output file" input boxes and change it the ending into `.xnb`.
5. Leave the `reach` radiobox.
6. Click "*Convert*".
7. Done!

### CLI support

```sh
png_to_xnb.exe [-h|--help] [-c] [-u] [-hidef] [-nopre] png_file [xnb_file]
```

The program reads the image 'png_file' and saves as an XNB file as 'xnb_file'.
Start without any input parameters to launch a GUI.

|Argument|Description|
|---|---|
|  `-h`     |Prints this help.|
|  `-c`     |Compress the XNB file. This is the default if xcompress32.dll is available. Note that the compression might take significant time, but of course the result XNB file will be much smaller.|
|  `-u`     |Save uncompressed XNB file, even if xcompress32.dll is available.
|  `-hidef` |XNB's can be either 'reach' or 'hidef'. Default is 'reach', so use this -hidef option when necessary. I don't know what 'reach' or 'hidef' means, but for example Terraria cannot load 'hidef' XNB files.|
|  `-nopre` |RGB channels will not be premultiplied by the alpha. By default, XNB's use premultiplied alpha.|

|`png_file` |This can either be a file or a directory. If this is a directory then it will convert all *.png files in the directory (not recursive).|
|`xnb_file` |This can also be a file or a directory. If this is a directory then the filename will be name.xnb if the image file was name.png.<br>If this is omitted then it converts the png_file into the same folder.|