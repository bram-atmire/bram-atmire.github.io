---
layout: post
title:  "100 Days of Code Day 66 - More Testing"
date:   2018-10-28 07:23:00
categories: 100DaysOfCode
---

# toBeTruthy()

Yesterday, I was wondering what truthy meant.

[Truthy and Falsy: When All is Not Equal in JavaScript](https://www.sitepoint.com/javascript-truthy-falsy/) made it very clear. tl;dr
* Truthy and Falsy evaluations are based the inherent boolean values that each value has. 
* In very short, if it's not 0, null or false, a value will inherently evaluate to true.

[toBe(true) vs toBeTruthy() vs toBeTrue()](https://stackoverflow.com/questions/32615713/tobetrue-vs-tobetruthy-vs-tobetrue) on Stackoverflow puts this subtle difference into the context of the Jasmine matchers.

# Should the component that we are testing be declared in the testbed or not?

In tutorials like [this one](https://codecraft.tv/courses/angular/unit-testing/angular-test-bed/#_configuring), I'm always seeing that the component that is being tested, is included in the declarations of the test bed. However, in the DSpace 7 [Browse By](https://github.com/DSpace/dspace-angular/blob/master/src/app/shared/browse-by/browse-by.component.spec.ts#L16) component that doesn't seem to be the case and I wonder why.

[Setup with module imports](https://angular.io/guide/testing#setup-with-module-imports) notes that either the component is already declared in one of your imports, or you declare it yourself in the spec you are writing. But I would tend to think that your testbed will always somehow need the code you wrote in the actual component file, so I would think you would always want to import it rather than declare it.

# Testbed .compileComponents() and splitting beforeEach into sync & async methods.

In an Angular CLI project, you don't need to call .compileComponents() for a testbed. However, as we're not (yet) on the Angular CLI structure in DSpace 7, you still have to do it to make sure your external .html and .css files are present.

This also relates to the reason why beforeEach methods are split up in an async and a sync one: 
* You need to be sure that compileComponents has completed
* By adding a second beforeEach synchronous method, you force the test runner to wait until the first async one is completed, before it continues with the second one.

[Source - Angular.io testing guide](https://angular.io/guide/testing#calling-compilecomponents)

# Bringing over the ngx-translate example test code into DSpace 7

Yesterday I already mentioned that [How to unit test a component with TranslateService and the translate pipe?](https://github.com/ngx-translate/core/issues/636) featured a whole discussion of what and how to mock for TranslateService. In one of the last replies in the thread, the developer behind ngx-translate responded by adding [a spec to his example app](https://github.com/ngx-translate/example/blob/master/src/app/app.component.spec.ts).

I made progress, and added my [current test file to the pull request](https://github.com/DSpace/dspace-angular/pull/308/commits/296be81b009b42911e9e9b9e964b202b90f6d5d7), however, it is still failing against dependency injections at the moment.

# Day 66 Plan

Solve the dependency injection problems for the tests

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