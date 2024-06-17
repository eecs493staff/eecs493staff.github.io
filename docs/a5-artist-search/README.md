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
| `img/` | A directory containing 2 image placeholders \[Your final code won’t need them\] |

Remarks

- You aren’t required to use any of the starter code, but it’s there to help you.
- Unless you know what you are doing, please do NOT modify anything inside the `<head>` tag in `index.html`.
- Please refer to Piazza for any modifications and clarifications.
- Make sure that your application (webpage) behaves properly on the latest version of Google Chrome. Your graders will use Chrome.
- To make sure your code runs correctly, it might be helpful to test it on a different computer.
