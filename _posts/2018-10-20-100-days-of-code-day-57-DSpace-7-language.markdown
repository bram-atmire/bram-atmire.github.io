---
layout: post
title:  "100 Days of Code Day 57 - DSpace 7 Language"
date:   2018-10-20 15:52:00
categories: 100DaysOfCode
---

# Taking a break from language deactivation and state

At the office yesterday we were discussing persisting the change that an admin would make, when deactivating an interface language from the UI.

Initially, the list of languages can be loaded and provided from the [Environment Config File](https://github.com/DSpace/dspace-angular/blob/master/config/environment.default.js). But it wouldn't be preferable that changes to the list of activated languages would be written back to that file, because ideally the file is under version control in Git. Which would mean that the change would get lost whenever someone would execute a new build and pull the config changes back from git.

So a more desirable alternative is to persist this kind of change in the database, meaning that the DSpace 7 REST API would serve it. Even though interface language could be seen as something purely UI based, it's possible that UIs building on top of the REST API will want to store some UI related parameters in the DB. One way to move forward, would be an endpoint/structure of UI config, there the REST API can just store and serve value pairs of UI config, without really knowing or controlling any logic of what happens with those.

I'm taking a short break from this in order to focus on [feedback that came in from Art on the original language switch](https://github.com/DSpace/dspace-angular/pull/308).

# Pulling the names of the languages back OUT of i18n.

Art made a great point stating that the names of the languages themselves can NOT be translated. An end user who wants to switch language doesn't necessarily know what is language is called in another language.

So for the time being, I'm pulling the names of the languages OUT of the i18n file, and loading them from config.

# The header of the dropdown should state the active language, not the word "Language"

To make it clearer, a font awesome icon for language is added in front of it.

# Code style issues

The automated checks on my pull request were failing because of code style issues. Executing yarn run lint in the root of my project told me what they were: whitespace and " vs ' issues, and I took care of those.

# Changes shipped!

[My pull request](https://github.com/DSpace/dspace-angular/pull/308) was updated with new commits, that hopefully resolve all of the open comments.

# Day 57 Plan

Continue with implementing the actions and the reducer for the language switch.
Continue with [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux), video 6.
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