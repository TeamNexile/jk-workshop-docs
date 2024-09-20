---
layout: default
title: Level&#58; First steps
parent: Getting started
nav_order: 4
last_modified_date: 2024-09-02 15:32
---

# First steps with levels
{: .no_toc }

Get your level set up for editing.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Creating a level

To create a level in Worldsmith, you'll need to:

1. Open [**Worldsmith** through Steam](steam://run/2245910).
   > If you do not find it in your library, head over in your Steam library, then on top-left you can find a dropdown and a search box.
   >
   > Either try **searching for "Jump King Worldsmith" in the search box**, or by clicking the dropdown, **select "Tools"** and Worldsmith will now appear in your sidelist like shown.
   >
   > ![Steam search box]({{site.baseurl}}/images/getting-started/worldsmith_steam_search.png){: width="50%" style="vertical-align:top;padding-right:0.5rem;" }![Steam dropdown]({{site.baseurl}}/images/getting-started/worldsmith_steam_dropdown.png){: width="50%" style="vertical-align:top;padding-left:0.5rem;" }
   {: .note }

2. Once opened, make sure you are in the home page of Worldsmith, this is what the page should roughly look like:

   ![Worldsmith home]({{site.baseurl}}/images/tools/worldsmith_home.png)

3. Click on **Create a new project**.
4. Worldsmith will ask you which item you'd want to create, select **Level** (this should already be selected by default) and click **Next**.

   ![Select level]({{site.baseurl}}/images/getting-started/worldsmith_select_level.png)

5. Once clicked Next, Worldsmith will ask you what you want to call your level (you can change this later) and where do you want to place it in your computer. Under **Name**, click on the input box and **write the name of your level**; and under **Folder**, click on the **folder icon** to select which folder to use for your item.
   > Make sure you create a new folder for your level or make sure the folder is empty before continuing! Worldsmith is **currently in development** and this is a temporary solution.
   {: .warning }
   ![Put name and folder]({{site.baseurl}}/images/getting-started/worldsmith_select_level_name_directory.png)

6. Click **Create!**, once clicked it Worldsmith will copy and build the default sample level in the directory chosen.

And that's it! You've successfully created your first level for Jump King.

## Testing your level

Testing your level is as simple as clicking a button.<br>At the bottom-right corner of Worldsmith (if you are making a level only), you will see a bright green button with the text "**Test in-game**".

![Test button]({{site.baseurl}}/images/getting-started/worldsmith_test_button.png)

By clicking it, Worldsmith should open Jump King.

> If this doesn't happen, tab into Steam and check if you had any prompts from Steam. Steam might ask you that Jump King is trying to open with optional parameters, this is necessary to enter the [Level Debug State](./#level-debug-state) set by Worldsmith, therefore click **Continue** and the game should open.
>
> ![Steam asks to open JK with parameters]({{site.baseurl}}/images/getting-started/steam_ask_open_jk.png)
{: .disclaimer }

### Level Debug State

The Level Debug State is a mode that you can enter through testing [with](./#testing-your-level) and [without](./#testing) Worldsmith that lets you easily look, test and play your level with some additions that help you out on the journey to make your level such as:

- drag your king around (left click to move the King, scroll wheel to change the screen),
- quick update to get the changes from Worldsmith,
- show your level's hitboxes,
- show your player's relative coordinates (relative to the screen) or absolute coordinates (relative to the first screen).

![Level debug state]({{site.baseurl}}/images/getting-started/level_debug_state.png)

---

<details class="expander">
   <summary markdown="1">
## Steps (without Worldsmith)
   </summary>

   <div markdown="1">

## Installation
{: .no_toc }

1. Extract the contents of the `Sample custom level` zip file in a folder you want.
   > Save it somewhere where you won't delete it by mistake and consider making backups every now and then!
   {: .warning }

2. You are set if you have a folder like the following (banner.png is optional):

   ![Level hierarchy]({{site.baseurl}}/images/getting-started/level_hierarchy.png)

> Before continuing, make sure you know how to get the path of your folder by: 
> - by right-clicking the sample level folder: `Properties > Security > Object name`
> - by opening the folder and clicking the bar on the left side of the searchbar
{: .disclaimer }

## Testing
{: .no_toc }

Take time testing your level. Have others also test your level to make sure you are achieving your intended experience. Here are some community [**tips**]({{ site.baseurl }}/level-making/tips){:target="_blank"}.

To test your level, you can choose two different approaches:

### Setting it up once
{: .no_toc }

Choosing this approach is easier for starters since **once it's setup all you need to do is open the game** but can be tedious if you want to test multiple levels since you will **always have to modify the launch options** through Steam. 

> If you want to **return to the base game**, remove everything from the **Launch options** and open the game.
{: .disclaimer }

1. Open Steam.
2. Right-click Jump King and click **Properties...**
3. In **General > Launch options** add: `-debug "DIRECTORY"`.
4. Replace `DIRECTORY` to the path of your sample level.

Once that's done, all you need to do is open the game and <u>it will automatically open your sample level all the times</u>!

### Setting it on-the-go
{: .no_toc }

Choosing this approach might be a bit more complicated since **you have to do the same procedure all the time**, but can be better if you are tinkering with multiple levels or you just **dont like to deal with the launch options**.

1. Open your browser of preference or <kbd>Ctrl</kbd>+<kbd>R</kbd> to open Windows Run.
2. Paste the following snippet and replace `DIRECTORY` with your sample folder's directory:
   ```
   steam://rungameid/1061090 -debug "DIRECTORY"
   ```
3. Press <kbd>Enter</kbd>.<br>
   > If you are on a browser, you might get a pop-up telling you that your browser wants to open Steam, let the browser allow you to open the game for you by clicking "Allow" or "Yes" depending by the browser.
   {: .disclaimer }

</div>
</details>


## Next up

Go to [**level details**]({{ site.baseurl }}/level-making) to learn how the configuration file works.
