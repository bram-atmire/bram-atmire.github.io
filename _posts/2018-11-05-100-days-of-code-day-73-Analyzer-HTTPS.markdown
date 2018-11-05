---
layout: post
title:  "100 Days of Code Day 73 - Analyzer HTTPs"
date:   2018-11-05 20:30:00
categories: 100DaysOfCode
---

# Input field for analyzing an item

In the current repository detail screen, a user can add a url to an item. However, it's enforced that this url starts exactly with the repository URL. Because I want to support both http and https variants, I want to make this check softer to only check for the hostname. 

[Remove URL Prefix from String (http:/, www, etc.)](https://stackoverflow.com/questions/16673628/remove-url-prefix-from-string-http-www-etc) led me to the use of java.net.URI for comparing the hostnames.

Locally, it seems to work great now. On the server however, the items are not successfully detected on Google Scholar. In order to see what's up, I added additional logging. If that doesn't work out, I can also look into attaching a remote debugger to figure it out.

# Day 73 Plan

Investigate on the server with my additional logging to detect the root cause for difference in behaviour locally vs on the server.

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