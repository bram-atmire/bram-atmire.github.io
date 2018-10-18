---
layout: post
title:  "100 Days of Code Day 55 - DSpace 7 Language and State"
date:   2018-10-18 07:00:00
categories: 100DaysOfCode
---

# Making my reducer and action files

I'm wondering how ngx-translate itself already handles some state changes, and whether there is any overlap on handling that I am about to put in. The API doesn't mention any of the following, so I definitely want to cater for:
* Deactivating a language: admin ensures that end users can no longer select a particular language
* Activating a language: admin extends the list of options to the end users with another language, from which the message catalog is present in DSpace.

But what about the action of language switching that the user does itself? What about the mere act of translating a key itself?
These all seem to work with the language switch feature right now, without having to implement any specific state.

I'll first try to get the activating & deactivating actions right, and then see how to treat the actual switching of languages here.

# Confusion about initial state - why is it important to set it in the reducer?

In the reducer, you need to define your initial state. For the language switch, the initial state currently gets set all the way up in app.component.ts, where the default language is loaded and the list of available languages is loaded from config. Not entirely sure if I somehow have to duplicate this from the reducer, or to read that initial state into the reducer.

# Passing arguments into the reducer

I modeled my reducer for the language switch state changes on the reducer for the header actions, which basically only contains expanding & collapsing, an action that doesn't have any input parameters. But when I want to activate or deactivate a language, I want to pass that language as a param.

Still have to figure out how to pass those along.

# People doing similar things

* [Where to translate with ngx-translate and ngrx in Angular 5?](https://stackoverflow.com/questions/50743119/where-to-translate-with-ngx-translate-and-ngrx-in-angular-5)
* [i18n with ngrx store - translating angular application](https://stackoverflow.com/questions/48545613/i18n-with-ngrx-store-translating-angular-application/48551317#48551317)

# Day 56 Plan

Continue with implementing the actions and the reducer for the language switch.
Continue with the [Redux fundamentals](https://blog.isquaredsoftware.com/presentations/2018-03-redux-fundamentals/#/18).
Continue implementation of the action to deactivate a language.

# Future days - DSpace 7 Angular

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

# September sustainability challenge - Completed

[The money has been wired](https://my.charitywater.org/bram-luyten/code-for-water) and I'm closing the books on the September sustainability challenge where I was sponsored for every successful day and where I would punish myself for every missed day.

# New sustainability challenge - Finish before Christmas

With today being day 43, there are 57 days of coding left. Setting the goal to get there before Dec 25th gives me a little more flexibility while still requiring a high frequency.

In terms of positive motivator, I'm currently thinking along the lines of a big reward at the end, while at the same time still wondering about something more incremental for Oct/Nov, or to have a self-punishment system in here as well.