---
layout: default
title: GUI
parent: Level Making
nav_order: 5
last_modified_date: 2024-04-16 14:34
---

# GUI folder
{: .no_toc }

list of locations and the *earthquake* effect<!-- more -->
{: .fs-6 .fw-300 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

> 🚧 If you do not understand how the text works in the example below. Go back to [File Types]({{site.baseurl}}/getting-started/filetypes) and read up on XML. 🏗
{: .disclaimer }

## Locations

The locations (also known as areas) are a group of screens that usually represent a specific gameplay or style. Each location have a name, start, end, introduction trigger screen.

![Location example]({{site.baseurl}}/images/level-making/location.png)

### Adding a location

1. Navigate to the **Locations** page.

    ![Locations page]({{site.baseurl}}/images/level-making/worldsmith_locations.png)

    > If you are in the Screens page, you can click on the location name above Screen 1 (or whatever screen are you on).
    > 
    > ![Locations link in Screens]({{site.baseurl}}/images/level-making/worldsmith_locations_in_screens.png)
    {: .note }

2. Click on the **Add new location** button on top-right side of the page.
3. A prompt will pop up asking you to write the location details (location name, start, unlock and end screen), here's how it should look like when done:

    ![Add location]({{site.baseurl}}/images/level-making/worldsmith_locations_add.png)

4. Click **Add** to add it on the location list.
5. Once done, you should be seeing a new location in the page.

    ![Location added]({{site.baseurl}}/images/level-making/worldsmith_locations_success.png)

### Changing or removing a location
From the **Locations** page, you can simply expand the location of your choice and edit them freely. Using the Delete button will get rid of your location area (all your details in the Screen page will be untouched, as this is just for the GUI).

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

### Adding a location
{: .no_toc }

To add a location:

1. Write down the screen numbers that you want to be part on a location.
2. Nagivate to `gui` and open `location_settings.xml`.
3. If this is the first time, should see something like this:
    ```xml
    <?xml version="1.0"?>
    <LocationSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <locations>

            <Location>
                <start>1</start>
                <end>1</end>
                <unlock>1</unlock>
                <name>YOUR_LOCATION_NAME</name>
            </Location>

        </locations>
    </LocationSettings>
    ```
    > **If this is not the first time**, paste the following snippet below the closing tag of the latest location.
    ```xml
        <Location>
            <start>1</start>
            <end>1</end>
            <unlock>1</unlock>
            <name>YOUR_LOCATION_NAME</name>
        </Location>
    ```
4. Replace the `start` value with the first screen of your location.
5. Replace the `unlock` value with the screen that you want to trigger the location title to show up.
    > If you don't  want the location title to show up, simply put `0` as a value.
    {: .highlight }

6. Replace the `end` value with the last screen of your location.
7. Replace `YOUR_LOCATION_NAME` with the name of your new location.

> Since this is supposed to be a linear location grouping method, if you trigger a later present location, the middle locations won't be triggered.
{: .disclaimer }

> Make sure your location always ends before starting another one! This can cause problems later on if ignored.
{: .warning }

### Removing a location
{: .no_toc }

To remove a location:

1. Find what is the name of the location you are looking to remove.
2. Nagivate to `gui` and open `location_settings.xml`.
3. Remove the entire `Location` tag where the name equals to the location you want to remove.

</div>
</details>

## Earthquake effect

This allows you to replicate the earthquake effect used by Jump King in correspondence of the towers. This is effect consists of moving the screen left and right by one pixel.

### Adding the earthquake effect

1. Navigate in the **Screens** page.
2. Using the **Go to screen...** button or the up-down arrows, move to the screen you want to add the effect.
3. Right-click on the preview on the left-side of the page, a context menu like the following should appear.

    ![Context menu]({{ site.baseurl }}/images/level-making/screens/worldsmith_screens_context_menu.png)

4. Navigate into **Add on screen...** and click **Earthquake effect**.

    ![Add earthquake]({{ site.baseurl }}/images/level-making/worldsmith_earthquake_add.png)

5. Once clicked, the effect will be added on your screen.

    ![Earthquake effect added]({{ site.baseurl }}/images/level-making/worldsmith_earthquake_success.png)

### Mass adding/removing the earthquake effect

1. Using the **Go to screen...** button or the up-down arrows, move to the screen you have the earthquake effect you want to get rid of.
3. From the right side of the page, expand the **Earthquake effect** tab.

    ![Earthquake effect tab]({{ site.baseurl }}/images/level-making/worldsmith_earthquake_tab.png)

4. Clicking on **Show/Hide effect** will toggle the earthquake preview shake. Clicking on the yellow button with a cog will open the earthquake setting where you can **add or remove multiple screens** at will. clicking on the red button with an X will **remove the earthquake effect from the current screen**.

    ![Earthquake settings]({{ site.baseurl }}/images/level-making/worldsmith_earthquake_settings.png)

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

### Adding and removing the earthquake effect on a screen
{: .no_toc }

To add the earthquake effect on a screen:

1. Write down the screen number(s) where you want to have the earthquake effect.
2. Nagivate to `gui` and open `earthquake_settings.xml`.
3. > By default there's only one screen set to 0, so it will never trigger. Like the following example:
    ```xml
    <?xml version="1.0"?>
        <EarthquakeSettings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
            <screens>
                <int>0</int>
            </screens>
        </EarthquakeSettings>
    ```
    {: .highlight }
   
   To add earthquake effects, you will need to paste the following and replace `SCREEN_NUMBER` with each screen number.
    ```xml
    <int>SCREEN_NUMBER</int>
    ```

To remove an earthquake effect on a screen:

1. Find the screen that you want to remove the effect.
2. write down the screen number.
3. Nagivate to `gui` and open `earthquake_settings.xml`.
4. Remove the entire line where the screen number is present.

</div>
</details>

## Next up

Go to [**props**]({{ site.baseurl }}/level-making/props).