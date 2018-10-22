---
layout: post
title:  "100 Days of Code Day 59 - Egghead Redux course continued"
date:   2018-10-22 07:00:00
categories: 100DaysOfCode
---

# Continuing Egghead Redux tutorial video 13 and onwards

[Redux: Reducer Composition with Arrays](https://egghead.io/lessons/react-redux-reducer-composition-with-arrays)
* Reducers can call other reducers. The example started with a single reducer both taking care of an action on the array of todos, as well as on an individual todo and ends with a reducer that takes care of the entire list, delegating actions on single todos to a separate reducer.

[Redux: Reducer Composition with Objects](https://egghead.io/lessons/react-redux-reducer-composition-with-objects)
* Instead of representing the state store as an array with objects from the same type, you can also represent it as an object, composed of different objects.
* Because the the different reducers only action on specific actions, act as pure functions and return the current state as default, you can safely have the same state and action pass through different reducers. These reducers will only act if they need to, and do it safely.

[Redux: Reducer Composition with combineReducers()](https://egghead.io/lessons/react-redux-reducer-composition-with-combinereducers)
* You don't have to write a function that combines reducers for different objects in the state yourself, Redux can do this for you.
* As a convention, the name of the reducer is equal to the name of the object part of the state tree, managed by that reducer. Even though not explicitly mentioned, I think it also means that you need a single reducer for every type of object in the state tree. Even though that reducer can delegate responsibilities to other reducers.

[Redux: Implementing combineReducers() from Scratch](https://egghead.io/lessons/react-redux-implementing-combinereducers-from-scratch)
* [Object.keys(anobject)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys) can give you all of the keys for a particular object.
* It's still ok to mutate and pass along objects, like nextState in this example, as long as they not live outside of the reducer.
* Did not fully understand this because of the nested fat arrow functions.

# Day 60 Plan

Continue with [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux), video 17.
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