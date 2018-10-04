---
layout: post
title:  "100 Days of Code Day 44 - Peeking at DSpace 7"
date:   2018-10-04 07:00:00
categories: 100DaysOfCode
---

# Peek at DSpace 7

## DSpace 7 Development instructions

Went through [DSpace 7 - Angular UI Development](https://wiki.duraspace.org/display/DSPACE/DSpace+7+-+Angular+UI+Development) on the DuraSpace wiki again. 

Found the [code style guidelines](https://angular.io/guide/styleguide): very extensive and likely a good point of reference for anything you have doubts about regarding style. Doesn't look that useful to read through entirely in one go.
 
Also found the [documentation style guidelines](http://typedoc.org/guides/doccomments/).

## Naming convention

The selectors for the components in DSpace 7 angular are all prefixed with ds-.
That way, these custom components can be separated out for others that are imported from elsewhere.

## Why are some module names prefixed with a plus and others aren't?

## What are .pipe files?

## How does i18n work?

The message catalog for English [is managed here](https://github.com/DSpace/dspace-angular/blob/master/resources/i18n/en.json).
Right now there was only a single catalog. Contributed a first Dutch translation to the development in https://github.com/DSpace/dspace-angular/pull/296
Interesting to see how this works with the [Waffle Board](https://waffle.io/DSpace/dspace-angular) to keep track of progress.

## How does testing in DSpace 7 work?

Jasmine, protractor, still have to look at in more detail

## Angular Universal

To support web crawlers who can't render JavaScript, the DSpace community is using Angular Universal to facilitate server-side rendering of the pages. [Angular Universal](https://angular.io/guide/universal) has a specific tutorial where the regular Tour of Heroes tutorial ended. Adding it as a future day plan to look into this.

# Day 45 Plan

Look further at DSpace 7 and i18n. Identify what needs to be done to actually see and use the Dutch language file I created.

# Future days - DSpace 7 Angular

* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
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

# September sustainability challenge - Completed

[The money has been wired](https://my.charitywater.org/bram-luyten/code-for-water) and I'm closing the books on the September sustainability challenge where I was sponsored for every successful day and where I would punish myself for every missed day.

# New sustainability challenge - Finish before Christmas

With today being day 43, there are 57 days of coding left. Setting the goal to get there before Dec 25th gives me a little more flexibility while still requiring a high frequency.

In terms of positive motivator, I'm currently thinking along the lines of a big reward at the end, while at the same time still wondering about something more incremental for Oct/Nov, or to have a self-punishment system in here as well.