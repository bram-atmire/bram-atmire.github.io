---
layout: post
title:  "100 Days of Code Day 75 - Scholar Bot Detection"
date:   2018-11-07 08:53:00
categories: 100DaysOfCode
---

# Switching up the user agents

Not sure if it will make a difference, but to rule it out as a possibility i'm switching to a different user agent string.

# Sleeping 5 seconds between homepage request and search query

Right now, I first request the homepage to get (and set) the Google Scholar cookies. My query for the item results comes immediately after that. I'm putting my thread to sleep for 5 seconds to see if this makes a difference.

Unfortunately, it didn't

# Allowing users to manually set whether full text and metadata was found in Google Scholar

Even if I would be able to get passed the captcha today, changes are big that it would break again at an arbitrary point in the future.
So now I'm empowering users to change the settings themselves for whether metadata or full text show up in google scholar after a manual check.

Shipped this change !

# Day 76 Plan

1. Clean up CSS for listed items, both on the repository page, as well as for the paragraph text on the item pages. Font should be darker
2. Render the titles of the items on a repository page in different colours, depending on whether metadata and/or full text have been found.

After that, ask my colleagues for assistance to access the assets and hopefully get a successful test run in place for the DSpace 7 Angular language switch.

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