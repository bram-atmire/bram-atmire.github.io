---
layout: post
title:  "100 Days of Code Day 83 - Angular Testing"
date:   2018-11-16 07:00:00
categories: 100DaysOfCode
---

# Lotte to the rescue

After grinding my teeth on this problem for a couple of days now, I got some assistance yesterday from my colleague and top DSpace 7 Angular contributor, [Lotte](https://github.com/LotteHofstede). 

First thing she almost immediately spotted was that I had an important typo where I used "usevalue" instead of the correct camel case "useValue" at the point where my mock language config is provided to the test bed.

A second problem was also related to this mock config. I was providing this as straight JSON and not as the typescript LangConfig that was created earlier. LangConfig does something neat, but it only does it when an actual constructor is invoked: it sets the value for "default" on a language to false, if no value is being provided with: 

```typescript
default? = false;
``` 

The temporary solution right now is that I have filled out that default field for each of the languages in my mock config, but this will need to be revisited as I don't want to make that field mandatory.

# From JSON config to array of objects config

At the end of the hour, the config loading is still giving me following problem:

```
ERROR in [at-loader] ./src/app/shared/lang-switch/lang-switch.component.spec.ts:153:78 
    TS2339: Property 'default' does not exist on type '{ code: string; label: string; active: boolean; default: boolean; } | { code: string; label: stri...'.
  Property 'default' does not exist on type '{ code: string; label: string; active: boolean; }'.

ERROR in [at-loader] ./src/app/shared/lang-switch/lang-switch.component.spec.ts:154:67 
    TS2339: Property 'default' does not exist on type '{ code: string; label: string; active: boolean; default: boolean; } | { code: string; label: stri...'.
  Property 'default' does not exist on type '{ code: string; label: string; active: boolean; }'.
  
```

# Day 84 Plan

Continue trying to get rest of the tests to work.

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
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whenever something is committed to master.
* Add documentation to the methods of the item controller
* Change the back button on the item page with a real link back to the repository analysis, instead of the current history -1 hack.

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