---
layout: post
title:  "100 Days of Code Day 60 - Egghead Redux course continued"
date:   2018-10-23 07:00:00
categories: 100DaysOfCode
---

# Continuing Egghead Redux tutorial video 17 and onwards

[Redux: React Todo List Example (Adding a Todo)](https://egghead.io/lessons/react-redux-react-todo-list-example-adding-a-todo)
* Since this was a React example, not 100% sure how much of this is applicable to ngrx.
* The render function is subscribed to any changes on the store. Because the todos prop is assigned in the render function, it's always up to date with the latest changes
* The UI component is not aware HOW todo's are added, but by dispatching the action it expresses its desire to perform the ADD_TODO action, for which the expectations and effect are unambiguously defined.

[Redux: React Todo List Example (Toggling a Todo)](https://egghead.io/lessons/react-redux-react-todo-list-example-toggling-a-todo)

[Redux: React Todo List Example (Filtering Todos)](https://egghead.io/lessons/react-redux-react-todo-list-example-filtering-todos)
* 4:00 Instead of loading all props part of the state as explicit props, you can spread over the entire state to have all props available.

[Redux: Extracting Presentational Components (Todo, TodoList)](https://egghead.io/lessons/react-redux-extracting-presentational-components-todo-todolist)
* An optional pattern is introduced, where components are separated into presentational components and container components.
* A presentational component is only concerned with how something looks, it doesn't know what data it renders and also not what action gets dispatched.
* Deciding which objects to render and which action to dispatch is what happens in the container component, that in turn, delegates presentation to the presentation components.

[Redux: Extracting Presentational Components (AddTodo, Footer, FilterLink)](https://egghead.io/lessons/react-redux-extracting-presentational-components-addtodo-footer-filterlink)
* Even though separating redux in the container components, vs the presentation components is not required, it makes the code more flexible to move to another framework in the future.
* The challenge that this creates is that a lot of props have to be defined and passed along the way but that is addressed in the next video.

# Day 61 Plan

Continue with [Egghead getting started with redux](https://egghead.io/courses/getting-started-with-redux), video 22 .
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