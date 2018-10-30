---
layout: post
title:  "100 Days of Code Day 67 - More Testing"
date:   2018-10-30 07:00:00
categories: 100DaysOfCode
---

# Intellij IDEA Locate file - Autoscroll from source

Something that's been annoying me more and more, when jumping to different files in the DSpace 7 project tree is the following:
* Use CMD+E to open up the recent files dialog and jump to one of the files I've been recently editing
* Try to access a file in the same directory or another related file there

The problem is that even though the source editor opens the file, the project tree view (CMD+1), just stays where it is, with the previous file highlighted.

[Locate current file in IntelliJ](https://stackoverflow.com/questions/1086041/locate-current-file-in-intellij) gave me the answer. Even though there is supposedly (not sure about Mac) a shortcut that shows you where the current file is in the hierarchy, even better is the "Autoscroll from Source" setting in the menu. Open another file? BAM, tree shows you immediately where you are. 

Maybe if you often jump to files that are outside of your project tree (external dependencies, ...) it might not be that handy, but for me it's awesome right now.

# Still stuck on the dependency injection problem

My npm test still produces:

```
FAILED TESTS:
  LangSwitchComponent
    ✖ should create
      Chrome 69.0.3497 (Mac OS X 10.12.6)
    Error: StaticInjectorError(DynamicTestModule)[LangSwitchComponent -> InjectionToken config]:
      StaticInjectorError(Platform: core)[LangSwitchComponent -> InjectionToken config]:
        NullInjectorError: No provider for InjectionToken config!
```

One problem is that I haven't found a way to determine which dependency injection it's exactly failing on.
My guess would be the httpClient, [referred to in \[deps\]](https://github.com/DSpace/dspace-angular/pull/308/commits/296be81b009b42911e9e9b9e964b202b90f6d5d7#diff-ce5c46ec17c51a4f6a4fca841e9a2497R36), but right now I haven't found an example that shows me where this httpclient is created.

It also made me realize that we are currently not using a translation loader in the DSpace 7 app component, but that the language loading logic is just straight into the app component constructor. [Created a new issue](https://github.com/DSpace/dspace-angular/issues/318) to follow up ont his.

# Day 68 Plan

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