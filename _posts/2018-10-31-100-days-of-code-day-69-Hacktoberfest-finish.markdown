---
layout: post
title:  "100 Days of Code Day 69 - Hacktoberfest Finish"
date:   2018-10-31 23:10:00
categories: 100DaysOfCode
---

# Evening session

Even though I did day 68 earlier in the morning, I continued in the evening to anticipate missing friday and to finish my Hacktoberfest pull requests.

# Before leaving work

Art gave me a few pointers, including Intellij IDEA shortcuts:
* alt + arrow-up to expand the scope of your selection. Handy to make sure you get exactly the right set of braces
* cmd alt v to extract a variable 

He also recommended me to change the Language representation in the configuration from:

```
lang: {
    //Default language in case there are no active translations for the user's browser language
    default: 'en',
    //Languages that users can choose from in the language switch
    active: ['en','cs','de'],
    //Labels for the languages that users can choose from in the language switch
    activeLabels: ['English','Čeština','Deutsch'],
    //Languages for which DSpace has translations files, but that are deactivated
    inactive: ['nl'],
    //Labels for deactivated languages
    inactiveLabels: ['Nederlands']
  }
```

into:

```typescript
lang: [{
    code: 'en',
    label: 'English',
    active: true,
    default: true
  }, {
    code: 'de',
    label: 'Deutsch',
    active: true
  }, {
    code: 'cs',
    label: 'Čeština',
    active: true
  }, {
    code: 'nl',
    label: 'Nederlands',
    active: false
  }]
```

This primarily addresses the weakness that the previous configuration really relied on maintaining the exact same order in the language arrays and their corresponding labels, which would become a mess with a big volume of possible languages.

He also helped me to solve the elusive dependency injection problem I was dealing with for the last days. All the time, I was thinking that the following stacktrace didn't reveal what was missing, but it did:

```
FAILED TESTS:
  LangSwitchComponent
    ✖ should create
      Chrome 69.0.3497 (Mac OS X 10.12.6)
    Error: StaticInjectorError(DynamicTestModule)[LangSwitchComponent -> InjectionToken config]:
      StaticInjectorError(Platform: core)[LangSwitchComponent -> InjectionToken config]:
        NullInjectorError: No provider for InjectionToken config!
```

I thought there was something wrong with configuration somewhere, but it turns out that my component needs the variable "config", where all of the environment.default.js gets loaded. So once that was mocked with a few languages, this hurdle was passed.

# Rewriting component 

I rewrote the methods in the component to support this new structure. Links that helped me along the way, primarily to get a refresh on .map() and .find().

* [How do I filter an array with typescript in Angular 2](https://stackoverflow.com/questions/37003551/how-do-i-filter-an-array-with-typescript-in-angular-2)
* [Angular 2 typescript how to find element in array](https://stackoverflow.com/questions/37969984/angular-2-typescript-how-to-find-element-in-array)
* [From an array of objects extract value of property as array](https://stackoverflow.com/questions/19590865/from-an-array-of-objects-extract-value-of-a-property-as-array)

# Stuck on the unit tests

After the dependency injection problem was addressed, I was now confronted with not being able to load the translation files from the assets/resources directory.

# Hacktoberfest pull requests

I really wanted to have fully meaningful and big pull requests in there, but as the end of the day, and the end of October Hacktoberfest deadline loomed, I had to settle for two contributions that were a little less challenging in nature:

* [Added padding to comm coll logos](https://github.com/DSpace/dspace-angular/pull/324)
* [Reworded the language on the DSpace 7 homepage](https://github.com/DSpace/dspace-angular/pull/322)

# Day 70 Plan

Find out how to access the language file assets from the unit tests.

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