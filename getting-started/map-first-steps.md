---
layout: default
title: Level&#58; First steps
parent: Getting started
nav_order: 3
last_modified_date: 2023-03-24 13:32
---

# First steps with levels<!-- more -->
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Installation


1. Extract the contents of the `Sample custom level` zip file in a folder you want.
   > Save it somewhere where you won't delete it by mistake!
   {: .warning }
2. You are set if you have a folder like the following:

   ![Level hierarchy]({{site.baseurl}}/images/getting-started/level_hierarchy.png)

> Before continuing, make sure you know how to get the path of your folder by: 
> - by right-clicking the sample level folder: `Properties > Security > Object name`
> - by opening the folder and clicking the bar on the left side of the searchbar
{: .disclaimer }

## Testing

Take time testing your level. Have others also test your level to make sure you are achieving your intended experience. Here are some community [**tips**]({{ site.baseurl }}/level-making/tips){:target="_blank"}.

To test your level, you can choose two different approaches:

### Setting it up once

Choosing this approach is easier for starters since **once it's setup all you need to do is open the game** but can be tedious if you want to test multiple levels since you will **always have to modify the launch options** through Steam. 

> If you want to **return to the base game**, remove everything from the **Launch options** and open the game.
{: .disclaimer }

1. Open Steam.
2. Right-click Jump King and click **Properties...**
3. In **General > Launch options** add: `-debug "DIRECTORY"`.
4. Replace `DIRECTORY` to the path of your sample level.

Once that's done, all you need to do is open the game and <u>it will automatically open your sample level all the times</u>!

### Setting it on-the-go

Choosing this approach might be a bit more complicated since **you have to do the same procedure all the time**, but can be better if you are tinkering with multiple levels or you just **dont like to deal with the launch options**.

1. Open your browser of preference or <kbd>Ctrl</kbd>+<kbd>R</kbd> to open Windows Run.
2. Paste the following snippet and replace `DIRECTORY` with your sample folder:
   ```
   steam://rungameid/1061090 -debug "DIRECTORY"
   ```
3. Press <kbd>Enter</kbd><br>.
   > If you are on a browser, you might get a pop-up telling you that your browser wants to open Steam, let the browser allow you to open the game for you by clicking "Allow" or "Yes" depending by the browser.
   {: .disclaimer }

## Next up

Go to [**level details**]({{ site.baseurl }}/level-making) by learning to learn how the configuration file works.
