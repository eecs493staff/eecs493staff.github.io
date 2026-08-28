---
layout: spec
title: a2-asteroids-menu
---

# EECS 493 Assignment 2: Asteroids Main Menu

| Total     | Released | Due           |
| --------- | -------- | ------------- |
| 65 points | 1/16     | 1/25 11:59 PM |

## Submission Instructions

**Before submitting, please ensure your website loads in Google Chrome by simply clicking and opening the `index.html` without using server hosting tools (e.g. VS Code Live Server).**

Please submit your work to Canvas as a zip file, named `a2_<uniqname>.zip`. Replace `<uniqname>` with your uniqname: e.g. `a2_zhaojer.zip`, note that the angle brackets should NOT be included in your filename. Renaming (e.g., "-1") done by Canvas is fine.

This zip file should have a _single directory_ containing _all files and directories_ provided in the starter code. In other words, the zip file should have the following structure.

```console
a2_uniqname
├── index.html
├── scripts
│   └── page.js
├── src
│   ├── asteroid.png
│   ├── frontpage_background.jpg
│   ├── port.gif
│   └── shield.gif
└── style
    └── index.css
```

Not following the upload instruction will result in a penalty.

## Objective

The objective of this assignment is for you to gain practical experience in building a single-page web application with HTML, CSS, and a little bit of JavaScript. Specifically, you will be creating the main menu of a game, and making it work at any window size. No external libraries or frameworks are allowed.

Watch this video for an overview of Assignment 2: [https://youtu.be/NHIMrnUo_uA](https://youtu.be/NHIMrnUo_uA)

## Grading Breakdown

This assignment has 3 main components (denominator of 65 points):

1. A landing page - _25 points_
2. A settings panel - _25 points_
3. A tutorials page - _15 points_

## Starter Code

You will use the starter code we provide to complete this assignment.

Download and unpack the starter files (either using the following commands or simply navigating to the link).

```console
$ wget https://eecs493staff.github.io/a2-asteroids-menu/starter_code.tar.gz
$ tar -xvzf starter_code.tar.gz
```

Here's a brief description of each of the starter files.

| File | Description |
| ---- | ----------- |
| `index.html` | The document skeleton and empty containers for the three screens; write your HTML code here |
| `style/index.css` | A few base styles for the page and the game window are defined; write your CSS code here |
| `scripts/page.js` | Some section headings to organize your code; write your JS code here |
| `src/` | Images to display on your website; do NOT modify |

Remarks:

- You aren’t required to use the starter code, but it’s there to help you.
- Please refer to Piazza for any modifications and clarifications.
- Please make sure that your application (webpage) behaves properly on the latest version of Google Chrome. Your graders will use Chrome.

## Requirements

We outline the requirements for each of the components below. **Everything listed in this section, unless labeled as "Suggested", is required.** The demo video may be helpful in understanding the website; however, your website does NOT need to look exactly like it.

### General

You are expected to follow the practices we discussed in class, whether or not they are spelled out below. The clearest of these is **separation of concerns**. _Up to -10 points if not followed._

- Only use one HTML file, `index.html`. _-10 points off if not followed._
- Do all styling/layout in a separate CSS file, `index.css`. _-10 points off if not followed._
  - Remark: `<b>` and `<i>` tags count as inline styling. Do not use them.
  - Moderate use of `<br>` tags are ok.
- Do all JavaScript code in a separate JS file, `page.js`. _-10 points off if not followed._
  - Register your event listeners with `addEventListener` inside `page.js`. Do not put `onclick` (or similar) attributes in your HTML.
- Do not use any external library or framework. _-10 points off if not followed._
- Use relative paths for images. _-10 points off if not followed._

### Responsive Layout

Your menu has to work at whatever size the browser window happens to be, not only at the size you developed it at. _Up to -10 points if not followed._

- Do not give layout elements a fixed pixel width or height. Size things with relative units (e.g., `rem`, `em`, `%`) and leverage Flexbox or Grid for arranging the layout.
  - `px` is still fine for things that are not layout, such as border widths.
- At any window width down to 375px, the page must not scroll sideways, and every control must stay visible and usable.
- Text has to stay readable at every size. Nothing may be clipped or overlap something else.

This has to hold at **every** width in that range, not just at a few particular sizes. Drag the edge of your window slowly from full width down to the narrowest and watch for the point where something first breaks. That is what your graders will do.

They will also spot-check these three sizes in Chrome DevTools' device toolbar, as a desktop, a tablet, and a phone:

- **1280×720**
- **768×1024**
- **375×667**

But note that passing those three is not enough on its own. A layout can look fine at all three and still break at, say, 900px wide.

### Semantic HTML

Choose elements for what they _mean_, not for how they happen to look. A `<div>` styled to look like a heading is not a heading.

- Every `<img>` needs an `alt` attribute. Use `alt=""` for images that are purely decorative.
- Every form control needs a `<label>` associated with it.
- You need to designate the regions of the page with the elements that describe them.

### Landing Page (25 points)

#### Main Components

- a background image
- an "Asteroids" header
- two buttons, "Play game!" and "Settings", that transition to the correct corresponding screen when clicked (Need JavaScript)
  - "Play game!" transitions to Tutorials Page
  - "Settings" transitions to the Settings Panel

#### Required

- When you first load the HTML page, the landing page should be shown
- Use `src/frontpage_background.jpg` as the background
- Header should be at the top and span the entire width of the game window
- The text "Asteroids" should be horizontally centered
- Asteroid gifs should appear on the left and right side of the header; they should also have the same height as the header while retaining their original width/height ratio
  - Hint: [CSS Flexbox](https://www.w3schools.com/css/css3_flexbox.asp) ([Flexbox Froggy](https://flexboxfroggy.com) is a great website to learn about Flexbox)
- Both buttons must appear within the game’s border and be horizontally centered and aligned
- Text in the buttons should be horizontally and vertically centered
- There should be some space between the first button and the bottom of the header, and some space between the two buttons

#### Suggested Style

The "Asteroids" title is much larger than the browser default. See the [demo video](#objective).

Header:

```css
background-color: darkslateblue;
border-bottom: 6px groove;
color: white;
```

Buttons:

```css
background-color: darkslateblue;
color: white;
```

### Settings Panel (25 points)

#### Main Components

- a "Settings" heading
- a "Volume:" label, with a slider beneath it to adjust the volume of the game
  - default: 50
- a "Difficulty" label, with 3 options beneath it to select the difficulty level
  - default: Normal
- a close button that returns to the landing page
- Settings should remain the same after closing the panel
  - Note: When the page is reloaded/refreshed, settings do _not_ have to remain the same.

#### Required

- The Settings Panel
  - should be centered both vertically and horizontally
  - should never be wider or taller than the window; if its contents do not fit, it should scroll rather than spill off the screen
- The "Settings" heading, the "Volume:" label, and the "Difficulty" label should be bolded and horizontally centered
  - Remark: The volume number, e.g. 50, is NOT bolded
- The slider has a range of 1 to 100 (inclusive); as the user drags the slider left and right, the current volume number based on the positioning of the slider should be updated next to the "Volume:" label. (Need JavaScript)
- The three difficulty options
  - are the same width and height as each other, whatever their labels say
  - are labeled "Easy", "Normal", and "Hard" respectively
  - are evenly spaced and side by side when there is room for them; they may stack vertically when the window is narrow
- Exactly one difficulty is selected at any time, and the selected one is clearly distinguishable from the other two
- The close button should be horizontally centered (i.e. aligned with the middle difficulty option)

#### Hints

There is more than one way to build the difficulty options. A radio group (`<input type="radio">`) is one of them! And in fact, it needs no JavaScript.

The starter code gives you a `<dialog>` for the panel. A `<dialog>` opened with `showModal()` centers itself and can be closed by a `<form method="dialog">` without any JavaScript. Note that a `<dialog>` is `display: none` until it is opened, so write its layout against `#settings[open]` rather than `#settings`.

#### Suggested Style

Difficulty options and close button:

```css
background-color: purple;
color: white;
```

### Tutorials Page (15 points)

#### Main Components

- All the texts and gifs as shown in the [demo video](#objective)
- A "Start" button (that doesn’t need to lead anywhere, yet)

#### Required

- "How to play" is bolded
- "Avoid", "Collect", "Travel", "Gain" are bolded
- "asteroids", "shields", "portals", "points" are italicized
- All components (texts, gifs, button) are horizontally centered on screen
- There should be some space between each component
- The images should retain their original aspect ratio

#### Suggested Style

The tutorial text is noticeably larger than the browser default, and "How to play" is larger still — see the [demo video](#objective).

Background:

```css
background-color: gainsboro;
```

## FAQ

### Do I need to create additional files other than the ones provided in the starter code?

No. You should write all of your code in `index.html`, `style/index.css`, and `scripts/page.js`.

### What is the recommended development environment for the assignments?

We recommend using any text editor (e.g. VSCode) and directly opening your `index.html` file in Google Chrome to test your code. You do not need any additional extensions (e.g. Live Server).

### What are relative paths vs. absolute paths?

Relative paths begin with the current directory `.`, whereas absolute paths begin with the root directory `/`. Read more in [this article](https://www.geeksforgeeks.org/absolute-relative-pathnames-unix/).

### Where should I look things up?

[MDN Web Docs](https://developer.mozilla.org/) is the reference we recommend, and the one to reach for first. Every HTML element, CSS property, and JavaScript method has a page there describing what it is for, what values it accepts, and how it behaves. For example [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) or [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked). It is written and maintained alongside the browsers themselves, so unlike most tutorial sites it stays accurate and current.

Getting comfortable reading documentation is part of learning web development. When this spec names an element or a property without explaining it, that is your cue to look it up.

### Can I use sample code from W3Schools?

Yes but with precaution. Be aware that a lot of its tutorials are old and use fixed sizes, so you will often need to adapt them.

### Can I use jQuery, Bootstrap, or another library?

No. Everything in this assignment can be done with plain HTML, CSS, and JavaScript, and doing it that way is the point of the assignment.

### How do I check that my page is responsive?

Drag the edge of your browser window and watch what happens. For specific sizes, open Chrome DevTools (F12), click the device toolbar icon, and enter the dimensions listed under [Responsive Layout](#responsive-layout). Watch for a horizontal scrollbar appearing at the bottom of the page, which means something is too wide.

### Can I apply additional CSS styling in my game?

Yes! As long as they do not conflict with any of the required styles mentioned in the spec.

### Is it OK if some elements briefly appear and then disappear upon opening `index.html`?

Yes, though you can avoid it entirely by starting the screens you don't want visible with the `hidden` attribute in your HTML, rather than hiding them from JavaScript once the page has loaded.

## Acknowledgments

Original spec written by Zirui Zhao <zhaojer@umich.edu>.
Updated by the EECS 493 team.

This document is licensed under a [Creative Commons Attribution-NonCommercial 4.0 License](https://creativecommons.org/licenses/by-nc/4.0/). You're free to copy and share this document, but not to sell it. You may not share source code provided with this document.
