---
layout: post
title:  "100 Days of Code Day 65 - Writing my first DSpace 7 Angular tests"
date:   2018-10-28 17:38:00
categories: 100DaysOfCode
---

# Writing tests for the language switch

# How can I only execute tests from a particular file, and not run the tests of the entire project?

To get my own tests to run, I ideally want those tests to run in isolation first, before having to pass through the tests of the entire project all the time.

[How to execute only one test spec with angular-cli](https://stackoverflow.com/questions/40683673/how-to-execute-only-one-test-spec-with-angular-cli) learned me that the test.ts file can be modified to run only the tests of a specific component. However, this doesn't seem to apply for the DSpace 7 Angular codebase.

There I found out that in the karma.conf.js, where the Karma test runner is configured, there's a reference to spec-bundle.js.
It looks like [that's indeed the place](https://github.com/DSpace/dspace-angular/blob/master/spec-bundle.js#L41) to limit which tests are included for the run.

# DebugElement vs HTMLElement

I understand from [Angular.io Testing guidelines](https://angular.io/guide/testing#component-dom-testing) that your tests might not always be running on a browser platform. They might be running on something that doesn't support queryselector, straight on the nativelement provided by the fixture. However, I'm not sure if the whole wrapping and workaround with a DebugElements is required or even desired for DSpace 7 Angular testing.

# Typescript colon (:) vs javascript equals sign (=) for declarations

Thanks to [TypeScript : Colon vs Equal To ( Angular Tutorial )](https://stackoverflow.com/questions/43368152/typescript-colon-vs-equal-to-angular-tutorial) and [Typescript documentation on Basic Types](https://www.typescriptlang.org/docs/handbook/basic-types.html), I was reminded of the following when I got confused about : vs =.

Basically javascript doesn't have types, so you could do assignments like:

```
const a = b;
```

Typescript adds \[: type\] as an optional type declaration, so the pattern for declaring variables becomes:

```
name[: type][ = value];
```

# Const is not about immutability

tl;dr of [ES2015 const is not about immutability](https://mathiasbynens.be/notes/es6-const)
* const only guarantees immutability on the initial binding. Properties of the object that is bound can still change
* Author recommends to use const by default, and only change it to let if you explicitly want to allow re-binding.

# Testbed schemas NO_ERRORS_SCHEMA

To ignore child components, unrecognized elements and attributes, you can set up the testbed with the NO_ERRORS_SCHEMA. 
Source: [Angular.io Testing documentation](https://angular.io/guide/testing#nested-component-tests)

# Intellij IDEA complaining about Observable.of

In many classes that I have not been modifying, I get complaints about calls like:

```
spyOn(store, 'select').and.returnValue(Observable.of({ navCollapsed: true }));
```

The complaint is [Property 'of' does not exist on type 'typeof Observable'](https://stackoverflow.com/questions/38067580/property-of-does-not-exist-on-type-typeof-observable). I couldn't determine yet whether it's something wrong with my particular configuration or if something might need to change on those files.

# Mocking / Creating stubs from variables read from config?

The language switch components is supposed to read the list of activated languages and their labels from the config.
Not sure if it is OK in a test to rely on this behaviour, or whether mock values from config also have to be provided.

# toBeTruthy()

I've come across this a couple of times and have no idea what it means.

# Dealing with the translation service dependency injection

[How to unit test a component with TranslateService and the translate pipe?](https://github.com/ngx-translate/core/issues/636) features a whole discussion of what and how to mock for TranslateService, where the developer behind ngx-translate responded by adding [a spec to his example app](https://github.com/ngx-translate/example/blob/master/src/app/app.component.spec.ts).

This should provide enough examples of how to deal with testing if some parts effectively get translated correctly.

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