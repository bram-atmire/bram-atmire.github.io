---
layout: post
title:  "100 Days of Code Day 71 - Loading assets in Webpack"
date:   2018-11-03 20:52:00
categories: 100DaysOfCode
---

# Loading assets in Webpack.test.js

[Yesterday](http://bram-atmire.github.io/100daysofcode/2018/11/02/100-days-of-code-day-70-Access-assets-in-Test.html) I thought I figured out that webpack.test.js is the place to load the i18n translation file assets in order to make them available during testing.

Today, I'm putting this to the test (pun intended).

I tried to mimic the approach used in [webpack.common.js](https://github.com/DSpace/dspace-angular/blob/master/webpack/webpack.common.js#L98), where CopyWebPackPlugin is used to copy the i18n assets from the resource directory to the assets directory.

That didn't work, as the Karma test runner still complains about the i18n files that can't be found. Since I don't understand what's actually going on in those WebPack files, and the relation with the yarn package manager, I spent the rest of the hour reading up on WebPack and Yarn.  

# Yarn

Whether it's starting DSpace 7 angular, running tests, it's all initiated with "yarn run ..." commands. The scripts section in package.json in the root of the project, reveals what these commands actually execute.

# Day 72 Plan

Take a break from DSpace7/Angular and fix testing of item pages in https://analyzer.atmire.com in cases where the item url starting with https or http might differ from the stored repository url.

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