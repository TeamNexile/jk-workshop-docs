---
layout: default
title: King
parent: Level Making
nav_order: 6
last_modified_date: 2022-12-19 14:05
---

# Custom King textures

a different look for the King!<!-- more -->
{: .fs-6 .fw-300 }

By default, you must have a different *base file*.

But what is this base file?
{: .text-gamma }

<style>
    .skewd {
        position: relative;
        width: 100%;
        padding-bottom: calc(75% + 4px);
        transition: 0.5s;
        overflow: hidden;
    }
    .skewd:not(:hover) img {
        opacity: 1;
    }
    .skewd:hover img:not(:hover) {
        opacity: 0.1;
        filter: grayscale(0.6);
        border-left-color: black;
    }
    .skewd img {
        position: absolute;
        width: 100%;
        transition: .5s;
        opacity: 1;
        border: solid 2px transparent;
    }
    .skewd img {
        width: 100%;
    }
    .skewd img:hover {
        opacity: 1;
        border-color: red;
    }
    .skewd:hover img:nth-child(2) {
        transform: translate(11.1%);
    }
    .skewd:hover img:nth-child(3) {
        transform: translate(22.2%);
    }
    .skewd:hover img:nth-child(4) {
        transform: translate(33.3%);
    }
    .skewd:hover img:nth-child(5) {
        transform: translate(44.4%);
    }
</style>


<div class="skewd">
    <img src="{{ site.baseurl }}/images/level-making/king/base.png" alt="Base">
    <img src="{{ site.baseurl }}/images/level-making/screens/masked.png" alt="Base">
</div>
![Base]()

The base file is a packed image file that contains every Jump King (jumping, falling, walking, dancing, you name it) and babes texture.

