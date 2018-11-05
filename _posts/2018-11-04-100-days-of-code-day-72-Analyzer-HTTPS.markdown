---
layout: post
title:  "100 Days of Code Day 72 - Analyzer HTTPs"
date:   2018-11-04 13:15:00
categories: 100DaysOfCode
---

# Taking a short break from Angular

Currently stonewalling on getting the tests to run for my language switch, I'm turning to another problem that needs to be solved urgently.

# Analyzer - the problem

I have worked and blogged earlier about the [Atmire Analyzer](https://analyzer.atmire.com), my free tool that helps repository managers to detect and resolve indexing problems with Google Scholar.

In the database to this tool, I essentially only want to keep a single record for every single DSpace repository. This is not trivial because institutions have often hosted their repositories under different URLs, context paths etc over time. 

A very common thing is that happens is that today or in the past, the repository was served both under http and https. The analyzer makes sure that only a single repository record exists for this repository, but either has the http or https url as the canonical one.

When a user then turns to the item analysis, the code currently enforces that the path to the item needs to exactly match the stored repository url. This needs to be made more flexible so that the item is tested against http and https.

# Changes made

When I get a Google Scholar Search Engine Results Page (SERP), I now test for the handle prefix + item identifier, specifically within the h3 that has the gs_rt class that marks a result.

# Day 73 Plan

Continue the fix for testing of item pages in https://analyzer.atmire.com in cases where the item url starting with https or http might differ from the stored repository url.

Ask my colleagues for assistance to access the assets and hopefully get a successful test run in place for the language switch.

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
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whever something is committed to master.

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