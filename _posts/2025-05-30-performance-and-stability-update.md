---
layout: post
author: Phoenixx19
title: Performance & Stability Update
date: 2025-05-30
---

## Worldsmith

The main focus in this update is to bring **general performance** and **stability issues** related to Worldsmith to make the process of making your custom content less slow and more enjoyable!

### Quality of Life additions

- Improvements on how "Load an existing folder" prompt works: 
      - Added a new checkbox to determine which folder to load from (Worldsmith's default or custom).
      - The prompt will not display if the folder does not exists.
      - Fixed a bug where writing the title of the loaded item BEFORE the item name would cause the folder directory to be changed.
- Improvements on how "Start position" works:
      - Fixed a bug where the start position would not save changes. *(thanks to Czar!)*
      - Moved start position from the Item Details page to the Screens page for ease of use and overall better experience; the position inside of the Screens page will be relative rather than the final value (that is absolute).
      - You can now visually see the start position inside of the Screens page.
- Improvements on how babes and their ending images works:
      - Revamped slighly how the UI looks in the ending details expanders.
      - Moved babe screens from the Item Details page to the Screens page for ease of use and overall better experience.
      - Fixed a bug where changing any babe screens would not save changes.
      - Fixed a bug where changing ending images would not save changes.
      - You can now add, move and/or remove a babe directly in the screen page.
- New awesome Worldsmith icon!
- Minor improvements with scrolling images over performance.

### Fixes

- Fixed freezes and crashes related a lot of sprites in one screen.
- Fixed level flags not changing on file when adding or removing. *(thanks to Cloudy & Czar!)*
- Fixed a crash when loading a different project. *(thanks to IntroCar!)*
- Fixed Hidden Walls sizing and scrolling image previews crashing if the velocity is set to 0.
- Fixed custom Wardrobe base not loading on first load.
- Fixed position offset of scrolling images.
- Fixed velocity calculations of scrolling images.
- Fixed static animations for scrolling images (without using floats).
- Fixed hidden walls not displaying correctly in Screen page.
- Fixed Worldsmith versioning in settings.
- Fixed an internal bug where the item settings would save recursively.
- Fixed a crash when trying to go up/down a screen in the Screen page. *(thanks to Czar!)*
- Fixed a bug where you couldn't add the same prop twice. *(thanks to Czar!)*
- Fixed a bug where the taskbar would display with a progress bar all the time after building content. (green background bar on windows 10, long progress bar on windows 11)
- Fixed a bug where a prompt issue dismisses a previously opened prompt
- Removed some unused assets.