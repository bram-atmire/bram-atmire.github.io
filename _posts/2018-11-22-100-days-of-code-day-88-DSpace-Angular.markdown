---
layout: post
title:  "100 Days of Code Day 88 - Persisting state of activated languages "
date:   2018-11-22 07:00:00
categories: 100DaysOfCode
---

# Persistent state of the activated languages in DSpace 7

Picking up on the work to allow an administrator to de-activate an activated language, I'm investigating if it's possible to make changes at runtime to environment.default.js. This is currently where the list of active languages is configured, for initialization at runtime.

Everything I read makes it clear that the env variables are set at build time and that all of these are not supposed to change at runtime.

Thinking again about my requirements, they boil down to:
* At an initial build/run of DSpace 7, all of the available languages should be active. It's beneficial for repositories to be served in as many interface languages as possible, so admins should be motivated to use as many of them as they are comfortable with.
* Because many repository admins don't have back end server access and are not privileged to rebuild the application, I find it important that they can activate and deactivate interface languages through the UI itself, at runtime
* Once they have decided to for example, deactivate 20 languages of the 25 languages that are available, it's important that this change persists restarts and rebuilds of the application. 
* If new languages get added, possibly in a minor update of DSpace that is rebuilt and deployed, the administrator should be able to activate that new language. So once the admin has made his or her initial decision on which languages should be active, we can't have new languages being automatically activated.

When considering all of these requirements, I can't help to think that the only solution is somehow to persist this configuration in the REST backend of DSpace, even though that back end is pretty much agnostic about the UI being used.

The Angular UI, or any UI for that matter, should be able to push a set of config keys and values for persistent storage to the REST back end, leaving the REST back end at the same time agnostic of what they represent.

# Secrets in environment files

Accidentally, I fell on two articles saying something totally different on whether you should put secrets or not in these environment files:
* [Properly Set Environment Variables for Angular Apps with gulp-ng-config](https://scotch.io/tutorials/properly-set-environment-variables-for-angular-apps-with-gulp-ng-config) states that you can put credentials in there
* [Becoming an Angular Environmentalist](https://blog.angularindepth.com/becoming-an-angular-environmentalist-45a48f7c20d8) states that the contents of the env file are completely visible/accessible to the client and that as such, you should never put secrets in there.

# Day 89 Plan

Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.

# Future days - DSpace 7 Angular

* UI for enabling/disabling particular languages
    * Continue with implementing the actions and the reducer for the language switch.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
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