---
layout: default
title: Mod&#58; First steps
parent: Getting started
nav_order: 7
last_modified_date: 2024-09-03 16:21
---

# First steps with mods
{: .no_toc }

Get your mod set up for editing.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Introduction

Jump King has a world of modding capabilities, and as part of the Workshop update we have refactored and exposed a series of game systems to support the creation of mods. A mod for Jump King can be split broadly into three categories:
- Custom Content (Maps, Sprites, Sounds)
- Custom Blocks (New block types used by custom maps)
- Custom Behaviours (New game modes or in-game functionality)

The mods you create may end up being a combination of these three categories. Here we will run you through the authoring process for creating some simple options to get you on your way to making your first mod.

## Getting started

> It is **mandatory** to install the SDK to target on .NET Framework 4.5, you can easily follow these steps in this [StackOverflow's post](https://stackoverflow.com/a/70109092){: target="_blank" }.
>
> <details class="expander" style="margin-bottom:0">
> <summary>Steps if the website is unavailable</summary>
> <div markdown="1">
>
> 1. Download [Microsoft.NETFramework.ReferenceAssemblies.net45](https://www.nuget.org/packages/microsoft.netframework.referenceassemblies.net45){: target="_blank" } from nuget.org
> 2. Open the package as zip (or rename the package file and change its extension from .nupkg to .zip then open it)
> 3. Copy the files from `build\.NETFramework\v4.5\` to `C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.5`
> 4. Close Visual Studio and then reopen it
>
> </div>
> </details>
{: .warning }

## Setting up Mod Projects

Mods that contain custom blocks and/or behaviours will be comprised of a C# project that outputs a Library (.dll), targeting .NET Framework 4.5. 

To create a mod in Worldsmith, you'll need to:

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
4. Worldsmith will ask you which item you'd want to create, select **Mod** and click **Next**.

   ![Select mod]({{site.baseurl}}/images/getting-started/workshop_select_mod.png)

5. Once clicked Next, Worldsmith will ask you what you want to call your mod (you can change this later) and where do you want to place it in your computer. Under **Name**, click on the input box and **write the name of your mod**; and under **Folder**, click on the **folder icon** to select which folder to use for your item.
   > Make sure you create a new folder for your mod or make sure the folder is empty before continuing! Worldsmith is **currently in development** and this is a temporary solution.
   {: .warning }
   ![Put name and folder]({{site.baseurl}}/images/getting-started/worldsmith_select_mod_name_directory.png)

6. Click **Create!**, once clicked it Worldsmith will generate the default sample mod in the directory chosen.

7. Once created, the Worldsmith footer will display three buttons: click on the yellow-filled with the Visual Studio logo on it with the text "*Open*".

    ![Left footer]({{site.baseurl}}/images/getting-started/worldsmith_footer_left.png)

8. Once Visual Studio opened, build the solution by clicking `Build` then `Build Solution` (or more precisely `Build NAMEOFYOURPROJECT`, in this scenario they are both the same).

    ![Build solution]({{site.baseurl}}/images/getting-started/vs2022_howto_build.png)

If the footer of Visual Studio or the Output says "Build succeeded" like in the picture below, you have successfully created and built your first mod for Jump King.

![Build successful]({{site.baseurl}}/images/getting-started/vs2022_build_success.png)

<details class="expander">
   <summary markdown="1">
## Alternatives to Worldsmith
   </summary>
   <div markdown="1">

If Worldsmith is not for you, there are two alternatives you can choose from. Although not recommended, these are always viable alternatives.

It is advised to use Visual Studio 2022. If you cannot use Visual Studio 2022 and you are on a previous version, read [how to manually set up your project](#manual-setup-visual-studio-2022-or-previous).

### Jump King Mod Template (Visual Studio 2022)

The 'Jump King Mod Project' template will streamline the process of setting up your mod. This template will only function on Visual Studio 2022 or newer, there is a [free version of Visual Studio](https://visualstudio.microsoft.com/vs/community/) available for everyone.

This is what Worldsmith uses under the hood to create your mod projects.

[Download Jump King Mod Template]({{ site.baseurl }}/files/JumpKingModProjectTemplateWizard.vsix){: .btn .btn-blue } v1.0.0 - 28/02/2024

Once installed you can select the Jump King Mod Project template when creating your project.

![Select the "Jump King Mod" template]({{ site.baseurl }}/images/mod-making/image-6.png)

![Name your Mod project]({{ site.baseurl }}/images/mod-making/image-7.png)

You will get a pop-up from the "Jump King Mod Project Wizard" asking you to point it to the location of your Jump King game. This is so it can properly set up your project.

![Input the path to your Jump King game and click 'OK'. Click the '...' button for easier selection]({{ site.baseurl }}/images/mod-making/image-8.png)

Once complete your project will open! Be sure to update the text inside the `JumpKingMod` attribute to something more fitting for your mod.

![Update the 'JumpKingMod' attribute, and get coding!]({{ site.baseurl }}/images/mod-making/image-9.png)

<details class="expander">
   <summary markdown="1">
### Manual Setup (Visual Studio 2022 or previous)
   </summary>
   <div markdown="1">

1. Select the "Class Library (.NET Framework)" option from the Visual Studio templates. 

    ![Select the "Class Library (.NET Framework)" option from the Visual Studio templates]({{ site.baseurl }}/images/mod-making/image-1.png)

2. Name your project and ensure it is targeting .NET Framework v4.5

    ![Name your project and ensure it is targeting .NET Framework v4.5]({{ site.baseurl }}/images/mod-making/image-2.png)

3. To make use of the attributes and types referenced by Jump King you will need to add it as a reference to your project, how to do this varies depending on your IDE of choice. For Visual Studio, go to the Solution Explorer and right click on the 'References' option underneath your project and select 'Add Reference', then select the 'Browse...' button in the bottom right and navigate to the JumpKing.exe in your Steam install directory.

4. Right click on 'References' under your project in the Visual Studio Solution Explorer and select 'Add Reference...'

    ![Right click on 'References' under your project in the Visual Studio Solution Explorer and select 'Add Reference...']({{ site.baseurl }}/images/mod-making/image-3.png)

5. Select 'Assemblies' then click 'Browse' in the bottom right

    ![Select 'Assemblies' then click 'Browse' in the bottom right]({{ site.baseurl }}/images/mod-making/image-4.png)

6. Navigate to your Jump King install directory and include JumpKing.exe and MonoGame.Framework.dll

    ![Navigate to your Jump King install directory and include JumpKing.exe and MonoGame.Framework.dll]({{ site.baseurl }}/images/mod-making/image-5.png)

</div>
</details>

### Debugging & Testing (without Worldsmith)

For both alternatives to Worldsmith, the debugging & testing part is somewhat the same and is as follows.

In order to test your mod locally, you need only build it into a .dll, and then place this file (and any dependencies!) in the /Content/JKMods/ folder in your Jump King game's Steam install directory. It will now be loaded when the game is ran.

</div>
</details>

## Debugging & Testing

After you have built your project, you might want to test it in-game to see if it works properly. To do so, tab back into Worldsmith.

In the same footer you've used to open the project in Visual Studio/VSCode, on the other side you might find a button labelled "*Debug in-game*".

![Debug in-game]({{site.baseurl}}/images/getting-started/worldsmith_footer_right.png)

By clicking on it, Worldsmith will **copy the Debug build files onto the local mods folder** that Jump King reads on start-up and will **start Jump King for you**, avoiding copy-pasting files that the other two alternatives will have to go through.

### Debugging tips

> If using Visual Studio, you can attach a debugger to the Jump King game directly to breakpoint and navigate through any of your custom code when it is loaded.

> If you're struggling - you can add `Debugger.Launch()` to your mod temporarily, which will prompt you to attach a debugger instance to the game when it is hit.

Additional logs about the game's `ModLoadLog.txt` and `crashlog.log` files respectively, which should both be found next to the JumpKing.exe

## Next up

Learn how a Mod Project is tied to Jump King and learn what attributes are for on the [**mod making**]({{ site.baseurl }}/mod-making) page.