---
layout: post
title:  "100 Days of Code Day 76 - Analyzer CSS tweaks"
date:   2018-11-08 07:10:00
categories: 100DaysOfCode
---

# Yesterday I made it work

Today I make it pretty.

# Disabling full Scholar full HTML page logging

Removed the extra logging that I added in previous days again. If I ever turn this on again, I have to find a way to log something a little bit more specific than logging the entire HTML response, including all of the javascript that Scholar returns.

# Colour coding item titles on repository homepage

Before, all items were just rendered the same way on the repository analysis page. I have added color coding to the items that were not found in scholar show up in red.

I also added a file icon that shows in red when the full text is missing, and in green when the full text was correctly found.

# Refresh results for item - clarify behaviour

Yesterday I introduced the ability for repository managers to manually switch the metadata and full text presence to found, after they've done a manual verification.

However, the "Refresh Results" action is currently overriding this. Hoping that I can ever fix the automated verification on Google Scholar, I will keep this in place, but I will rename the button to "reset results".

# Day 77 Plan

Switch back to DSpace 7 Angular.

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