---
layout: post
title:  "100 Days of Code Day 64 - DSpace 7 Angular Testing"
date:   2018-10-27 16:50:00
categories: 100DaysOfCode
---

# Yesterday's incomplete day

I got up later than usual and also had a morning meeting with a client in Brussels. As a result, I only got half an hour in and [a messy blog post](http://bram-atmire.github.io/100daysofcode/2018/10/26/100-days-of-code-day-63-Jasmine-Testing.html).

Picking up, doing a bit more than an hour today to compensate, and trying to make sense of everything I'm seeing.

# DSpace 7 Angular testing lingo

Lots of specific terms and tools here, let's put it together

## Jasmine

[Jasmine](https://jasmine.github.io/) determines the system and the syntax for writing behavioural tests for the code of your angular components. These tests in themselves are written in javascript as well. You can find detailed explanations of Jasmine concepts in the tutorial [Your first test suite](https://jasmine.github.io/tutorials/your_first_suite). Mainly for myself, here's a quick and dirty tl;dr of that page:

* A suite starts with a "describe" function call. I it is a collection of specs, testing the same "thing". 
* A spec is embodied as an "it" function call. A spec can consist of one or more expectations. If one expectation fails, the spec fails. A spec with all true expectations is a passing spec.
* by putting x in front of a spec or a suite, meaning that instead of the "it" or "describe" function calls, you're calling xit or xdescribe, they are skipped from the test run. Skipped is also labelled "Pending".
* by spying on a particular function call on a particular object, you can write expectations against that function being called, how many times it should be called and with which arguments it should be called.
* If you need something more vague than exact equality, jasmine.any can provide class names as expected values. For example if you want to test if a method is called with a Number object, but you don't want to test against a specific instance of a Number object. jasmine.anything is even more vague: it will pass as long as the value is not null or undefined.

# Had to stop early

Assisted in a friend's move earlier in the day, had to lie down because of back pain and watched [Paywall The Movie](https://paywallthemovie.com/), about the business of scholarship.

# Copy paste of Friday's content, still to be processed/reviewed

Still have to process the stuff below more

# DSpace 7 Testing

Tests are mandatory for contributions to DSpace 7 and my language switch pull request.
Looked at a few spec.ts files in DSpace 7 to get a feel for it and found the [Jasmine Tutorial](https://jasmine.github.io/tutorials/your_first_suite) to get going with this.

## Karma vs Jasmine

Both Karma and Jasmine are being used, and it seems like Karma is a test runner, while Jasmine is the actual semantics for writing the unit tests.

https://karma-runner.github.io/3.0/intro/installation.html

## Executing tests

Every time a pull request comes in to DSpace 7, the tests are automatically executed on Github.

To execute the tests you can execute npm test in the source root of the project.

Note that Angular CLI applications allow you to spin up the tests with "ng test" from the CLI. Because the DSpace 7 Angular UI is not (yet) compatible with Angular CLI, this currently does not work.

What is Karma?

## Measuring Coverage

The DSpace 7 Angular build is integrated with Coveralls, that is able to measure whether test coverage of the code improves or decreases with a certain pull request. Inside the Github interface, a percentage summary is presented, showing how much coverage improved or decreased with the pull request. [A detail page](https://coveralls.io/builds/19631826) is available on coveralls that gives you more details.

In my example, coverage decreased because I added code without tests. However, I'm confused by the detail page on coveralls, as it seems to show changes in coverage for so many files and places that I didn't touch. 

First of all, I don't know what the build compares to. The latest master? There might be changes on the latest master that I should rebase my own branch to.


# Day 64 Plan

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