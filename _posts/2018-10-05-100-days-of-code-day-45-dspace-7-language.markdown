---
layout: post
title:  "100 Days of Code Day 45 - DSpace 7 Language"
date:   2018-10-05 07:00:00
categories: 100DaysOfCode
---

# DSpace 7 Language switch

As I made a [Dutch translation of the current DSpace 7 messages](https://github.com/DSpace/dspace-angular/pull/296) yesterday, I now want to see how a simple language switcher could be added to the UI.

The spec in DSpace is currently that the language should be initialised to the user's browser language, and if that one is not available, default to a default language, English in most cases.

But in order not to get ahead of of myself, I just want to initialise on English (like currently is the case), show which languages are available, and allow the user to switch.

# NGX-Translate

Would figure that this has been done before ... so reading in the NGX translate documentation.

Tutorial: [How to translate your Angular app with ngx-translate](https://www.codeandweb.com/babeledit/tutorials/how-to-translate-your-angular-app-with-ngx-translate)

Language switching actually looks very easy in the tutorial. However, only a simple, single app component is used there. In the layout, I want the lanugague switch to be placed next to login in the top level nav bar, so I would look for such a component to modify. However, the impact of the change should be across the entire app.

Got stuck at getting access to the translate service in the header, but [reported my progress to the community](https://github.com/DSpace/dspace-angular/issues/298) so maybe there's someone who will help out.
 
# Day 46 Plan

Continue work on the language switch.

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