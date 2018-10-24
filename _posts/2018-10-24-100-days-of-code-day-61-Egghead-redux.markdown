---
layout: post
title:  "100 Days of Code Day 61 - Egghead Redux course continued"
date:   2018-10-24 07:00:00
categories: 100DaysOfCode
---

# Continuing Egghead Redux tutorial video 22 and onwards

[Redux: Extracting Container Components (FilterLink)](https://egghead.io/lessons/react-redux-extracting-container-components-filterlink)
* Previously, the whole application rendered again at every single state change in the store. This is not efficient.
* Instead, it makes more sense to subscribe specific components to the state changes of the store.
* The newly extracted container components get the state from the store themselves, and compare/do operations with the element props.

[Redux: Extracting Container Components (VisibleTodoList, AddTodo)](https://egghead.io/lessons/react-redux-extracting-container-components-visibletodolist-addtodo)
* The AddTodo component now again does both presentation as well as logic, because it's not a clear cut presentation or container component.
* Whereas the list of active todos, and the footer need to be aware of the current state, the AddTodo component doesn't need to be aware of state. It pushes a new todo regardless. However, it's pretty weird right now that it holds the id counter and the increment itself, rather than getting it from the store. 
* The application itself no longer needs an overall re-render, and all props & actions have been removed from the top level appcomponent.
* Separating the container and the presentational components shouldn't take it as a dogma. Only when it reduces the complexity of the code base.
  *  first try to extract the presentational components. Only if too much boilerplate applies passing props to them, create containers around them loading the data and specifying the behaviour.
  
[Redux: Passing the Store Down Explicitly via Props](https://egghead.io/lessons/react-redux-passing-the-store-down-explicitly-via-props)
* In a large, real world application, you can't count on a single top level store variable to be available.
  * For example, in a universal app that renders on the server, you'll need a different store for each request, since the data can be totally different for each request
* Instead, the store can be passed through as part of the props
* This shows the problem that the code gets less clean, as the store is explicitly added to the signature of every method that needs to access the store or dispatch actions to it, meaning more or less every method in the example todo app.

[Redux: Passing the Store Down Implicitly via Context](https://egghead.io/lessons/react-redux-passing-the-store-down-implicitly-via-context)
* A provider component is introduced and the whole app runs inside of it.
* The provider needs to declare what context type it can provide to its children
* The children need to declare which context types they will be receiving
* The result is that the store doesn't have to be passed down within props anymore
* Context is a specific advanced feature of React, not sure if there is something comparable in Angular/ngrx.

[Redux: Passing the Store Down with <Provider> from React Redux](https://egghead.io/lessons/react-redux-passing-the-store-down-with-provider-from-react-redux)
* The react-redux library is not the same as the redux library. It provides specific bindings to redux for react.
* The Provider component you can get from there essentially does the same as the one written by hand in the previous video

[Redux: Generating Containers with connect() from React Redux (VisibleTodoList)](https://egghead.io/lessons/react-redux-generating-containers-with-connect-from-react-redux-visibletodolist)
* mapStateToProps and mapDispatchToProps are the only things that are needed to generate the full container component, using the connect method.
* Struggling with the call to getVisibleTodos there. 
* Connect is a curried function and need to be called twice. TODO: read up on curried functions to properly understand this.

# Day 62 Plan

Continue with [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux), video 28, 29 and 30 .

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