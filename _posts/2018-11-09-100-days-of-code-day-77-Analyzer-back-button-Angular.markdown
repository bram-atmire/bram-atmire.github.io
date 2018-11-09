---
layout: post
title:  "100 Days of Code Day 77 - Analyzer back button - Back to Angular"
date:   2018-11-09 07:02:00
categories: 100DaysOfCode
---

# Analyzer: back button on the item page

The very last tweak I made yesterday went straight to the server without testing. Bad idea.
In order for a user to go back to the repository analysis page, I added a back button but the rendering is off.

I got the rendering right, but it still left me unsatisfied with this back button. It mimics the browser's back button so it only sends a user back to the repository page if that's where they came from. If someone just shared the item page link, there's no way to get back to the repository analysis. For this to work, my Item controller should pass the URL to get back to the repo, to the Item view. 

Briefly looked into this, but it's not trivial mainly because I'm lacking documentation in my Item controller class. 

# Back to Angular testing

To get back into the problem of getting i18n assets loaded in my TestBed, I went back through the official [Testing Guide on angular.io](https://angular.io/guide/testing)

# Day 78 Plan

Ask my colleagues for assistance to access the assets and hopefully get a successful test run in place for the DSpace 7 Angular language switch.

# Future days - DSpace 7 Angular

* Investigate writing of tests and write tests for the original language switch.
* Continue with implementing the actions and the reducer for the language switch.
* Continue implementation of the action to deactivate a language.
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
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whenever something is committed to master.
* Add documentation to the methods of the item controller
* Change the back button on the item page with a real link back to the repository analysis, instead of the current history -1 hack.

# Future Days - Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

# Future days - Jekyll http://bram-atmire.github.io/ site

* Make it prettier

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.