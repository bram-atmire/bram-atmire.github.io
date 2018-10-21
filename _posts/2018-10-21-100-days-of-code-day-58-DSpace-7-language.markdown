---
layout: post
title:  "100 Days of Code Day 58 - Egghead Redux course continued"
date:   2018-10-21 20:06:00
categories: 100DaysOfCode
---

# Continuing Egghead Redux tutorial video 6 and onwards

[Video 9](https://egghead.io/lessons/react-redux-avoiding-array-mutations-with-concat-slice-and-spread)
* Use deepFreeze to guard against mutating on places where you shouldn't. Objects frozen by deepFreeze can't be changed.
* Concat operator creates a new array, whereas a push operation works on the original array itself
* [ES6 Spread syntax](https://codeburst.io/javascript-es6-the-spread-syntax-f5c35525f754) allows arrays to expand into values.
* Like push, splice is a method that mutates the original array on which it is called. Better to return a new array that is a concatenation of two slices: the slice before the index to remove, and after the index to remove.

Since the list of activated & deactivated languages for DSpace 7 is represented in arrays, these concepts might come in handy to ensure that the state is changed properly without the unwanted mutations.

[Video 10](https://egghead.io/lessons/react-redux-avoiding-object-mutations-with-object-assign-and-spread)
* [ES6 Assign](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign) can be used to avoid object mutations. Instead of re-creating an object by manually setting every value from the previous object.
* Similar to the array spread operator, there's a new proposed spread operator that expands properties from objects.

[Video 11](https://egghead.io/lessons/react-redux-writing-a-todo-list-reducer-adding-a-todo)
* If you want to pass variables into the reducers, you can set properties on the action. The type property defines what the action is supposed to do, and then you can add any properties as needed.

# Day 59 Plan

Continue with [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux), video 13.
Continue with implementing the actions and the reducer for the language switch.
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