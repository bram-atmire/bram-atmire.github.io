---
layout: post
title:  "100 Days of Code Day 81 - Angular Testing"
date:   2018-11-14 07:00:00
categories: 100DaysOfCode
---

# Initialising the Test Bed multiple times - One passes, one breaks

I currently have two blocks of tests: one block where there is only one active language configured. In this block the test and the expected behaviour is that the language switch doesn't render at all.

In the second block, I do have two languages active, for tests against the case where the switch is present.

For each of these blocks, I'm initialising the entire test bed, with only a very small difference: the configuration of the active language.

The first block already passes the tests, but the second block is still giving me the error I was confronted with before:

```
TypeError: Cannot read property 'lang' of undefined
    at new LangSwitchComponent (spec-bundle.js:176278:6483)
```

Even though moving the initialisation of the class members into the ngOnInit method fixed it for my first block of tests.

* [Codecraft.tv Angular Test Bed](https://codecraft.tv/courses/angular/unit-testing/angular-test-bed/)

# Testbed CompileComponents() and Webpack

DSpace 7 uses webpack. [Here](https://github.com/angular/angular/issues/13963) I read that it's not necessary to call compilecomponents on the test bed, as css and templates are already in-lined.

But that also makes me wonder if it's going to work if I configure the test bed twice in my tests, since the compilecomponents call may not have effect neither.

# When to use async for tests

Yesterday I was wondering when (not) to use async for tests.

[Angular 2 Testing - Async function call - when to use](https://stackoverflow.com/questions/40126729/angular-2-testing-async-function-call-when-to-use) talks about when (not) to use it in the testbed call.

The short summary of this seems to be that if you have any asynchronous activities going on, having the async in front of it will force all other tests to wait until this block is done. 

Reading back my previous blogs, I already dipped into this in [Day 66](http://bram-atmire.github.io/100daysofcode/2018/10/29/100-days-of-code-day-66-Testing.html)

# Comparing sections of the same file

IntelliJ IDEA has a great compare-view, where you can compare two DIFFERENT files with eachother.
To compare if I have any differences in my test bed initialization, I wanted to do a line by line comparison of the same file.

[Quick way to compare methods in IntelliJ](https://stackoverflow.com/questions/20576925/quick-way-to-compare-methods-in-intellij)

Tl;dr the trick is to use "compare with clipboard" after you've copied the contents of the file into clipboard.

# No differences found - switching block orders

To test if the first test bed initialization really affects the second one, i'm switching the order of the blocks to see if that makes a difference.

Switching the order didn't matter, so the good news is that the two describe blocks are correctly working in complete isolation

# Cannot read property of undefined

At the end of the hour, it still seems that my component is not full instantiated/ready before the test, even with the two beforeach sections in place.

```
TypeError: Cannot read property 'find' of undefined
	    at LangSwitchComponent.currentLangLabel (spec-bundle.js:176278:6966)
```

# Day 82 Plan

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