---
layout: post
title:  "100 Days of Code Day 89 - Git"
date:   2018-11-23 07:00:00
categories: 100DaysOfCode
---

# Git: moving code between remotes

We currently have a fix sitting on an internal Atmire git repository for which the client asked me yesterday if we can make a pull request for this, in their own repository on Github.

Instead of burdening my already overloaded tech lead, I thought I can give this a shot myself.

At first instance, I wanted to leave IntelliJ IDEA project creation etc out of this, since I'm not immediately planning on making any code changes on this codebase in IDEA.

Steps I took:

1. Forked the client's repository on Github to my own account
2. made a clone of that repository on my local machine in a new folder
3. Added the Atmire repository [as another remote](https://help.github.com/articles/adding-a-remote/).
4. git fetch atmire to get all references of the Atmire repo locally
5. cherry picked the two commits that should be part of the pull request to the client
6. pushed my local branch to my account in Github
7. Issued my pull request from Github

And there it was: https://github.com/milieuinfo/dspace54-atmire/pull/1 

# Mysteriously reappearing metadata fields

For this same client, investigated another report on metadata fields that were miraculously re-appearing after being deleted from a DSpace metadata schema 

# Day 89 Plan

Investigate the transition from JSON language files to .po files for DSpace 7.

# Future days - DSpace 7 Angular

* Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.
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