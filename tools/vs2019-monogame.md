---
layout: default
title: VS2019 + Monogame
parent: Tools
nav_order: 10
---

# Visual Studio 2019 and Monogame
Not recommended. This takes a lot in both space on your drive and time. Choose only if this is your last hope.
{: .fs-6 .fw-300 }
<!-- more -->

> Warning!
    <br>Converting fonts has not been fully tested and might end up not working.

## Supported types
Everything compatible with Monogame (and so Jump King).

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
            <th class="label-green">✔</th>
            <th class="label-red">✖</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">font</th>
            <th class="label-green">✔</th>
            <th class="label-red">✖</th>
        </tr>
    </tbody>
</table>

## Usage
1. Install Visual Studio Community 2019.
2. Download *.NET desktop development*.
3. Install MonoGame from the official website.
4. [**Follow these instructions**](https://docs.monogame.net/articles/getting_started/1_setting_up_your_development_environment_windows.html#install-monogame-extension-for-visual-studio-2019) (from __Install MonoGame extension for Visual Studio 2019__ to __Install MGCB Editor__ included!).
5. Reopen and create a new project in Visual Studio with the template: ![Project](https://docs.monogame.net/images/getting_started/vswin-mg-new-2.png) (the project name does not matter)
6. On the right side of the screen (Solution Explorer), open the folder Content and open the file `Content.mgcb`. If you have installed MGCB Editor this will show up: ![MGCBE](https://docs.monogame.net/images/MGCB-editor.png)
7. To add convert images, audio files and fonts you need to add files using the rectangle with a yellow asterisk with tool tip saying Add Item.
8. Select all the items you have to convert. To convert fonts, [__follow these instructions__](https://stackoverflow.com/questions/55045066/how-do-i-convert-a-ttf-or-other-font-to-a-xnb-xna-game-studio-font).
9. Save the Content file and build it.
10. You will find all your packed file in: `project directory/bin/x86/Debug/Content/`.