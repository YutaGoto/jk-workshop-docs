---
layout: default
title: Mod Making
has_children: true 
has_toc: false # true if you want the list of subpages
nav_order: 10
last_modified_date: 2024-04-16 15:07 # remember to change this when updating a file (just for UI effect)!
---

<!-- your content -->

# Mod Making
{: .no_toc}
<!-- the .no_toc class prevents to add the title to the following table of contents -->

**everything** you need to know to make a mod.<!-- more -->
{: .fs-6 .fw-300 }

<!-- more -->
<!-- cuts text for "seo"/embed -->

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

> Making a mod for Jump King requires **<u>at least</u>** a basic programming background!<br>**This is not made for starters!**
{: .warning }

## Getting started
Jump King has a world of modding capabilities, and as part of the Workshop update we have refactored and exposed a series of game systems to support the creation of mods. A mod for Jump King can be split broadly into three categories:
- Custom Content (Maps, Sprites, Sounds)
- Custom Blocks (New block types used by custom maps)
- Custom Behaviours (New game modes or in-game functionality)

The mods you create may end up being a combination of these three categories. Here we will run you through the authoring process for creating some simple options to get you on your way to making your first mod.

## Setting up Mod Projects

Mods that contain custom blocks and/or behaviours will be comprised of a C# project that outputs a Library (.dll), targeting .NET Framework 4.5. If you are using Visual Studio it is advised to use Visual Studio 2022. If you cannot use Visual Studio 2022 and you are on a previous version, read [how to manually set up your project](#manual-setup-visual-studio-2022-or-previous).

### Jump King Mod Template (Visual Studio 2022)
The 'Jump King Mod Project' template will streamline the process of setting up your mod. This template will only function on Visual Studio 2022 or newer, there is a [free version of Visual Studio](https://visualstudio.microsoft.com/vs/community/) available for everyone.

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

## How a mod works under the hood

Your project has a single entry point, denoted by the `[JumpKingMod]` attribute affixed to a static class. This attribute should contain a unique name to identify your mod, this will help you debug any errors that may arise during the authoring of your work.

```cs
using JumpKing.Mods;

namespace MyCoolMod
{
    [JumpKingMod("MyName.MyCoolMod")]
    public static class MyCoolMod
    {
    }
}
```

This attribute is what tells Jump King where to look to find the 'setup' logic for your mod. From here there are four potential entry points you can register to, which you can use to set up and plug in your systems. This is done through the use of some additional attributes. When loading your mod, Jump King will note which methods contain these attributes and call them at the appropriate time.
- **BeforeLevelLoadAttribute** - Called before Jump King attempts to load the data for the game. You should use this entry point for the registration of any custom blocks or for any logic that the level relies on.
- **OnLevelUnloadAttribute** - Called when the player swaps to a new map to allow you to unload any data or unregister behaviours that are no longer needed. Eg, if a player started a base game map, but then changes to a Workshop map, or swaps between workshop maps.
- **OnLevelStartAttribute** - Called when a Level is loaded and the player has been created, but before the user gets a chance to see/act on anything. You should use this entry point for the registration of any behaviours that will affect the player.
- **OnLevelEndAttribute** - Called when the player stops playing a Level and moved back to the Main Menu, whether this be through the pause menu or by beating the map.

A mod making use of these attributes would look like this:
```cs
using JumpKing.Mods;

namespace MyCoolMod
{
    [JumpKingMod("MyName.MyCoolMod")]
    public static class MyCoolMod
    {
        [OnLevelStart]
        public static void OnLevelStart()
        {
            // Get the player
            PlayerEntity player = EntityManager.instance.Find<PlayerEntity>();

            // Do something...
        }
    }
}
```

A project/mod should have a single entry point, but it can be used to setup whatever suite of behaviours and logic your mod requires! 

### Debugging & Testing
In order to test your mod locally, you need only build it into a .dll, and then place this file (and any dependencies!) in the /Content/JKMods/ folder in your Jump King game's Steam install directory. It will now be loaded when the game is ran.

> If using Visual Studio, you can attach a debugger to the Jump King game directly to breakpoint and navigate through any of your custom code when it is loaded.

> If you're struggling - you can add `Debugger.Launch()` to your mod temporarily, which will prompt you to attach a debugger instance to the game when it is hit.

Additional logs about the game's `ModLoadLog.txt` and `crashlog.log` files respectively, which should both be found next to the JumpKing.exe

## Further Reading
- [Player Behaviour]({{site.baseurl}}/mod-making/player-behaviour)
    - A rundown on how the Player functions within Jump King and how you can interface with it using your mod
- [Collision Info]({{site.baseurl}}/mod-making/collision-info)
    - A rundown on how the Player collides within Jump King and how you can interface with it using your mod
- [Block Behaviours]({{site.baseurl}}/mod-making/block-behaviours)
    - A rundown on how blocks can influence how the player behaves in Jump King
- [Advanced Modding using Harmony]({{site.baseurl}}/mod-making/harmony)
    - A brief introduction into 'Harmony' - an open source library that can help you make more advanced mods