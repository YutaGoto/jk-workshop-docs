---
layout: default
title: Blocks
parent: Level Making
nav_order: 2
last_modified_date: 2024-05-03 09:48
---

<style>
  .main-content h3 {
    margin-top: 3rem;
  }

  #markdown-toc input[type="color"] {
    height: 1rem;
    vertical-align: middle;
  }

  input[type="color"] {
    padding: 0;
    width: 2rem;
    height: 2rem;
    margin-right: .75rem;
    vertical-align: -.5rem;
    cursor: pointer;
  }
</style>

# Block types
{: .no_toc }

every color defines a block, a mechanic and more!<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Blocks for new users

Below are the basic blocks you use to build your level. Make sure to read up what each of the colours do before you start making your hitboxes.

> Pro-tip!
>
> Try each colour out and test them ingame to develop an understanding for what they do.
{: .note-title }

By clicking or hovering the color box you can see the RGB color that you will need to use in the hitbox.

### <input type="color" title="RGB(0,0,0)" value="#000000">Solid block

The solid block is a normal block you can stand on.

- It is solid,
- you can walk on it [^1],
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(255,0,0)" value="#FF0000">Slope block

The slope block is the block used for slopes. It needs two adjacent any-solid or fake blocks to exist. These two
adjacent blocks needs to be:
1. one on the left or right side of the slope
2. one on the top or bottom side of the slope

- It is usually solid [^4],
- you can't walk on it,
- you will slide on it no matter what,
- it can affect your direction [^3].

### <input type="color" title="RGB(128,128,128)" value="#808080">Fake block

The fake block is a block that is not solid and the sole purpose is to create a slope without surrounding blocks.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it can affect your direction [^3].

### <input type="color" title="RGB(0,255,255)" value="#00FFFF">Ice block

The ice block is a solid block that will make the player slide if it's standing on it.

- It is solid,
- you can walk on it [^1],
- you will slide on it no matter what,
- it can affect your direction [^3].


### <input type="color" title="RGB(255,255,0)" value="#FFFF00">Snow block

The snow block is a solid block that will make the player stand in one position, needs at least 7 frames to jump.

- It is solid,
- you can't walk on it,
- you can't slide on it [^2],
- it can affect your direction [^3].

<br>
#### Snow particles

The snow hitbox/mechanic can let you decide which type of snow particles you would like to have in a particular area.

> This is an optional, therefore if you don't want a different snow type you can leave it as is and it will default to no particles used.
{: .highlight }

<!-- ### Adding/removing a snow particle (with Worldsmith)

🚧 Work in Progress. **No trespassing!** 🏗
{: .disclaimer } -->

<details class="expander">
   <summary markdown="1">
### Steps (without Worldsmith)
{: .no_toc }
   </summary>
   <div markdown="1">

The `snow_settings.xml` (snow particles settings file) file can be found inside the `particles` folder of your level.

### Adding/removing a snow particle
{: .no_toc }

To add a snow particle:

1. Write down the first and last screen where you want your particle to present.
2. Decide [__what type of snow particle you want__]({{site.baseurl}}/api/particles){: target="_blank"}.
3. Copy the following snippet:
   ```xml
   <SpriteSpan>
    <start>YOUR_FIRST_SCREEN</start>
    <end>YOUR_LAST_SCREEN</end>
    <sprite>YOUR_SNOW_PARTICLE_TYPE</sprite>
   </SpriteSpan>
   ```
4. Navigate to `particles` and open `snow_settings.xml`.
5. If this is your first time dealing with snow particles, remove the already existing `SpriteSpan`s.
6. Paste in a new line below the `sprite_spans` opening tag.
7. Replace `YOUR_FIRST_SCREEN` with your first screen.
8. Replace `YOUR_LAST_SCREEN` with your last screen.
9. Replace `YOUR_SNOW_PARTICLE_TYPE` with the value of the particle chosen.

To remove a snow particle:

1. Find the screen(s) where the snow particle is present.
2. Navigate to `particles` and open `snow_settings.xml`.
3. Find the `SpriteSpan` that contains your screens (between start and end) and delete it.
4. If your `sprite_spans` is without any `SpriteSpan`, add the following SpriteSpan:
   ```xml
   <SpriteSpan>
      <start>0</start>
      <end>0</end>
      <sprite>0</sprite>
    </SpriteSpan>
    ```

</div>
</details>

### <input type="color" title="RGB(255,255,128)" value="#FFFF80">Thin snow block

The snow block is a solid block that will make the player stand in one position, you can jump any jump charge.

- It is solid,
- you can't walk on it,
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(255,106,0)" value="#FF6A00">Sand block

The sand block, is pretty much what quicksand is, by landing on it you will immediately sink.

- It is solid,
- you can walk on it [^1],
- you can't slide on it,
- it affects your direction (you will sink down).

### <input type="color" title="RGB(0,255,0)" value="#00FF00">Wind block

The wind block, if present on a screen, it will activate an infinite loop where it will slowly push the player left and
right. The wind polarity changes direction every 5 seconds.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

### <input type="color" title="RGB(255,255,255)" value="#FFFFFF">No wind block

The no wind block does exactly what it sounds like. It's called "no wind" block because it's main use was to stop the
wind, but can be used for water and low gravity too!

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it cancels out the wind, water and low gravity (not affecting your direction).

### <input type="color" title="RGB(0,170,170)" value="#00AAAA">Water block

The water block is an area block that slows you down.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (velocity, gravity and jump charge).

### <input type="color" title="RGB(128,255,255)" value="#80FFFF">Low gravity block

The low gravity block is an area block that slows you down but amplifies your jump range.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (velocity, gravity and jump curve).

---

## Blocks for intermediate users

These are just different colours but have more advanced functions. It is preferred to not touch these until you are proficient with the starter blocks.

### <input type="color" title="RGB(182,255,0)" value="#B6FF00">Quark block

When the player touches a quark block, their **Y (height) position is rounded** to the closest value on the base of 4 (4,8,12,16,etc). Using **TWO** quark blocks together rounds the player position by one full in-game pixel (8 pixels on the .png/hitboxes), giving a more "consistent" outcome.

In order to get the full potential of a quark block:
1. It has to be used when player is in full falling velocity
2. It has to be used on one of the side of the screen

![Usage](https://media.discordapp.net/attachments/623779998494490624/782275174916685864/unknown.png)

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (player Y position).

### <input type="color" title="RGB(1,0,255)" value="#0100FF"><input type="color" title="RGB(255,0,255)" value="#FF00FF">Teleport block

The teleport block has a range of values that goes from 1 to 255, if placed on a screen, when the player crosses the
side of the screen, it teleports the player to the specific screen number given by the red channel number.

> For example if on the screen you place one teleport block colored RGB(9,0,255), once the player walks/jumps/falls in
either side of the screens, it will get teleported to the 9th screen of your hitbox file.

> By default works both ways, adding another teleport to the other side of the screen will allow you to have two
different side teleports per screen.
{: .disclaimer }

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction (player Y position).

### <input type="color" title="RGB(192,255,0)" value="#C0FF00"><input type="color" title="RGB(207,255,0)" value="#CFFF00">Wind gradient block

The wind gradient block has a range of 16 intesities of [wind](#wind-block), from 12.5% or RGB(192,255,0) to 200% or
RGB(207,255,0) of the original strength of the wind.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

### <input type="color" title="RGB(208,255,0)" value="#D0FF00"><input type="color" title="RGB(223,255,0)" value="#DFFF00">Left one-way wind gradients

The wind gradient block has a range of 16 intesities of the left one-way wind, from 12.5% or RGB(208,255,0) to 200% or
RGB(223,255,0) of the original strength of the wind. The one-way wind will never change direction.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

### <input type="color" title="RGB(224,255,0)" value="#E0FF00"><input type="color" title="RGB(239,255,0)" value="#EFFF00">Right one-way wind gradients

The wind gradient block has a range of 16 intesities of the right one-way wind, from 12.5% or RGB(224,255,0) to 200% or
RGB(239,255,0) of the original strength of the wind. The one-way wind will never change direction.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

---

## Blocks for expert users

These are the most complex blocks. It is preferred to learn them last.

> You should follow the following blocks only if you really know what you are doing!
{: .warning }

### <input type="color" title="RGB(65,65,65)" value="#414141"><input type="color" title="RGB(68,65,65)" value="#444141">Semi-solid block

The semi-solid block is a solid block that is solid only in one side.

| Solid side | Red channel value |
| ---------- | ----------------- |
| Top        | 65                |
| Right      | 66                |
| Bottom     | 67                |
| Left       | 68                |

- It is solid [^6],
- you can walk on it [^1],
- you can't slide on it [^2],
- it can affect your direction [^3].

### <input type="color" title="RGB(0,0,75)" value="#00004B"><input type="color" title="RGB(60,45,75)" value="#3C2D4B">Warp block

The warp block warps the player into the coordinates given by the Red and Green channel.

To get warp color working:
1. Use the test mode with Relative Coordinates,
2. write down the coordinates you want to teleport to,
3. divide the number by 8, round if necessary.
4. Use the new numbers for the Red and Green value.

- It is not solid,
- you can't walk on it,
- you can't slide on it,
- it affects your direction.

## Blocks recap

Remembering all blocks can be hard

<table class="vertical">
  <thead>
    <tr>
      <th>Title</th>
      <th>Solid</th>
      <th>Slope</th>
      <th>Fake</th>
      <th>Ice</th>
      <th>Snow and thin snow</th>
      <th>Sand</th>
      <th>Wind</th>
      <th>No wind</th>
      <th>Water</th>
      <th>Low gravity</th>
      <th>Quark</th>
      <th>Teleport</th>
      <th>Wind gradient</th>
      <th>One-way wind gradient</th>
      <th>Semi-solid</th>
      <th>Warp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>is solid?</td>
      <td class="label-green">✔</td>
      <td class="label-yellow"><a href="#fn:4">~<sup role="doc-noteref">4</sup></a></td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-yellow"><a href="#fn:5">~<sup role="doc-noteref">5</sup></a></td>
      <td class="label-red">✖</td>
    </tr>
    <tr>
      <td>walkable? <sup role="doc-noteref"><a href="#fn:1">1</a></sup></td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
    </tr>
    <tr>
      <td>slideable? <sup role="doc-noteref"><a href="#fn:2">2</a></sup></td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
    </tr>
    <tr>
      <td>affects player?</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
    </tr>
    <tr>
      <td>affected by other blocks?</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-red">✖</td>
      <td class="label-green">✔</td>
      <td class="label-red">✖</td>
    </tr>
  </tbody>
</table>

## Next up

Once proficient with at least the [blocks for new users](#blocks-for-new-users). [**Head to Screens**]({{site.baseurl}}/level-making/screens).

### Notes

[^1]: You can walk on it until you are not wearing Giant Boots.
[^2]: You can slide on it if you are wearing Snake Ring.
[^3]: It can affect your position if a type of wind, water or low gravity is in the screen, this can be avoided with the use of the [no wind block](#no-wind-block).
[^4]: The slope can be not solid if the one or all adjacent blocks are missing.
[^5]: You can't slide on a fake block unless it's connected to a slope block.
[^6]: The one-way block is solid only on one side, depending on the color chosen.
