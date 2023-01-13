---
layout: default
title: Monogame Pipeline
parent: Content packing tools
grand_parent: ✔ Tools
nav_order: 10
last_modified_date: 2023-01-13 16:45
---

# Monogame Pipeline

is the official tool used by Nexile to mass-compile all the content for the game.
{: .fs-6 .fw-300 }
<!-- more -->

{: .disclaimer }
> Not recommended. This takes a lot in both space on your drive and time. Choose only if this is your last hope.

[Download steps](#usage){: .btn .btn-blue }

![Preview](https://docs.monogame.net/images/MGCB-editor.png)

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
Everything that is compatible with Monogame (and so Jump King).

## Usage
1. Install the latest version of Visual Studio Community available.
2. Download *.NET desktop development* and all of its dependencies.
3. [**Follow these instructions**](https://docs.monogame.net/articles/getting_started/1_setting_up_your_development_environment_windows.html#install-monogame-extension-for-visual-studio-2019){:target="_blank"} (from __Install MonoGame extension for Visual Studio 2019__ to __Install MGCB Editor__ included!).
4. Reopen and create a new project in Visual Studio with the template: ![Project](https://docs.monogame.net/images/getting_started/vswin-mg-new-2.png) (the project name does not matter)
5. On the right side of the screen (Solution Explorer), open the folder Content and open the file `Content.mgcb`. If you have installed MGCB Editor this will show up: ![MGCBE](https://docs.monogame.net/images/MGCB-editor.png)
    Otherwise, you can search the application through Windows and open the MGCB file manually.
6. To add convert images and audio files you need to add files using the rectangle with a yellow asterisk with tool tip saying Add Item.
7. Select all the items you have to convert.
8.  Save the Content file and click on the **Build** icon.

Once the build is complete, you will find all your packed files in: `project directory/bin/x86/Debug/Content/`.