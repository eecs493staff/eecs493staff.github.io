---
layout: spec
title: a5-artist-search
---

# EECS 493 Assignment 5: Artist Search

| Total      | Released | Due                    |
| ---------- | -------- | ---------------------- |
| 150 points | 3/14     | **4/5 at 11:59 PM ET** |

## Submission Instructions

**Unlike Assignments 2 and 3, this assignment must be opened through a local web server. See [Running the Assignment](#running-the-assignment). It will not work if you open `index.html` directly from your file system. Before submitting, please make sure your website loads correctly in Google Chrome this way. You should not need to install any packages (e.g. `npm install`) or build your code (e.g. `npm run build`).**

Please submit your work to Canvas as a zip file, named `a5_<uniqname>.zip`. Replace `<uniqname>` with your uniqname: e.g. `a5_zhaojer.zip`, note that the angle brackets should NOT be included in your filename. Renaming (e.g., "-1") done by Canvas is fine.

This zip file should have a _single directory_ containing _all files and directories_ provided in the starter code. In other words, the zip file should have the following structure.

```console
a5_uniqname
├── assets
│   ├── Back.svg
│   ├── Fwd.svg
│   ├── Library.svg
│   ├── Pause.svg
│   ├── Play.svg
│   ├── Repeat.svg
│   ├── Repeating.svg
│   ├── Shuffle.svg
│   ├── Song.svg
│   ├── VolumeDown.svg
│   ├── VolumeUp.svg
│   └── loading.gif
├── img
│   ├── 1.jpg
│   └── 2.jpg
├── index.css
├── index.html
└── script.js
```

Not following the upload instruction will result in a penalty.

## Assignment Objective

The objective of this assignment is for you to gain practical experience with the MVC pattern using Vue.js, a web application development framework, and with fetching data from a web API. Specifically, you will create a website that searches for artists using the iTunes API.

Watch this video for an overview of this assignment: [https://youtu.be/C4ekC9MYN9M](https://youtu.be/C4ekC9MYN9M)

_Remark: the video was recorded for an earlier version of this assignment that used the Bootstrap CSS framework. **Ignore anything it says about Bootstrap.** This version uses no CSS framework, and Vue is the only library involved. Watch it for what the finished site does._

_Remark: The search results from the video may not be what you get. To determine whether your results are correct, please see the [FAQ](#should-our-search-results-match-exactly-the-ones-in-the-spec) section._

## Grading Breakdown

The assignment has 9 main component (denominator of 150 points):

1. Search Bar - _25 points_
2. Artists Grid - _30 points_
3. Navigation Tabs - _5 points_
4. Track Information - _5 points_
5. Genre Selection - _20 points_
6. Sort Menu - _15 points_
7. Search History - _10 points_
8. Favorites - _15 points_
9. Play - _25 points_

## Starter Code

You will use the starter code we provide to complete this assignment.

Download and unpack the starter files (either using the following commands or simply navigating to the link).

```console
$ wget https://eecs493staff.github.io/a5-artist-search/starter_code.tar.gz
$ tar -xvzf starter_code.tar.gz
```

Here's a brief description for each of the starter files.

| `index.html` | HTML page **\[Write your HTML code in this file\]** |
| `script.js` | Imports Vue and creates one Vue instance for you **\[Write your JS code in this file\]** |
| `index.css` | All the styling for the finished page, including how it responds to window size \[Do NOT modify this file\] |
| `assets/` | A directory containing icons that you may use in your code |
| `img/` | A directory containing 2 image placeholders \[Your final code won't need them\] |

Remarks

- You aren't required to use any of the starter code, but it's there to help you.
- Please refer to Piazza for any modifications and clarifications.
- Make sure that your application (webpage) behaves properly on the latest version of Google Chrome. Your graders will use Chrome.
- To make sure your code runs correctly, it might be helpful to test it on a different computer.

## Running the Assignment

This assignment has to be opened through a web server. Double-clicking `index.html` will not work, for the reason explained under [CORS and the iTunes API](#cors-and-the-itunes-api). The short version is that the API will not answer a page that was opened straight off your disk.

You do not need to install anything. Open a terminal, move into the folder that contains your `index.html`, and run:

```console
$ python3 -m http.server 8000
```

Then open <http://localhost:8000> in Chrome. Leave the terminal running while you work; press Ctrl+C when you are finished.

VS Code's Live Server extension works too, if you prefer it. What matters is that the address bar says `localhost`, not a path beginning with `file://`.

Serving the page is also what lets this assignment use `<script type="module">`, the way we did in class. Assignments 2 and 3 had to use `defer` instead, because module scripts cannot load over `file://`.

## Helpful Resources

### iTunes API

- [Constructing Search](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html#//apple_ref/doc/uid/TP40017632-CH5-SW1)
  - Hint: Most useful parameters are _term_, _media_, and _attribute_.
  - **IMPORTANT UPDATE:** The archived Apple documentation above no longer lists the _attribute_ parameter. **Please also refer to [this documentation](https://performance-partners.apple.com/search-api), which includes a more comprehensive list of parameters used in this assignment.**
- [Search Examples](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/SearchExamples.html#//apple_ref/doc/uid/TP40017632-CH6-SW1)
- [Understanding Search Results](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/UnderstandingSearchResults.html#//apple_ref/doc/uid/TP40017632-CH8-SW1)

### Vue

- [Get Started using createApp](https://vuejs.org/guide/quick-start.html#without-build-tools)
- [Vue Cheat Sheet w/examples](https://www.vuemastery.com/pdf/Vue-Essentials-Cheat-Sheet.pdf)
- [Template](https://vuejs.org/guide/essentials/template-syntax.html)
  - Dynamically update HTML text using <code>&#123;&#123; &#125;&#125;</code>
  - Dynamically update HTML attributes using `v-bind`
  - Single JavaScript expressions can be used in <code>&#123;&#123; &#125;&#125;</code> for text and `" "` for attributes
- [Binding Classes (`v-bind`)](https://vuejs.org/guide/essentials/class-and-style.html)
  - Dynamically toggle a class depending on certain conditions
- [Conditional Rendering (`v-show`, `v-if`)](https://vuejs.org/guide/essentials/conditional.html)
  - Dynamically render a block (e.g. `<div>`) under certain conditions
- [List Rendering (`v-for`)](https://vuejs.org/guide/essentials/list.html)
- [Events (`v-on`)](https://vuejs.org/guide/essentials/event-handling.html)
  - Listener
  - Method Handler
  - Modifier (prevent page from reloading)
  - Keyboard events (listening for specific keys)
- For making API calls, use `fetch`, which is built into the browser:
  - [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
  - [Response.json()](https://developer.mozilla.org/en-US/docs/Web/API/Response/json)

### JavaScript

- [Object.keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
- [Object.entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)
- [Array.prototype.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
- [Array.prototype.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

### Other

The 'Description' and 'Track info.' tabs are a good illustration of the MVC pattern. There is no CSS framework doing the switching for you, so which tab is showing is simply part of your data, and the template renders whichever one your data says is open.

The thing to work out is that every track has its own pair of tabs, so a single "which tab is open" value is not enough. A common symptom of getting this wrong is that clicking one track's 'Track info.' tab switches all of them at once, or only ever switches the first one. Think about how to keep one value per result, not one value for the whole page.

The same idea covers the search history panel, the Favorites list, and the sort menu. Each of them is either open or closed, that is a piece of data, and the template shows or hides from it.

## Screenshots

### Landing Page

<img 
    src="images/search-bar.png" 
    width="100%" 
    alt="Music search interface with an empty search bar and no results displayed in the center of the screen."
/>

### Search for an Artist

<img 
    src="images/search-result.png" 
    width="100%" 
    alt="Music search interface showing results for the artist 'Ayokay.' Fifty tracks found, with several tracks displayed at a time."
/>

### "Track Info" Tab (for the left two results)

<img 
    src="images/track-info.png" 
    width="100%" 
    alt="Music search interface displaying results for the artist 'Ayokay.' Several tracks are visible. The first track’s info tab is selected, showing its track ID and the country of origin."
/>

### Sort

#### Menu

<img 
    src="images/sort-menu.png" 
    width="100%" 
    alt="An interface displaying music track results with controls to sort the results using a dropdown menu and filter them by genre. Selecting the dropdown filter opens options such as sort list results by: Reset to original, collection, and price"
/>

#### Sort by "Collection Name"

<img 
    src="images/sorted-collection.png" 
    width="100%" 
    alt="An interface displaying music track results. The results are sorted by collection."
/>

#### Sort by "Price"

<img 
    src="images/sorted-price.png" 
    width="100%"
    alt="An interface displaying music track results. The results are sorted by price."
/>

### Select the "Dance" and "Pop" Genres

Remark: Sort is reset to original in this screenshot.

<img 
    src="images/select-genre.png" 
    width="100%" 
    alt="An interface displaying music track results. In this screenshot the user has selected to filter by 'Dance' and 'Pop'."
/>

### Search History

#### Dropdown

<img 
    src="images/search-history.png" 
    width="100%" 
    alt="An interface displaying music track results. The search bar displays a list of past search results."
/>

#### After searching for "John Williams"

<img 
    src="images/search-history-add.png" 
    width="100%" 
    alt="An interface displaying music track results. The search bar displays a list of past search results. The user has just searched for artist 'John Williams' which has been added to the list of past search results."
/>

#### After deleting "ayokay"

<img 
    src="images/search-history-remove.png" 
    width="100%" 
    alt="An interface displaying music track results. The search bar displays a list of past search results. The search result 'Ayokay' has been removed from the result history."
/>

### Favorites

#### Left Panel

<img 
    src="images/favorites.png" 
    width="100%" 
    alt="An interface displaying music track results, each with additional options and information, including a star icon; selecting the star marks the track as a favorite and adds it to the “Favorites” folder in the side panel."
/>

#### After adding "Hedwig's Theme"

<img 
    src="images/favorites-add.png" 
    width="100%"
    alt="An interface displaying music track results, each with additional options and information, including a star icon; selecting the star marks the track as a favorite and adds it to the “Favorites” folder in the side panel." 
/>

### Play

<img 
    src="images/play.png" 
    width="100%" 
    alt="An interface displaying music track results, each with additional options and information, including a play button. Selecting the play button opens a now-playing display at the top of the screen showing the current track and a progress bar."
/>

### Narrower Windows

The screenshots above were all taken in a full width window. The page rearranges itself as the window gets narrower, and the two screenshots below show the same search at two smaller widths. The styling in `index.css` handles this for you, so you get it for free as long as you build your markup out of the classes it provides.

<div style="display: flex; flex-wrap: wrap; gap: 1rem; align-items: flex-start;">
  <img
    src="images/responsive-two-columns.png"
    style="width: 48%; min-width: 15rem;"
    alt="The search page in a fairly narrow window. The Favorites sidebar sits above the results, the genre filter buttons wrap onto three rows, and the track results are laid out in two columns."
  />
  <img
    src="images/responsive-one-column.png"
    style="width: 48%; min-width: 15rem;"
    alt="The same search in an even narrower window. The track results have dropped from two columns to one, and the genre filter buttons have rewrapped onto five rows."
  />
</div>

## Requirements

We outline the requirements for each of the components below. Everything listed in this section, unless labeled as "Suggested", is required. Please be sure to examine the overview video and screenshots to understand the expected behavior. Again, remember that your website does not have to look exactly like the one in the video/screenshots.

**Please read the [Helpful Resources](#helpful-resources) section for hints and learning resources.**

### General

Ground rules - _max 50 points off if not followed_

1. The primary point of the assignment is to use MVC pattern in developing the application using Vue.js. Therefore, reference and direct modification of HTML elements (such as `document.querySelector()`, `append()`, `document`) in JavaScript are NOT allowed.
   - Everything the page displays should follow from your Vue data. You change the data; Vue updates the page. _Reaching into the page yourself will result in significant deductions._
2. We've given you some starter code, and you'll only need to write JS code inside Vue instance(s) (in the JS file) and Vue directives in the HTML file.
   - We already created one Vue instance for you. You may add other instances if you prefer, but NO extra JS code should be written outside of Vue instances.
3. All the styling you need is already written for you in `index.css`, which defines a class for every part of the finished page.
   - Build your markup out of those classes. You are NOT allowed to define your own CSS classes or ids, and you should not need to.
     - i.e. Do NOT modify `index.css`.
   - You are NOT allowed to use inline styling (e.g. `style=''`). The _only_ exception to this rule is when implementing the [progress bar](#play-25-points), which you may use _exactly one_ instance of inline styling (`style=''`) to dynamically update its width.
   - This is deliberate: Assignment 2 was where you wrote the CSS. Here the point is the data and how the page follows from it, so the CSS is handled for you.
4. Vue.js is imported at the top of the provided `script.js`. No other library or framework is permitted.
   - In order for the page to work properly, make sure you
     - Have internet connection,
     - Leave the `import` line at the top of `script.js` as it is,
     - Do NOT modify anything inside the `<head>` tag in `index.html`.
   - Because `index.html` loads `script.js` with `type="module"`, the page has to be served over http. See [Running the Assignment](#running-the-assignment).
   - Note that `index.html` has some hard-coded data. This is just to show you an example, but the hard-coded data should eventually be replaced.
5. Follow the submission instructions at the beginning of the spec.
6. After unzipping your submission, the assignment should work when served from a local web server and opened in Google Chrome, as long as there is an internet connection. See [Running the Assignment](#running-the-assignment).
7. This assignment uses the iTunes API, which again requires internet access. Plan ahead if you will be in a situation that has no internet access. It is your responsibility to read the documentation and figure out the data structure of the JSON object.
8. This assignment requires online search and reading the documentation of Vue.js and iTunes API that we use. The assignment may include materials that are not covered in class. We believe that, in today's programming practice, searching and mining information from online materials is a significant part of a programmer's expertise.
9. Check out Piazza frequently for any changes or additional information.

### Search Bar (25 points)

- There is an input text box at the top left of the screen (already provided for you in the starter HTML file).
- When a user types a keyword (i.e., an artist's name) and presses the "enter" key, the entered keyword is used to make an AJAX request to the iTunes API, searching for _music_ tracks made by the artist(s) whose name contains (or is close to) this keyword.
  - Hint: Use `v-on:keyup` to check whether the key pressed was Enter.
  - Use `fetch()` for the AJAX call.
- The URL for the AJAX request and the returned JSON data are specified in the [iTunes API documentation](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html#//apple_ref/doc/uid/TP40017632-CH5-SW1)
  - Check out the [iTunes API section](#itunes-api) for a hint on which URL parameters you will need to get the correct results.
  - When constructing the request, only _music_ media types should be included.
  - Do not include any additional URL parameters that may change/restrict the results; just leave them as the default.
- Print out the returned JSON object in the console, using JS console.log(), when making requests for the APIs.
  - This should be the _only_ thing that is printed in the console.
  - We will take off points if the above requirements are not met.
- When there are no artists returned from iTunes, alert the user, using JS alert(), that no artist was found with the keyword.
- "Total _N_ found" message should display _N_ = the total number of artists (results) returned by the iTunes API.

### Artists Grid (30 points)

- The returned tracks of the artist should be displayed in two columns, where each result grid displays an image and related information of the track right next to each other (when the browser is in full size).
  - One exception will be the last row which may have less than two artist grids when the number of results is odd.
- Use the `track-grid` and `track` classes from `index.css` for this. The grid works out how many columns fit on its own, so you do not need to count them or decide when to wrap.
- Because of that, the layout is responsive once your markup is right: the number of columns changes as the window is resized, and drops to one on a narrow screen. Check this by dragging your window narrower, and compare against the [screenshots](#narrower-windows).
- Typically, iTunes will provide an image URL for each track returned. Use the first available URL in the properties.
- Note: We provided [screenshots](#screenshots) of the search result when a user searches for an artist. When unsure, please refer to these (and the assignment intro video).

### Navigation Tabs (5 points)

- The returned artists should also have their information displayed next to them in the navigation tabs.
- Use the `tabs`, `tab`, `tab-active`, and `tab-panel` classes from `index.css` for this and the next section. The starter file shows the markup for one set of tabs. Which tab is showing is up to your Vue data: see the [Helpful Resources](#other) section.
- The 'Description' tab should contain: artist name, track name, collection name, and collection price. These properties can be found in the response JSON object.
  - If the price is not provided, set the price to 0.
  - If one of the returned values is an empty string, display "No information provided".
- There should also be a "play" button and a "favorites" button under the description tab, but they are discussed later in the spec in their respective sections.

### Track Information (5 points)

- When clicking the 'Track Info.' tab, the system should display the Track ID (which is a unique identifier) & Country for that particular search result.
  - You may assume that Track ID and Country are always going to be provided by the API.
- This means, whenever you click on the 'Track Info.' tab, the unique identifier will be different for each different 'Track Info.' tab you click on. See the [screenshots](#track-info-tab-for-the-left-two-results) section for an example.
- Hint: The key to getting this section to work is figuring out how to get only that particular div to change when you click on that 'Track Info.' tab. Check out the [Helpful Resources](#helpful-resources) section if you would like a more specific hint.
- When clicking back to the 'Description' tab, the five types of information should still be there.

### Genre Selection (20 points)

- Create a list of tags of which genre labels are available from the search results. (See screenshots/video above)
- As a user toggles a genre, only the artists that are categorized in the selected genre should appear in the grid.
  - The number of results should update as well.
  - You can select and deselect genres.
  - The genres selected should be indicated by the change in the background color.
- Once you select other genres besides ALL, the ALL button should be deselected, indicated by a change in its background color.
- Use the `chip` class from `index.css` for the genre buttons, and add `chip-selected` to the ones currently selected. Binding that second class to your data is what makes the colour change: see [Binding Classes](#vue) in Helpful Resources.
- The genre selection works like a set union: The more genres that are selected the more results should be displayed.
- If ALL is selected, the other genres are deselected, and the results return back to the original list but maintaining the current sort selection. (see Sort Menu)
- The genre selected should automatically reset to ALL when you search for a new artist.

### Sort Menu (15 points)

- A "Sort list of results by: " button that displays a dropdown menu when clicked.
  - There are three options in the menu:
    - Reset to original
    - Collection Name
    - Price
- For "Reset to original", reset the displayed results to the original order.
  - This should be the default selection.
- For "Collection Name", sort results alphabetically by collection name.
- For "Price", sort results by increasing price.
- For API results that did not return a Collection Name or Price, they should be sorted as if their Collection Name was "No information provided" and Price was 0.
- The selected option should be indicated by a distinct background color.
- Use the `sort`, `sort-toggle`, `sort-menu`, and `sort-option` classes from `index.css` for this, adding `sort-option-active` to the option currently selected. Whether the menu is open and which option is selected are both your Vue data.
- When multiple genres are selected, the list of results should still be updated by the current sort selection (e.g., collection name or price).
  - In other words, when you select a genre, the sort option should not reset.
- The sort should automatically reset when you search for a new artist.

Here is another example of what the sort menu should look like and how it works.

In the dropdown menu, initially, it should be set as the "Reset to original" indicated below by blue background.

<img 
    src="images/sort-eg2-initial.png" 
    width="100%" 
    alt="An interface displaying music track results with controls to sort the results using a dropdown menu and filter them by genre."
/>

When selecting a different option, it should be changed to that selection, for example, selecting "Collection Name", indicated by the blue background.

<img 
    src="images/sort-eg2-collection.png" 
    width="100%" 
    alt="An interface displaying music track results with controls to sort the results using a dropdown menu and filter them by genre. Selecting the dropdown filter opens options such as sort list results by: Reset to original, collection, and price."
/>

After an artist search and sorting by "Collection Name", then selecting different genres should still update the list by "Collection Name".

In other words, if the user sorts by Collection Name, it should update the list sorted by collection name; after that, if the user picks a genre, e.g. Anime, it should update the Anime list sorted by collection name too.

<img 
    src="images/sort-eg2-genre.png" 
    width="100%" 
    alt="An interface displaying music track results with controls to sort the results using a dropdown menu and filter them by genre. In this screenshot the user has selected to filter by the Soundtrack genre."
/>

This should work when selecting any of the three sort options.

### Search History (10 points)

- When the user clicks on the input text box, a search history list should appear below the text box, displaying top 5 most recent searches made by the user.
  - The most recent search should always be displayed at the top of the list.
    - i.e. You should dynamically update the search history as the user makes more searches.
  - There should be no duplicates in the search history: If the user searches for an artist again, simply move this search up to the top of the list.
  - Even though only the top 5 most recent searches are displayed, your code should remember more than 5 searches.
    - This matters when deleting.
  - It's ok if a small box appears even when there are no previous searches.
- Clicking anywhere on the screen closes the search history.
- _When_ hovering over a search in the search history list, a cross mark appears on the right side.
  - Clicking on the cross mark deletes this search from the search history.
- When a search is deleted, all searches below should move up in the list by one.
  - Previously hidden searches (when number of searches in the history > 5) should also move up in the list, making them appear on the screen.
  - e.g., There are 6 searches in the history and only the top 5 are displayed on the screen; the user deletes a search, now there are 5 searches in the history and all 5 searches are displayed on the screen.
- Clicking on a search searches for this artist again.
  - Optional: You may use caching to save the previous search results to avoid repeated AJAX requests, but this is not required.
- Remark: It's ok if the search history resets after refreshing the page.

### Favorites (15 points)

- A "star" icon/button should be displayed at the bottom of the "description" tab of each track.
- Upon clicking the "star" button, add the corresponding track to "Favorites".
- When a track is added to "Favorites":
  - This track should appear under the "Favorites" tab/list in the left panel.
    - Each track should display:
      1. an image (same as the one in the search result)
      2. the track name
      3. the artist name
    - _When_ hovering over a track (in the "Favorites" tab):
      1. a "play" icon/button should appear on top of the track image
         - more on this in the Play section of the spec
      2. the track and artist names should scroll left (CSS code provided for you)
      3. a cross mark appears on the right side
  - The star icon in this track's description tab should show a change in appearance to indicate it has been added to Favorites.
    - e.g. from an outline star symbol (&#9734;) to a filled star symbol (&#9733;)
  - Remark: Favorites should NOT reset between searches.
    - e.g. If I added a track titled "Radioactive" from "Imagine Dragons" search results to Favorites and then searched "John Williams", "Radioactive" should still be in Favorites.
    - i.e. This essentially means that the Favorites can have tracks from different search results.
  - Remark: You cannot add the same track to Favorites twice (more than once).
    - e.g. If I added a track titled "Radioactive" from "Imagine Dragons" search results to Favorites, then searched "John Williams", and then searched "Imagine Dragons" again, "Radioactive" track's Description tab should still have a star icon appearance indicating it is added to Favorites (e.g. &#9733;).
- Upon clicking the star icon again OR clicking the cross mark (on the right side of the track in the left panel's Favorites tab), remove the corresponding track from Favorites.
- When a track is removed from "Favorites":
  - The track should no longer be displayed in the left panel's Favorites tab.
  - The star icon in this track's description tab should change back to its original state (e.g. no longer filled).
- The Favorites do not have to be displayed in the order they were added.
- Remark: It's ok if the Favorites reset after refreshing the page.

### Play (25 points)

- There are 3 (possible) locations on the screen where there is a "play" icon/button, which the user can use to play the corresponding track:
  - In the Description tab of a track
  - In the top panel
    - already implemented for you in starter HTML file
  - On top of a track's image in the left panel's Favorites list
    - only appears when this track is added to Favorites and the user is hovering over this track in the left panel's Favorites list
      see Favorites section of the spec for more details
- The "play" button in these 3 locations should all behave the exact same.
- Upon clicking the "play" button in (in any of the 3 locations):
  - The corresponding track plays.
    - Exception: Clicking the play button in the top panel initially when there was no previously playing track would not do anything.
  - The 3 "play" icons change to the "pause" icons.
  - The middle part of the top panel displays the information of the currently playing track, including:
    1. track image
    2. track name
    3. artist name
    4. collection name
    5. a progress bar
- While a track is playing:
  - The progress bar (in the top panel) should dynamically update indicating the progress of how much the song has been played.
  - The track and artist names of the corresponding track in the left panel's Favorites list should keep scrolling (just as if you are hovering over it).
- Upon clicking on either of the 3 "pause" buttons (i.e. in the top panel, in the corresponding track's description tab, or in the corresponding track in the left panel's Favorites list):
  - The currently playing track pauses.
  - All 3 "pause" icons change to "play" icons.
- When a track finishes playing on its own, the 3 "pause" icons should change to "play" icons.
- Clicking the "next" button selects a random track in the search result and plays it.
  - Playing follows the same behavior as mentioned previously.
- Clicking the "repeat" button plays the track on repeat and changes the icon appearance.
  - Use the svg from the "assets/" folder for the alternative appearance.
- Clicking on the "repeat" button again stops playing the song on repeat (i.e. finish the current play iteration and stop) and changes the icon appearance back to the original.
- Adjusting the volume slider should update the currently playing track's volume.

## CORS and the iTunes API

A browser will not let a page read a response from another website unless that website says it is allowed to, by sending back a header called `Access-Control-Allow-Origin`. When the header is missing, the request itself succeeds but the browser throws away the response and reports a **CORS error**.

The iTunes API sends that header only when the request comes from a real web address. A page opened directly from your disk has no such address. The browser reports its origin as `null`, and the API will not answer that. This is why the assignment has to be [served from a local web server](#running-the-assignment).

So if you see a CORS error, check the address bar first. It should read `http://localhost:8000`, not a path starting with `file://`.

It is also worth searching for a variety of artists while you work, and not defaulting to the same obvious name as everybody else, whether that is the artist from the demo video or just whoever is most famous at the moment. iTunes appears to throttle requests when hundreds of identical ones arrive from the same network, which is exactly what happens when a whole class tests with the same name on campus wifi.

So if one particular search starts failing while others still work, that is probably what you have hit, and not a bug in your code. Try a different artist before you go looking for one.

If you continue to have issues, please come speak to us in office hours or post on Piazza.

## FAQ

### Sometimes, the search result seems unrelated to the search keyword, is this fine?

Yes, as long as you are correctly using the 3 query parameters listed in the [iTunes API](#itunes-api) section.

### When I minimize the window to the minimum width, the text in one artist grid overlaps with the next artist grid, is this fine?

Yes.

### Should our search results match exactly the ones in the spec?

Not necessarily, since API results change from time to time. As long as you make sure you are using the 3 (and only those 3) parameters in the [iTunes API](#itunes-api) section, you should be all set.

## Acknowledgments

Original spec written by Zirui Zhao <zhaojer@umich.edu>.
Updated by the EECS 493 team.

This document is licensed under a [Creative Commons Attribution-NonCommercial 4.0 License](https://creativecommons.org/licenses/by-nc/4.0/). You're free to copy and share this document, but not to sell it. You may not share source code provided with this document.
