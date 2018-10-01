---
layout: post
title:  "100 Days of Code Day 41 - ng-book 2"
date:   2018-10-01 07:00:00
categories: 100DaysOfCode
---

# Missing saturday and catching up with sunday

I did not code on saturday and sunday. According to the rules below, I now owe Charity:Water €100 for missing saturday, and I can still catch up with sunday by carrying over the hour and doing 2 hours today. This log is the carry over hour for yesterday. Hopefully I can make the time tonight so I don't have to carry over monday's hour into tuesday.

# Different directories git-initiated in tree structure

Generating a new Angular project with Angular CLI automatically initiates the directory of that project with a new Git repo.
As I want to use [a single repo](https://github.com/bram-atmire/ng-book) for all of the ng-book 2 examples, I don't want each subfolder to be its own Git repo.

Next time I make a new subfolder and a new project I just need to add [--skip-git](https://medium.com/codingthesmartway-com-blog/creating-angular-projects-with-angular-cli-e32b2cb486da) to the ng new command.

To fix the wrong situation in my own directory tree, I deleted the .git folders from both the root and the subfolder, and re-initialised the subfolder.

# ng-book 2 (p53-59 of 668)

The ES6 backticks will also expand template variables, so they do more than just allowing multi line strings.

It looks like input elements don't need to be closed, but I don't know why yet.

# Day 42 Plan

Continue on p60 of [ng-book 2](https://www.ng-book.com/2/)

# Future days - DSpace 7 Angular

* Finish angular.io tutorials
* Translate of the standard messages keys in Dutch, to learn how i18n in Angular works
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* UI for enabling/disabling particular languages

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

# Sustainability - Raising the stakes - Looking for sponsors (unchanged)

I have raised the stakes by
* giving €100 to Charity:Water for every day I miss.
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win. These are the rules that I'll apply:

1. I can anticipate or fix a lost day by doing an hour extra the day before, or an hour extra the day after. In theory this means I can maximally compensate a streak of 2 missed days. 
2. Goal is to have a steady frequency, so I can't just do 8h on a sunday to get myself off the hook for the next 7 days.
3. Sponsor commitments are fully voluntarily: any sponsor can back out at any time.
4. My commitment is fully voluntarily: if I want to change the rules or back out, I can at any time.

I will raise the stakes this way and gather money for Charity:Water. Let me know if you want to sponsor me and for how much per completed day in September. September 1st is the first successfully completed day.

# September tracking

Will only log the failed days here. 

* Saturday September 29th

# Thanks to the following sponsors!

1. Jan & Hilde: €2 per successful day (Yes, these are my parents)


