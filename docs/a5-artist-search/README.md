---
layout: spec
title: a5-artist-search
---

EECS 493 Assignment 5: Artist Search
======================================

| Total     | Released | Due                         |
| --------- | -------- | --------------------------- |
| 100 points| FIXME    | **FIXME at 11:59 PM ET**    |

## Submission Instructions

Please submit your work to Canvas as a zip file, named `a5_<uniqname>.zip`. Replace `<uniqname>` with your uniqname: e.g. `a5_zhaojer.zip`, note that the angle brackets should NOT be included in your filename. Renaming (e.g., "-1") done by Canvas is fine.

This zip file should have a *single directory* containing *all files and directories* provided in the starter code. In other words, the zip file should have the following structure.

```console
a5_uniqname
├── README.txt (OPTIONAL)
├── img
│   ├── 1.jpg
│   └── 2.jpg
├── index.css
├── index.html
├── loading.gif
└── script.js
```

Not following the upload instruction will result in a penalty.

## Assignment Objective

The objective of this assignment is for you to gain practical experience with the MVC pattern using Vue.js, a web application development framework, and Bootstrap, a CSS framework for responsive design. Specifically, you will create a website that searches for artists using the iTunes API.

Watch this video for an overview of this assignment: [https://youtu.be/uZ_q3TYPZTY](https://youtu.be/uZ_q3TYPZTY)

*Remark: The search results from the video may not be up to date. Please refer to the screenshots below for more recent, accurate results.*

## Grading Breakdown

The assignment has 6 main components and 1 optional component (denominator of 100 points):

1. Search Bar - *25 points*
2. Artists Grid - *30 points*
3. Navigation Tabs - *5 points*
4. Track Information - *5 points*
5. Genre Selection - *20 points*
6. Sort Menu - *15 points*
7. (Optional) Bonus Features - *up to 10 points*

## Starter Code

You will use the starter code we provide to complete this assignment.

Download and unpack the starter files (either using the following commands or simply navigating to the link).

```console
$ wget https://eecs493staff.github.io/a5-artist-search/starter_code.tar.gz
$ tar -xvzf starter_code.tar.gz
```

Here's a brief description for each of the starter files.

| `index.html` | HTML page **\[Write your HTML code in this file\]** |
| `script.js` | Placeholder for one Vue.js instance **\[Write your JS code in this file\]** |
| `index.css` | Additional customized style \[Do NOT modify this file\] |
| `loading.gif` | Show this gif while waiting for fetch \[Optional\] |
| `img/` | A directory containing 2 image placeholders \[Your final code won't need them\] |

Remarks

- You aren't required to use any of the starter code, but it's there to help you.
- Unless you know what you are doing, please do NOT modify anything inside the `<head>` tag in `index.html`.
- Please refer to Piazza for any modifications and clarifications.
- Make sure that your application (webpage) behaves properly on the latest version of Google Chrome. Your graders will use Chrome.
- To make sure your code runs correctly, it might be helpful to test it on a different computer.

## Helpful Resources

### iTunes API

- Constructing Search: <https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html#//apple_ref/doc/uid/TP40017632-CH5-SW1>
    - Hint: Most useful parameters are *term* and *attribute*.
- Search Examples: <https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/SearchExamples.html#//apple_ref/doc/uid/TP40017632-CH6-SW1>
- Understanding Search Results: <https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/UnderstandingSearchResults.html#//apple_ref/doc/uid/TP40017632-CH8-SW1>

### Vue

- Get Started using createApp: <https://vuejs.org/guide/quick-start.html#without-build-tools>
- Vue Cheat Sheet w/examples: <https://www.vuemastery.com/pdf/Vue-Essentials-Cheat-Sheet.pdf>
- Template: <https://vuejs.org/guide/essentials/template-syntax.html>
    - Dynamically update HTML text using <code>&#123;&#123; &#125;&#125;</code>
    - Dynamically update HTML attributes using `v-bind`
    - Single JavaScript expressions can be used in <code>&#123;&#123; &#125;&#125;</code> for text and `" "` for attributes
- Binding Classes (`v-bind`): <https://vuejs.org/guide/essentials/class-and-style.html>
    - Dynamically toggle a class depending on certain conditions
- Conditional Rendering (`v-show`, `v-if`): <https://vuejs.org/guide/essentials/conditional.html>
    - Dynamically render a block (e.g. `<div>`) under certain conditions
- List Rendering (`v-for`): <https://vuejs.org/guide/essentials/list.html>
- Events (`v-on`): <https://v2.vuejs.org/v2/guide/events.html>
    - Listener
    - Method Handler
    - Modifier (prevent page from reloading)
    - Keyboard events (listening for specific keys)
- For making api calls, we can use the following. Both are supported in Vue 3.
    - `fetch`: <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch>
    - `Axios`: <https://axios-http.com/docs/example>

### JavaScript

- Object.keys(): <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys>
- Object.entries(): <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries>
- Array.prototype.sort(): <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort>
- Array.prototype.forEach(): <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach>
- Arrow functions: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions>

### Bootstrap

- Intro: <https://getbootstrap.com/docs/5.3/getting-started/introduction/>
- Button (btn): <https://getbootstrap.com/docs/5.3/components/buttons/>
- Dropdown: <https://getbootstrap.com/docs/5.3/components/dropdowns/>
- Navigation tabs: <https://getbootstrap.com/docs/5.3/components/navs-tabs/>
- Grid System: <https://getbootstrap.com/docs/5.3/layout/grid/>

### Additional Tips/Hints

When trying to toggle the 'Description' and 'Track info.' tabs, take a look at this tutorial and play around with the code. Note how this can be achieved simply using Bootstrap and HTML.

Specifically, quoting directly from it: 'Add `data-toggle="tab"` to each tab, and add a `.tab-pane` class with a unique ID for every tab and wrap them in a `.tab-content` class.'

If you have trouble (e.g. clicking on 1 Description tab changes all Description tabs, or no matter which Description tab is clicked, only 1 Description tab changes), make sure the stuff bolded is implemented correctly. Put into context of our assignment, each 'Description' and 'Track info.' tab must have its own unique ID (i.e. `<div id='[something unique]'> </div>`). In other words, suppose there are 50 songs returned by the API call, then there will be 50 'Description' and 'Track info.' tabs, so we need 50 unique IDs for 'Description' and 50 unique IDs for 'Track info.'

Note: This is not the only way to achieve this behavior, but it is in my opinion the easiest way to do so.
