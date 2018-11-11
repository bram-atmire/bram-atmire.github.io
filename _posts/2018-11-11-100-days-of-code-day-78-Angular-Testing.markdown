---
layout: post
title:  "100 Days of Code Day 78 - Analyzer Testing"
date:   2018-11-11 20:20:00
categories: 100DaysOfCode
---

# Forget about loading assets, mock everything you don't explicitly want to test

Friday's words of my sensei and Angular guru Art were short but firm.
He strongly discouraged me to go further down the path of trying to load the i18n resources in the testbed for my component.

Instead, I should revisit the code of my component, take a closer look what it actually is that I wrote there, and figure out what I want to test exactly.

# What I don't want or need to test

I don't want to test the actual language switching, as this is provided by the ngx-translate library.

# Test 1: The switch should disappear if there is only one active language

For this test, I have to mock the constructor with only a single language active. And then I somehow have to test that the component doesn't get rendered.

# Test 2: My custom method to return the active language should return the actual active language

I have to create a mock with a particular language initialised as the active one, and then I have to test if my custom method to return this one actually does that.

# Test 3: My custom method to return a label for any of the active languages


# Day 79 Plan

Continue trying to get tests to work.

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