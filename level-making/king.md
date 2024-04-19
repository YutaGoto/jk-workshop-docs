---
layout: default
title: King
parent: Level Making
nav_order: 6
last_modified_date: 2024-04-18 17:07
---

# King folder
{: .no_toc }

how to change the look for the player character.<!-- more -->
{: .fs-6 .fw-300 }

> By default, you must have a different *base file*.
{: .highlight }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## But what is this base file?

<style>
    .skewd {
        position: relative;
        width: 100%;
        padding-bottom: calc(46.1538461538% + 4px);
        transition: 0.5s;
        overflow: hidden;
    }
    .skewd:hover {
        padding-bottom: calc(51% + 4px);
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
        transform: translateY(11.1%);
    }
</style>

<div class="skewd">
    <img src="{{ site.baseurl }}/images/level-making/king/sprite_grid.png" title="Grid" alt="Grid">
    <img src="{{ site.baseurl }}/images/level-making/king/base.png" title="Base" alt="Base">
</div>

The base file is a packed image file that contains every Jump King (jumping, falling, walking, dancing, you name it) and babe's ending textures.

## Base

### Replacing the base

1. Navigate to the **Wardrobe** page.
2. Expand the **Preview spritesheet** tab.

    ![Preview spritesheet]({{ site.baseurl }}/images/level-making/king/base_preview.png)

3. Click on the **Change base** button found in the bottom-right corner of the tab. A prompt will show up asking you to select a new base.

    ![Replace base]({{ site.baseurl }}/images/level-making/king/base_replace.png)

4. After clicking **Open**, your base should have updated.

    ![Base successfully replaced]({{ site.baseurl }}/images/level-making/king/base_success.png)

> If you've lost the original base or wanted to roll back to the original one: [here's the original base]({{ site.baseurl }}/images/level-making/king/base.png){: target="_blank"}.
{: .note }

> If you want to branch out from the classic look and go for a more customized experience, you also [use the grid]({{ site.baseurl }}/images/level-making/king/sprite_grid.png){: target="_blank"} to create a new base and other textures too.
{: .disclaimer }

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

### Replace or delete existing base
{: .no_toc }

If you are just getting started, you should:

1. Save [the base image]({{ site.baseurl }}/images/level-making/king/base.png){: target="_blank"} by right-clicking it.
2. Modify as you will.
3. Convert the image file you worked on into a packed XNB file naming it `base`.
4. Replacing the already existing base file in the `king` folder.

</div>
</details>

## Items

Other than the base texture, you can also decide to customize all the other wearable items from the [item's list]({{ site.baseurl }}/api/items){: target="_blank"}.

> Making custom textures is the same process as making single skins without making the XML files; you need a image editor that supports at least three layers. In the first layer you will need to put the grid, in the second the base of your choice, and in the third your item texture.

Once you are satisfied with your item texture, you can decide to add it onto your level.

<!-- ### Adding/replacing/deleting a custom texture (with Worldsmith) 

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Replacing an item's texture

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Wardrobe".
3. Expand both the **Customized** and the **Default** tabs to find your item.
4. Once found, hover on its name/sprite to show up further settings:

    ![Hover on skin]({{ site.baseurl }}/images/level-making/king/skin_hover.png)

5. Click on **Replace**. A prompt will show up asking you to select the new worlditem's texture.

   ![Replace skin texture]({{ site.baseurl }}/images/level-making/king/skin_replace.png)

6. After clicking **Open**, your worlditem should have changed sprite!

   ![Successfully changed worlditem]({{ site.baseurl }}/images/level-making/king/skin_success.png)

### Rolling back the original texture of an item

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Wardrobe".
3. Expand the **Customized** tab to find your item.
4. Once found, hover on its name/sprite to show up further settings:

    ![Skin rollback]({{ site.baseurl }}/images/level-making/king/skin_rollback.png)

5. Click on the red button with the tooltip "Bring back the original look".
6. Your item should now look like the game's default. (It should be now available in the *Default* tab instead)

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

### Adding/replacing a custom texture 
{: .no_toc }

1. Convert the image file you worked on into a packed XNB file.
2. Look out for your **Item** name in the [Items List]({{ site.baseurl }}/api/items){: target="_blank"}.
3. Open the `skin_settings.xml` and search for the **Item** name.
4. Use the name you will find in the `texture` tag where you found your Item for your texture. If the file is already existing, replace the file.

### Deleting a custom texture
{: .no_toc }

1. Look out for your **Item** name in the [Items List]({{ site.baseurl }}/api/items){: target="_blank"}.
3. Open the `skin_settings.xml` and search for the **Item** name.
4. Delete the file that is called as the `texture` tag where you found your Item.

</div>
</details>

## Next up

Modifying [**Audio**]({{ site.baseurl }}/level-making/audio).