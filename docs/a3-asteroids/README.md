---
layout: spec
title: a3-asteroids
---

EECS 493 Assignment 3: Asteroids Game
======================================

| Total     | Released | Due                         |
| --------- | -------- | --------------------------- |
| 100 points| FIXME    | **FIXME at 11:59 PM ET**    |

## Submission Instructions

Please submit your work to Canvas as a zip file, named `a3_<uniqname>.zip`. Replace `<uniqname>` with your uniqname: e.g. `a3_zhaojer.zip`, note that the angle brackets should NOT be included in your filename. Renaming (e.g., "-1") done by Canvas is fine.

This zip file should have a *single directory* containing *all files and directories* provided in the starter code. In other words, the zip file should have the following structure.

```console
a3_uniqname
├── index.html
├── scripts
│   ├── jquery.min.js
│   └── page.js
├── src
│   ├── arrowkeys.png
│   ├── asteroid.png
│   ├── audio
│   │   ├── collect.mp3
│   │   ├── die.mp3
│   │   └── pew.mp3
│   ├── frontpage_background.jpg
│   ├── player
│   │   ├── player.gif
│   │   ├── player_down.gif
│   │   ├── player_left.gif
│   │   ├── player_right.gif
│   │   ├── player_shielded.gif
│   │   ├── player_shielded_down.gif
│   │   ├── player_shielded_left.gif
│   │   ├── player_shielded_right.gif
│   │   ├── player_shielded_up.gif
│   │   ├── player_touched.gif
│   │   └── player_up.gif
│   ├── port.gif
│   └── shield.gif
└── style
    └── index.css
```

Not following the upload instruction will result in a penalty.

## Objective

The objective of this assignment is for you to gain practical experience in building an interactive single-page web application with HTML, CSS, and JavaScript/jQuery. Specifically, you will be creating a game called "Asteroids" as outlined in this spec. No external library, other than jQuery, is allowed.

Watch this video for an overview: [https://youtu.be/waDMWIfT8yg](https://youtu.be/waDMWIfT8yg)

## Grading Breakdown

This assignment has 8 main components (denominator of 100 points):

1. Asteroids spawn randomly from different directions - *25 points*
2. Shields and portals spawn at certain time intervals - *15 points*
3. A rocket (controlled by the user) with the goal of traveling through portals - *15 points*
4. A scoreboard - *5 points*
5. Sounds - *5 points*
6. A “Get Ready” splash screen - *5 points*
7. A game over page - *15 points*
8. Overall functionality - *15 points*

## Starter Code

You will use the starter code we provide to complete this assignment.

Download and unpack the starter files (either using the following commands or simply navigating to the link).

```console
$ wget https://eecs493staff.github.io/a3-asteroids/starter_code.tar.gz
$ tar -xvzf starter_code.tar.gz
```

Here's a brief description of each of the starter files.

| `index.html` | Some containers (divs) for the game window and the game board are defined; write your HTML code here |
| `style/index.css` | Some stylings for the game window, game board, and images are defined; write your CSS code here |
| `scripts/page.js` | Here is a list of things provided:

1. Some comments describing the structure of the code
2. Some global variables for storing game states/data
3. An Asteroids class is defined (Asteroids that are randomly generated and travels linearly across the gameboard)
4. Event handler for arrow key presses
5. Additional helper functions (e.g. determining collision);

write your JS code here |
| `scripts/jquery.min.js` | jQuery library source code; do NOT modify |
| `src/` | Images and audios for your website; do NOT modify |

Remarks:

- You will need to import all your Assignment 2 code into Assignment 3 starter code.
    - See Overall Functionality section for details
- You may choose to not use the starter code and implement those functionalities yourself.
- Please check Piazza for any modifications and clarifications.
- Make sure that your application behaves properly on the latest version of Google Chrome. Your graders will use Chrome.


