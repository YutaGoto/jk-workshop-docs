---
layout: default
title: Hitboxes
parent: Level Making
nav_order: 1
last_modified_date: 2024-04-15 15:09
---

# Hitbox file
{: .no_toc }

is a PNG image with transparency that is used to determine the custom level gameplay.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Understanding the basics of hitboxes

The hitboxes are determined by the pixels that you will draw on the image file, each color has a different use and logic that can be used for plentiful of platforming or behaviours.

<figure class="mb-5">
   <img src="{{ site.baseurl }}/images/level-making/hitboxes.png" alt="Completion on tool">
   <figcaption class="text-grey-dk-000 text-epsilon">Blocks will be explained in the <a href="{{site.baseurl}}/level-making/blocks">Block</a> page. This is just an example of a platform.</figcaption>
</figure>

### Level image

This image file (called level) can be found in the root folder of your level.
The level file resolution **needs to be specifically 780 by 585 pixels** because the game needs a grid (13 columns by 13 rows) to determine the hitboxes for each screen.

<details class="expander">
   <summary markdown="1">
### Level image not found (using Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">
1. Open your project.
2. Navigate to the **Hitboxes** page.

   ![Hitbox page]({{site.baseurl}}/images/level-making/worldsmith_hitboxes.png)

3. Your file will be generated now, you can click on the button with folder icon to open your level's folder. 

   ![Hitbox page]({{site.baseurl}}/images/level-making/worldsmith_hitboxes_folder.png)

</div>
</details>

<details class="expander">
   <summary markdown="1">
### Level image not found (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">
In order to have a full-functioning hitbox an image file you will need to create a file with the following details:

|Requirements|Details|
|---|---|
|File name|level|
|Resolution|**780** pixels (*width*) by **585** pixels (*height*)|
|File placement|Root of the level folder|

</div>
</details>

Here's an example of how hitboxes look on the level image file:

![Hitbox Example](https://raw.githubusercontent.com/JumpKingPlus/JumpKingPlus.github.io/www/workshop/files/level.png)

> From the example shown, **every screen is ordered by column starting from top to bottom**.
{: .highlight }

### Visual level image (Worldsmith only!)

If you are using Worldsmith, you will also find a visual_level file in your level's folder.
The visual_level file resolution **needs to be specifically 60 by 7605 pixels**, 1 column with 169 rows.
This should be the same as your level file but reorganized in a more "usable" state.

Since Jump King uses the level file, **Worldsmith will automatically build the level file for you**.

Here's an example of how hitboxes look on the visual_level image file:

![Hitbox Example]({{site.baseurl}}/images/level-making/visual_level.png)

> From the example shown, **every screen starts from bottom to top**.
{: .highlight }

### Common similarities

Regardless their differences, both level and visual_level images share some common similarities:

- **Each screen** is sized <u>60 by 45 pixels</u> meaning that 1 pixel on the hitbox equals to 8 pixels in-game. (since the screen size for other details is 480 by 360 pixels).
- The current total amount of possible screens is 169.

> **Take in mind what the screen number is from the examples above, since this <u>will get heavily used</u> in the next chapters.**
{: .disclaimer }

> Following the common screen size, you can add an helper grid (with whatever tool you chose to draw hitboxes) to help you find easily the hitbox of your screen without overflowing into a new one.
{: .note }

## Modifying the hitboxes

1. Open your visual_level file with your pixel-art software of choice. You can easily open its folder by [**clicking the folder button in the Hitboxes page**](./#level-image-not-found-using-worldsmith).

2. Edit your hitboxes freely.

3. Once you've deemed it worth a try, **save** your changes using your pixel-art software of choice. Once saving, Worldsmith should be automatically building your hitboxes.

4. If you have the game closed, click **Test In-game** in the bottom-right corner of Worldsmith.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

1. Open the file [you've created above](#understanding-the-basics-of-hitboxes) or unpack existing hitboxes and open it using your tool of choice.
2. Use the [**block page as a cheat sheet**]({{site.baseurl}}/level-making/blocks){:target="_blank"} or put it page aside your pixel-art program of your choice for reference (you should start with starter blocks only!).
3. Start drawing your hitboxes!
    > Don't forget to add a solid block bottom line on the first screen otherwise you will fall endlessly and you are basically forced to restart or teleport.
    {: .warning }
4. Once you are satisfied or you want to give it a test, save the image file.
5. Convert/Pack the image into XNB with the tool of your choice.
6. Place it in the folder of your level. If asked to replace the file, click **Yes**.
7. [Give it a test!]({{site.baseurl}}/getting-started/map-first-steps#testing).

</div>
</details>

> If your game was already open from testing your level before, simply navigate to the pause menu and click **Update** and the new hitboxes should show up.
{: .note }

## Next up

> Even if the details you have planned look good, what matters more is the quality and fair of your hitboxes. Please give a read to [some tricks and tips]({{site.baseurl}}/level-making/tips) from JumpKingPlus' veterans.
{: .note }

Read up on [**Starter Blocks**]({{site.baseurl}}/level-making/blocks/#blocks-for-new-users) then head to [**Screens**]({{site.baseurl}}/level-making/screens/).