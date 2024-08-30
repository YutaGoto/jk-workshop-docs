---
layout: default
title: Skin & Set Making
nav_order: 8
last_modified_date: 2024-04-18 18:22
---

# Skin & Set Making
{: .no_toc }

**everything** you need to know to make a skin or set.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Setting the environment to make any skin

First of, open the software of your choice and set two layers.

1. The first (or top) layer should be the layer you use for drawing your skin,
2. the second (or bottom) layer should be the [**base file**]({{site.baseurl}}/images/level-making/king/base.png){:target="_blank"}; this second layer will help you building a fully working skin.

> A simple trick while making a skin is setting the second (or bottom) layer to a lower opacity, for example 50%.
{: .note }

<details class="expander">
   <summary markdown="1">
### Additional details (without Worldsmith)
   </summary>
   <div markdown="1">

### Once satisfied with the texture(s)
{: .no_toc }

1. Disable or hide the last (bottom) layer. 
2. > **If you are doing a single skin**, export the image file but save the filename somewhere since you will need it later.
   {: .highlight }

   > Otherwise, **if you are doing a skin set** save them with the following format and save the filenames somewhere since you will need them later.
   ```md
   (YOUR COLLECTION NAME)_(YOUR ITEM NAME).png
   ```
   > This format is not mandatory but can help you identify the items inside your set, in case you need to update something.
   {: .highlight }

## Why does Jump King need a configuration file?
{: .no_toc }

In order for get the basic data about your skin or set, Jump King (and in the past with JumpKingPlus) uses a configuration file.

This configuration file contains your skin or set: 
- the boolean that tells you **if the skin/set is enabled**
- one (if a skin) or multiple (if a set) **filenames** of your packed images
- one (if a skin) or multiple (if a set) **item** you want to override

</div>
</details>

## Single skins

<!-- ### Setting everything (using Worldsmith)
🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

### Changing/replacing a skin

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Wardrobe".
3. You should find one item inside the **Customized** tab, which represents your single skin.

![Single skin settings]({{ site.baseurl }}/images/level-making/king/single_skin_hover.png)

From here you can change its type using the dropdown. Hovering your item will show additional settings such as: a **Replace** button to replace your item's texture and a button with a folder icon if you were to open that skin with your file explorer.



<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

The configuration in sigle skins is called `cosmetic_settings.xml`.<br>Open the file and proceed with the settings below. A single skin's configuration file looks like this:

```xml
<?xml version="1.0"?>
<ReskinSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <skin>Cap</skin>
  <name>Propeller Hat</name>
  <enabled>false</enabled>
</ReskinSettings>
```

### Setting the skin's item
{: .no_toc }

1. Search for "skin" in your XML file.
   You should find something like this:
   ```xml
   <skin>YOUR_SKIN_HERE</skin>
   ```
2. Replace `YOUR_SKIN_HERE` with the [**wearable item**]({{site.baseurl}}/api/items){:target="_blank"} of your choice.
3. Done!

### Setting the skin's filename
{: .no_toc }

1. Search for "name" in your XML file.
   You should find something like this:
   ```xml
   <name>YOUR_NAME_HERE</name>
   ```
2. Replace `YOUR_NAME_HERE` with the packed file name of your skin (no extension in the name).
3. Done!

</div>
</details>

## Skin sets

### Adding a skin to a skin set

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Wardrobe".
3. You should find a **Default** tab, expanding it will show you the items you haven't customized.

    ![Skin set preview]({{ site.baseurl }}/images/level-making/king/skin_set_add.png)

4. Hovering an item in the **Default** tab, will display a **Replace** button.
5. By clicking it, a prompt will show up asking you to select a texture for the skin you've clicked the Replace button on.

    ![Skin set add]({{ site.baseurl }}/images/level-making/king/skin_set_add_preview.png)

6. After clicking **Open**, your newly modified skin will be displayed inside the **Customized** tab.

    ![Skin set success]({{ site.baseurl }}/images/level-making/king/skin_set_add_success.png)

### Replacing a skin from a skin set

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Wardrobe".
3. You should find a **Customized** tab, expanding it will show you the items you have customized already.

    ![Skin set preview]({{ site.baseurl }}/images/level-making/king/skin_set_replace.png)

4. Hovering an item in the **Customized** tab, will display a series of buttons including a **Replace** button.
5. By clicking it, a prompt will show up asking you to select a texture for the skin you've clicked the Replace button on.
  
    ![Skin set preview]({{ site.baseurl }}/images/level-making/king/skin_set_replace_preview.png)

6. After clicking **Open**, your updated skin will be displayed.

    ![Skin set success]({{ site.baseurl }}/images/level-making/king/skin_set_replace_success.png)

### Deleting a skin from a skin set

1. Navigate to the **Wardrobe** page.
2. Scroll until you find an header "Wardrobe".
3. You should find a **Customized** tab, expanding it will show you the items you have customized already.

    ![Skin set preview]({{ site.baseurl }}/images/level-making/king/skin_set_replace.png)

4. Hovering an item in the **Customized** tab, will display a series of buttons including a red button that has a tooltip that says "Bring back the default look". 
5. Clicking that button will remove the customized skin from your skin set.

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
   </summary>
   <div markdown="1">

The configuration in skin sets is called `set_settings.xml`.<br>Open the file and proceed with the settings below. A skin set's configuration file looks like this:

```xml
<?xml version="1.0"?>
<SetSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <enabled>false</enabled>
  <Reskins>
    <Reskin>
      <skin>Crown</skin>
      <name>RedHorns</name>
    </Reskin>
    <Reskin>
      <skin>NULL</skin>
      <name>RedBaseSkin</name>
    </Reskin>
  </Reskins>
</SetSettings>
```

### Adding a new skin to the set
{: .no_toc }

1. Search for "Reskins" in your XML file.
2. Add the following snippet below the opening tag of `Reskins` in a new line:
   ```xml
    <Reskin>
      <skin>YOUR_SKIN_HERE</skin>
      <name>YOUR_FILENAME_HERE</name>
    </Reskin>
   ```
3. Replace `YOUR_SKIN_HERE` with a **wearable** [**item**]({{site.baseurl}}/api/items){:target="_blank"} of your choice.
4. Replace `YOUR_FILENAME_HERE` with the file name of your packed XNB file for your skin.
5. Repeat step 2 for each skins you want to add. 
6. Done!

### Removing a skin from the set
{: .no_toc }

1. Search for "Reskins" in your XML file and find the [**item**]({{site.baseurl}}/api/items){:target="_blank"} that you want to remove.
2. Remove the whole `Reskin` tag that contains `skin` as your unwanted item.
3. Done!

</div>
</details>

## Testing

> Testing your skin is **currently not available** since you can see your skin directly both in Worldsmith and in your pixel-art editor of choice.
{: .warning }

<!-- **WARNING**:<br>The following reskins and collections won't work in custom levels:
- Base reskin
- Collection that contains a base skin -->

## Next up

Once you are done with your skin, read [**Publishing**]({{site.baseurl}}/publishing).