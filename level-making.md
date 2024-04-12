---
layout: default
title: Level Making
has_children: true
has_toc: false
nav_order: 7
last_modified_date: 2023-04-12 17:18
---

# Level Making
{: .no_toc }

**everything** you need to know to make a custom level.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

{: .warning }
> **All the changes you make on your level will be available only to you until you decide to [upload]({{ site.baseurl }}/publishing/#publishing-your-item) your Workshop item. Every further modification needs an [update]({{ site.baseurl }}/updating/#updating-your-item) to your Workshop item to be available to everyone that is subscribed to your item.**

## Change your level title

The level title is the text that gets shown in-game when paused, inside your Worldsmith project, in your item's workshop page and in the Workshop overall (once released public).

To change your level's title:
1. Open Worldsmith through Steam and open your level project from the recents or favorites list.
    > If you can't find your project in your recents/favorites list and you know where it's placed in your drive, click on **Load an existing project** and follow the instructions on screen.
    {: .note }

2. Once clicked, you'll see the title of your level in the header of Worldsmith, this means your project has been opened in Worldsmith. Some pages will show up on the sidebar now like in the image below.

    ![Opened project]({{ site.baseurl }}/images/level-making/worldsmith_selected_project.png)

3. From the left sidebar, enlarge the sidebar with the expand button and click on **Item details** or click on the first item below the map icon (*resembling a circled i*).

    ![Item details button]({{ site.baseurl }}/images/level-making/worldsmith_click_item_details.png)

4. Right below the header "**Item details**", you should find another header "**Title**"; here using the input box you can change the name of your level. 
    > The changes will take place after you click outside of the input box.

5. You've successfully changed the name of your level locally.

<!-- ## Changing the babe screen

By default, the babe's screen equals the one in the main game.

## Setting the starting data
## Setting the ending images
## Setting the ending extra images
## Setting the end credits -->

<details class="expander">
   <summary markdown="1">
## Steps (without Worldsmith)
   </summary>

   <div markdown="1">

### Why does Jump King need a configuration file?
{: .no_toc }

In order for get the basic data about your map, Jump King (and in the past with JumpKingPlus) uses a configuration file.

This configuration file contains your level: 
- **title** (that will show up in the pause menu)
- **babe screen number** (where the first babe will spawn)
- **second babe screen number** (where the second babe will spawn)
- **third babe screen number** (where the third babe will spawn)
- **starting position** (changing your initial position and speed)
- **ending images** (for each babe)
- **ending extra images** (letting you choose what item can trigger the secondary ending image)
- **end credits** (once you finish your level, after the cutscene)

### Setting your level title
{: .no_toc }

1. Search for "title" in your XML file.
   You should find something like this:
   ```xml
   <title>YOUR_TITLE_HERE</title>
   ```
2. Replace `YOUR_TITLE_HERE` with your title name.
3. Done!

### Setting a different babe screen number
{: .no_toc }

1. Search for "ending_screen" in your XML file.
   You should find something like this:
   ```xml
   <ending_screen>YOUR_ENDING_SCREEN_HERE</ending_screen>
   ```
2. Replace `YOUR_ENDING_SCREEN_HERE` with your babe screen number.
3. Done!

For the second and third babe, the procedure is the same but replacing your search query with "ending_screen_second" or "ending_screen_third".

### Setting the starting data
{: .no_toc }

To set a new starting data:
1. Copy the following snippet: 
    ```xml
    <StartData>
        <Position>
            <X>YOUR_X_POSITION_HERE</X>
            <Y>YOUR_Y_POSITION_HERE</Y>
        </Position>
        <Velocity>
            <X>YOUR_X_VELOCITY_HERE</X>
            <Y>YOUR_Y_VELOCITY_HERE</Y>
        </Velocity>
    </StartData>
    ```
    > If you want don't want a custom position or a custom velocity, you can decide to remove the entire tag you don't want **but** make sure you always have the X and Y value of the tag you left in since those are necessary.
    {: .disclaimer }

2. For the <u>position</u>, replace your `X` and `Y` with the **absolute value** that you can find while testing the level. For the <u>velocity</u>, replace your `X` and `Y` at your will.
   > The velocity can be voided if the user is standing on a solid block by default.
   {: .warning }
3. Done!

To remove a starting data, select the **whole** `StartData` tag and delete it.

### Setting the ending images
{: .no_toc }

1. Make sure you have a packed image (file that has been converted to XNB) with **480x360 pixels of resolution**.
2. Move your image into the `ending` folder.
3. Search for "MainBabe" in your XML file.
   You should find something like this:
   ```xml
   <MainBabe>YOUR_ENDING_IMAGE_HERE</MainBabe>
   ```
4. Replace `YOUR_ENDING_IMAGE_HERE` with your ending image name.
5. Done!

For the other babes, repeat the process replacing your search query with "SecondBabe" or "ThirdBabe".

### Setting the ending extra images
{: .no_toc }

1. Make sure you have a packed image (file that has been converted to XNB) with **480x360 pixels of resolution**.
2. Move your image into the `ending` folder.
3. Search for "MainItem" in your XML file.
   You should find something like this:
   ```xml
   <MainItem>
    <item>Shoes</item>
    <image>YOUR_ENDING_IMAGE_WITH_ITEM_HERE</image>
   </MainItem>
   ```
4. Replace `Shoes` with the item of your choice based on the [item list]({{ site.baseurl }}/api/items){: target="_blank"}.
5. Replace `YOUR_ENDING_IMAGE_WITH_ITEM_HERE` with your ending image name.
6. Done!

### Setting the end credits
{: .no_toc }

1. Search for "EndingLines" in your XML file.
   You should find something like this:
   ```xml
   <EndingLines>
    <Credit>
        <header>YOUR_FIRST_ENDING_TITLE_HERE</header>
        <people>
            <string>YOUR_FIRST_ENDING_FIRST_ITEM_HERE</string>
            <string>YOUR_FIRST_ENDING_SECOND_ITEM_HERE</string>
        </people>
    </Credit>
    <Credit>
        <header>YOUR_SECOND_ENDING_TITLE_HERE</header>
        <people>
            <string>YOUR_SECOND_ENDING_FIRST_ITEM_HERE</string>
            <string>YOUR_SECOND_ENDING_SECOND_ITEM_HERE</string>
            <string>YOUR_SECOND_ENDING_THIRD_ITEM_HERE</string>
            <string>YOUR_SECOND_ENDING_FOURTH_ITEM_HERE</string>
            <string>YOUR_SECOND_ENDING_FIFTH_ITEM_HERE</string>
        </people>
    </Credit>
   </EndingLines>
   ```

> One instance of Credit equals one credit that's being shown, while there isn't a strict limit of this, having more than 5-6 `Credit` tags can be hard to follow.
{: .disclaimer }

2. Replace `YOUR_FIRST_ENDING_TITLE_HERE` with your first credit main title.
3. Replace all the `YOUR_FIRST_ENDING_[...]_ITEM_HERE` with whatever subtitles you want to add.<br>You can add or remove the `string` tags that you dont need.
    > Having more than 5 `string` tags can cause some of them to overflow the screen making them invisible.
    {: .disclaimer }

4. Done, you've set your first credit!

To add a new Credit simply add another Credit like the example above.

> Localization
> 
> Inside the Ending Lines, it's possible to use the default library for translations included in the game. LanguageJK includes all the possible text in Jump King based by your localization language.
> [Check out all the possible combinations!]({{ site.baseurl }}/api/LanguageJK.xml){: target="_blank"}
{: .important-title }

</div>
</details>

## Next up

Once you understand the configuration file, go to [**hitboxes**]({{ site.baseurl }}/level-making/hitboxes).