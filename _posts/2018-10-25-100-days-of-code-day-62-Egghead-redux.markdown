---
layout: post
title:  "100 Days of Code Day 62 - Egghead Redux course continued"
date:   2018-10-25 07:00:00
categories: 100DaysOfCode
---

# Continuing Egghead Redux tutorial video 28, 29, 30

[Redux: Generating Containers with connect() from React Redux (AddTodo)](https://egghead.io/lessons/react-redux-generating-containers-with-connect-from-react-redux-addtodo)
* If your component doesn't need any props from the store, you can pass a null reference in the connect method and only map the dispatchers
* Having the dispatch method mapped is so common that is implemented as the default behaviour for connect, so that doesn't have to be supplied explicitly either
* This is how they get to the connect() method without any arguments and its default behaviour
  * No subscription to the store
  * having access to the dispatch method
  
[Redux: Generating Containers with connect() from React Redux (FooterLink)](https://egghead.io/lessons/react-redux-generating-containers-with-connect-from-react-redux-footerlink)
* mapStateToProps and mapDispatchToProps often need the properties of the component itself, compare those to values from the state, in order to get the final properties. That's why ownProps are passed through into the mapStateToProps and mapDispatchToProps methods. The footer link needed this, but AddTodo didn't need this.

[Redux: Extracting Action Creators](https://egghead.io/lessons/react-redux-extracting-action-creators)
* An action creator method does nothing more than taking the actual inputs needed for the action, and then return the action object, with the right corresponding type. It's not mandatory but handy for testing to have all your action creators in the same place.
* I'm still not sure/confused at the end why nextTodoId is not present in the store. Maybe because only a single component needs it?

# DSpace 7 Testing

Tests are mandatory for contributions to DSpace 7 and my language switch pull request.
Looked at a few spec.ts files in DSpace 7 to get a feel for it and found the [Jasmine Tutorial](https://jasmine.github.io/tutorials/your_first_suite) to get going with this.

# Day 63 Plan

Write tests for my [language switch pull request](https://github.com/DSpace/dspace-angular/pull/308).

# Future days - DSpace 7 Angular

* Investigate writing of tests and write tests for the original language switch.
* Continue with implementing the actions and the reducer for the language switch.
* Continue implementation of the action to deactivate a language.
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

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.