---
layout: post
title:  "100 Days of Code Day 56 - DSpace 7 Language and State"
date:   2018-10-16 07:00:00
categories: 100DaysOfCode
---

# Redux Fundamentals continued + egghead tutorial

Finished the [Redux fundamentals](https://blog.isquaredsoftware.com/presentations/2018-03-redux-fundamentals/#/18), where the last pieces didn't sound that relevant as they seemed to be React specific.

On to [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux).

Things worth remembering:
* The whole state of the application is a single javascript object
* The state tree itself is immutable. To make changes, components have to dispatch actions that describe in the minimal way how state changes.
* Pure functions are functions of which the output solely depends on the input parameters. e.g. it's not getting any objects or inputs elsewhere. They do not modify the values of the objects passed to them.
* Order of development
  * Write the reducer first
* In ES6, you can declare a default value for a function input parameter in case you get passed undefined. This helps you to take the logic for handling illegal input values from the method implementation to the signature.

Saw the first five videos of the egghead tutorial and they are really good. 

# Feedback on my pull request for the original language switch

A number of changes were requested to the [original language switch implementation](https://github.com/DSpace/dspace-angular/pull/308) that I need to process before it will be accepted.

# Day 57 Plan

Continue with implementing the actions and the reducer for the language switch.
Continue with the [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux).
Continue implementation of the action to deactivate a language.

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