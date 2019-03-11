---
layout: post
title:  "DSpace 7 - PO transition"
date:   2019-03-11 22:59:00
categories: DSpace7
---

# Issued pull request

Even though this work wasn't entirely finished after my last work on it in February, I issued [a pull request](https://github.com/DSpace/dspace-angular/pull/366) to get some other eyes on it and to bring it closer to finalization.

# Rebasing again

Because I was again a number of new commits on master behind, I have rebased again. Also tried to take care of the 
comments that came in from the reviewers.

# Next actions

The JSON catalog has grown substantially again, a lot more messages remain to be added to the .pot catalog.

## DSpace 7 Angular

* Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.
* UI for enabling/disabling particular languages
    * Continue with implementing the actions and the reducer for the language switch.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

## Analyzer.atmire.com work

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
* Create a new item test to check if the publication date is correct, or has a high chance of being wrong

## Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

## Jekyll http://bram-atmire.github.io/ site

* Make it prettier

## Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.
Look into web.dev from google for this (thank you Philip)

## Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)