---
layout: post
title:  "100 Days of Code Day 80 - Analyzer Testing"
date:   2018-11-13 07:00:00
categories: 100DaysOfCode
---

# Break points - identify where it's going wrong

One of my challenges right now, is that I don't understand the flow of control during execution of the Karma test runs. As a consequence, I don't see where the current error is exactly thrown. Already a while ago, I installed the Karma plugin for Intellij IDEA. It seems to have breakpoint support but I don't know how they work yet.

* [Intellij IDEA: Running Unit Tests on Karma](https://www.jetbrains.com/help/idea/running-unit-tests-on-karma.html)

Learned that these break points and the process of stepping in, stepping over etc, should basically be similar to the java debugger.
However, even when put very early in the execution of the test, the test already fails before we get there, with the constructor of my LangSwitchComponent.

```
TypeError: Cannot read property 'lang' of undefined
    at new LangSwitchComponent (spec-bundle.js:176278:6483)
```

# OnInit ?

My LangSwitchComponent currently implements the OnInit interface and I can't recall whether this was a conscious need/decision or just a result from copying template code from somewhere.

* [Difference between Constructor and ngOnInit](https://stackoverflow.com/questions/35763730/difference-between-constructor-and-ngoninit)

From this answer:
_Mostly we use ngOnInit for all the initialization/declaration and avoid stuff to work in the constructor. The constructor should only be used to initialize class members but shouldn't do actual "work"._
 
_So you should use constructor() to setup Dependency Injection and not much else. ngOnInit() is better place to "start" - it's where/when components' bindings are resolved._

When reading this, I noticed and realised that I'm initialising two class members, activeLangs and moreThanOneLanguage, not in the constructor, not in ngOnInit, but just at their declarations. Even thought the code actually worked, I wonder if I should be moving this to the constructor or the ngOnInit method.

Since the initialization of those members depends on the config being present and dependency injection done, it likely makes sense to move them to ngOnInit. Because it's exactly the lang property that is relied upon, which is what the test run is complaining about.

This definitely made a difference, because some of my tests are now passing!

# When to use async for tests?

Noticed that had two of my tests set to async but don't recally exactly why that's necessary or preferable.

# Day 81 Plan

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