---
layout: default
title: Updating
nav_order: 16
last_modified_date: 2024-04-12 15:10
---

# Updating
{: .no_toc }

how to update the content of your items in the Workshop.<!-- more -->
{: .fs-6 .fw-300 }

<style>
   .toc-spaced > li {
      margin: 2rem 0;
   }
</style>

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Updating your item

> You won't have to follow this if your item has not been published yet, you can quickly checking this in the right side of the **Item details** page, hovering the icon next to your item's title. If your tooltip looks like the following example, you can skip this.
>
> ![Check if on workshop]({{ site.baseurl }}/images/level-making/worldsmith_check_if_on_workshop.png)
{: .warning }


1. To bring your changes on the Workshop as well, you will need to scroll down until you find the **Changelog** subsection under **Workshop details** (you can find it before the "Danger zone" section) inside the **Item details** page.

    ![Find changelog]({{ site.baseurl }}/images/level-making/worldsmith_find_changelog.png)

2. *(Optional)* Write what you've changed.
3. Click **Update**.
4. A prompt will show on screen showing you the progress for your update. Once done updating, Worldsmith will tell you it has updated your item like so:

    ![Update successful]({{ site.baseurl }}/images/level-making/worldsmith_success_updated_item.png)

5. If Worldsmith has shown the pop-up like the example above, you have **successfully updated** your item. From here you can either close the pop-up by clicking **Close** or check your changes yourself by going on your item's Steam Workshop page by clicking **Open on Steam...**.

<details class="expander">
   <summary markdown="1">
## Steps (using Workshop Manager)
   </summary>

   <div markdown="1">

{: .toc-spaced }
1. Open `Jump King Workshop Manager` from Steam or [**click here**](steam://rungameid/2245910).<br>
   
   ![Step 1]({{ site.baseurl }}/images/publishing/Step1.png)
   
   <blockquote class="highlight">
    <details>
        <summary>If you can't find it, make sure you have tools enabled from the dropdown in your Steam library. Expand for image reference.</summary>
        <img src="{{ site.baseurl }}/images/publishing/SteamToggleTools.png" alt="Step 1a">
    </details>
   </blockquote>

2. Once opened, click on **Update existing content**.
   ![Step 2]({{ site.baseurl }}/images/updating/Step2.png)

3. From the blank dropdown, select the item you want to update.
   ![Step 3]({{ site.baseurl }}/images/updating/Step3.png)
   
   <blockquote class="highlight">
    <details>
        <summary>If you can't open the dropdown, expand this.</summary>
        <p class="mt-2 mb-0">Make sure:</p>
        <ul>
            <li>You are in the right Steam account.</li>
            <li>You have uploaded at least an item and are subscribed to it (therefore finished downloading).</li>
        </ul>
    </details>
   </blockquote>

   <blockquote class="highlight">
    <details>
        <summary>If you don't see your item from the dropdown, expand this.</summary>
        <p>If you have just uploaded it, consider restarting the tool once the item has been downloaded from Steam. Otherwise make sure you are subscribed your item and it is downloaded.</p>
    </details>
   </blockquote>

   Once selected, you will see the item details menu as following.
   ![Step 3a]({{ site.baseurl }}/images/updating/Step3a.png)

4. Make sure the **"Updating from" folder** of your item is correct in directory.<br>This folder will be what you will update so make sure your item's content is right.
   ![Step 4]({{ site.baseurl }}/images/updating/Step4.png)

5. *Optional*{: .text-grey-dk-000 } 
   —
   **Add a new thumbnail or replace the existing one**

   To add or replace the thumbnail, click on the **"Replace thumbnail"** button and select the image you want to use.

   {: .warning }
   > For the Steam limitations, we recommend you to follow the following details:
   - resolution: **256x256 pixels**
   - file size: below **34 kB** (kilobytes)
   - bit depth: **8 bit** *(not required but lowers the file size dramatically)*
   - image type: **png** *(not requred but lowers the file size dramatically)*

   If the image follows the limitations above, it will prompt you a message telling you it has changed the thumbnail to the image selected. *(Don't forget to click Update to change it!)*
   ![Step 5]({{ site.baseurl }}/images/updating/Step5.png)

6. Add a changelog to let other players know what you've changed in this version.<br>
   ![Step 6]({{ site.baseurl }}/images/updating/Step6.png)

7. Click Update and let the tool update the item for you.
   ![Step 7]({{ site.baseurl }}/images/updating/Step7.png)

</div>
</details>

## Reverting changes

Reverting changes only works on Steam, your project will be unchanged, therefore if you want to continue editing on a rolled back project, you will need to find the changes and undo them yourself!
{: .important }

> For tech-savvies
> 
> Consider using Git (or other version control systems) for each update to ease what's changed.<br>So you can easily rollback on your project too!
{: .note-title }

Sometimes it can happen you've made an unwanted change.<br>
By clicking on the "Change Notes" tab on your item's Workshop page you can check when you have updated your item and by clicking **Revert to this version** (based on the date of the change) you can update your item to the chosen specific version.

![Step 7a]({{ site.baseurl }}/images/updating/Step7a.png)

> This only works if you change the contents of the item, if you change the thumbnail, you won't see any change note.
{: .warning }

> It's recommended to always write what has been changed every update. This way, you can immediately identify each edit and revert back if you need to.
{: .note }