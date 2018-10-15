---
layout: post
title:  "100 Days of Code Day 52 - DSpace 7 Language"
date:   2018-10-15 06:57:00
categories: 100DaysOfCode
---

# Disabling activated languages

To render an X to delete a language, as part of the unordered list (ul), [li element with delete image on right with css](https://stackoverflow.com/questions/10487041/li-element-with-delete-image-on-right-with-css) put me on the right path.

The code example [add and remove items to a list](https://codepen.io/gfrancesca/pen/gbpoxQ) reminded me to use a font awesome icon instead of writing a text X myself.

The icon wasn't aligned with the middle of the text and vertical align: middle wasn't working. In [How to center text vertically with a large font-awesome icon?](https://stackoverflow.com/questions/17309928/how-to-center-text-vertically-with-a-large-font-awesome-icon), I leared that if an element isn't aware of the line height, line-height inherit can fix it.

# Width of the dropdown relative to the label of the authentication message

When certain language names get too long in a particular language, the X button is being pushed to the second line, like is happening here:

![X button moving to the line below](../../../../assets/img/2018-10-15-dropdown-01.png)

I tried to fix this by playing with the min-width value of the dropdown menu, which seemed to work to some extent.
```css
.dropdown-menu {
  min-width: 14rem;
}
```

![Min-width fix on the dropdown menu](../../../../assets/img/2018-10-15-dropdown-02.png)

But when the text on the login button gets too short, the side effect is that the x symbols are no longer visible at all.

![Login label too short](../../../../assets/img/2018-10-15-dropdown-03.png)

# Bonus

Figured out how to work with images in this blog. The trick to resize them though with =100x at the end of the URL and the relative paths didn't work yet though.

# Day 53 Plan

The action on the x button doesn't work at the moment. It likely requires me to work with observables and subscribe to them, in order to have this work. Will try to get the button to actually work.

# Future days - DSpace 7 Angular

* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* UI for enabling/disabling particular languages
* Learn how to write tests and write them for the language functionality
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* Transition from plain CSS to SASS to make it prettier and learn about SASS at the same time
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whever something is committed to master.

# Future Days - Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

# Future days - Jekyll http://bram-atmire.github.io/ site

* Make it prettier

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# September sustainability challenge - Completed

[The money has been wired](https://my.charitywater.org/bram-luyten/code-for-water) and I'm closing the books on the September sustainability challenge where I was sponsored for every successful day and where I would punish myself for every missed day.

# New sustainability challenge - Finish before Christmas

With today being day 43, there are 57 days of coding left. Setting the goal to get there before Dec 25th gives me a little more flexibility while still requiring a high frequency.

In terms of positive motivator, I'm currently thinking along the lines of a big reward at the end, while at the same time still wondering about something more incremental for Oct/Nov, or to have a self-punishment system in here as well.