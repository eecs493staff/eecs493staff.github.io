EECS 493 Course Website
=============

The website is hosted by GitHub Pages from the `/docs/` directory in the `master` branch, containing the course homepage website (in `eecs493.org/`), and the assignment specs and starter code (in directories with prefix `a`).

The course homepage was adapted from eecs485.org. The specs were written using primer spec.

## Contributing

### Course Website

To update the course website, modify the files in `/docs/eecs493.org/` in `master` branch and push to GitHub.

A list of items that need to be updated each semester for the course website is listed below (nearly comprehensive, please add more items to this list if you find them). Feel free to uncheck/check items off of this list as you update the website.

`syllabus.html`

- [x] Term (e.g., Winter 2025)
- [x] Instructors and their contact info
- [x] Update previous semester's exemplary final projects in `final-project/README.md`

`index.html`

- [x] Links to course resources in the left navigation menu (e.g. Piazza, Canvas, Gradescope, etc.)
- [x] Term (pick a color of your choice!)
- [x] Announcement (e.g., write something like "Welcome to EECS 493!" and other important info)
- [ ] Course Info cards
    - [x] Lecture time and location
    - [ ] Links to lecture resources (i.e., recordings and slides)
    - [ ] Links to discussion resources (i.e., recordings and slides)
    - [x] Remove previous semester's assignment/project info cards (e.g., "Project Milestone 4")
    - [ ] Assignment card
        - [ ] Due date
        - [x] Title (e.g., Assignment 1: PEERRS Training)
        - [ ] Links to spec and canvas submission portal
    - [ ] Project milestone card
        - [ ] Due date
        - [x] Tilte (e.g., Milestone 0: Team Formation)
        - [ ] Links to spec and canvas submission portal
- [ ] Course Google Calendar link
- [ ] Course schedule (this section is quite long and tedious)
- [ ] People section
    - [x] Staff email
    - [ ] For every member: photo, name, email
    - [ ] For IAs/GSIs: include which lab section (time and location) do they teach

### Assignment Spec and Starter Code

To update the assignment spec, modify the markdown file in each of the assignment directories (e.g., `/docs/a2-asteroids-menu/`).

Do NOT directly modify the starter code in this repo; please see each assignment's own repos for more instructions.

## Future TODOs

- Upgrade to GitHub Teams to host course website from a private repo - [#2](https://github.com/eecs493staff/eecs493staff.github.io/issues/2)
    - Can also encapsulate each assignment spec into its own website by moving them to their respective private repos
- Improve GitHub Pages config to fix Google search result issue - [#3](https://github.com/eecs493staff/eecs493staff.github.io/issues/3)
