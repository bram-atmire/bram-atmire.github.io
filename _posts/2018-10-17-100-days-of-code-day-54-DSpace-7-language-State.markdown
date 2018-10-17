---
layout: post
title:  "100 Days of Code Day 54 - DSpace 7 Language and State"
date:   2018-10-17 07:00:00
categories: 100DaysOfCode
---

# Time to learn about state

If the admin is supposed to be able to make a live config change from the UI, e.g. disabling a specific language, that change needs to be applied consistent in the dropdown menu and also needs to persist for all users.

This makes me wonder about two things:
* Can I write live into the Environment.default.js file or update the config in some other way?
* Instead of working with a static list of languages, should I somehow use Observable and subscribe to it?
* How exactly comes ngrx & redux into play here, as they are important components of how [DSpace 7 Angular handles state changes](https://wiki.duraspace.org/display/DSPACE/DSpace+7+-+Angular+UI+Development#DSpace7-AngularUIDevelopment-Statechanges). For redux, Art had already recommended me this [free egghead tutorial](https://egghead.io/courses/getting-started-with-redux).

I started off with the [Redux fundamentals slideshow](http://blog.isquaredsoftware.com/2018/03/presentation-reactathon-redux-fundamentals/). Worth remembering:
* map() takes an array and produces a new array, applying the function passed along to all values in the array. 
* reduce() produces a single value from an array, by applying a function from left to right, on all values in the array.

# Concepts that need to be applied on the deactivate language feature

State is a collection of plain objects, gathered in a central store.
To change the state, I need to dispatch an action. In this case, the action will be DEACTIVATE_LANGUAGE.
It's best practice to make an action creator function to make this action object, instead of making that object in another (longer) method.

The actual removing of the language needs to be built in a reducer. This reducer takes the state (of the activated languages) before the removal, applies the action of removing, and returns a new state.

# Day 55 Plan

Continue with the [Redux fundamentals](https://blog.isquaredsoftware.com/presentations/2018-03-redux-fundamentals/#/18).
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