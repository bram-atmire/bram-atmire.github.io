---
layout: post
title:  "100 Days of Code Day 68 - Translation Loaders"
date:   2018-10-31 07:10:00
categories: 100DaysOfCode
---

# Interaction between app.module.ts, browser-app.module.ts and server-app.module.ts

Yesterday I was wondering about the empty [TranslateModule.forRoot(); import in app.module.ts](https://github.com/DSpace/dspace-angular/blob/master/src/app/app.module.ts#L62). This lead me to think that DSpace 7 isn't using a loader for the language files and I [created a new issue](https://github.com/DSpace/dspace-angular/issues/318) to ask about this. 

Turns out app.module.ts is not loaded directly, but is loaded to browser-app.module.ts when the app is executed in the browser, and in server-app.module.ts when the app is loaded on the server. The latter is required if crawlers/users can't execute javascript on the client side.

Both of them specify a different loader
* Loader in [server-app.module.ts](https://github.com/DSpace/dspace-angular/blob/master/src/modules/app/server-app.module.ts#L26)
* Loader in [browser-app.module.ts](https://github.com/DSpace/dspace-angular/blob/master/src/modules/app/browser-app.module.ts#L26)

This all leaves me wondering about the following after today's hour:
* When writing tests, should there be abstraction of whether the app runs on server or in the browser? 
* What kind of loader should I use in the test?
* If both server-app.module.ts and browser-app.module.ts already make the forRoot call on translate module, why is it still being called with empty values in app.module.ts ?

It's really frustrating that the further I venture into this, the more complex and confusing it seems to get.

# Day 68 Plan

Solve the dependency injection problems for the tests

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