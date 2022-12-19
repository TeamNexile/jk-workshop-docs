---
layout: default
title: XNBCLI
parent: Tools
nav_order: 2
---

# XNBCLI <a target="_blank" title="Download tool" href="https://github.com/LeonBlade/XNBCLI/releases/latest"><ion-icon name="download"></ion-icon></a><a title="Go to repository" target="_blank" href="https://github.com/LeonBlade/XNBCLI"><ion-icon name="logo-github"></ion-icon></a>
{: #xnbcli .title }

is a CLI tool for XNB packing/unpacking purpose built for Stardew Valley (but works for Jump King too!), made by [**LeonBlade**](https://github.com/LeonBlade).
{: .fs-6 .fw-300 }

This program can be used in command line only, but there are two batch files that help you out so you don't have to do anything in command line.<!-- more -->

> Command line usage is:
    <br>`xnbcli pack input-file output-file` - to pack a file
    <br>`xnbcli unpack input-file output-file` - to unpack a file

## Supported types
Supported images formats are: .png, .bmp and more.

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
            <th style="background-color: lightgreen;">✔</th>
            <th style="background-color: lightgreen;">✔</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">sound</th>
            <th style="background-color: lightcoral;">✖</th>
            <th style="background-color: lightcoral;">✖</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">font</th>
            <th style="background-color: lightcoral;">✖</th>
            <th style="background-color: lightcoral;">✖</th>
        </tr>
    </tbody>
</table>

## Usage 
0. Install prerequisites of XNBCLI available [here](https://github.com/LeonBlade/xnbcli/blob/master/README.md).
1. Download the latest release for XNBCLI in the links above.
2. Export the `xnbcli-windows-x64.zip` file.

### Unpack images (from XNB to image file)
If you want to unpack an image from the game, put the file inside the `packed` folder and open the `unpack.bat`. If succeeded, you will find your files inside the `unpacked` folder.

### Pack images (from image file to XNB)
If you want to pack an image to put on the mod, make sure you have the .json file of your file ready to get packed with your image. If you never unpacked an image you can use this simple .json and modify for your own use! 

<span>YOURFILENAMEHERE.json&nbsp;&nbsp;<a class="button transparent small" href="https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/YOURFILENAMEHERE.json"><ion-icon name="code-download"></ion-icon> Download</a></span>
```json
{
    "header": {
        "target": "w",
        "formatVersion": 5,
        "hidef": false,
        "compressed": false
    },
    "readers": [
        {
            "type": "Microsoft.Xna.Framework.Content.Texture2DReader",
            "version": 0
        }
    ],
    "content": {
        "format": 0,
        "export": "YOURFILENAMEHERE.png"
    }
}
```

Once put your image inside the `unpacked` folder with the .json file, you can open the `pack.bat`. And if succeeded, you managed to create your very own custom texture! The packed file can be found inside the `packed` folder.