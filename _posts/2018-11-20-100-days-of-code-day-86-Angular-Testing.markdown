---
layout: post
title:  "100 Days of Code Day 86 - TSLint issues"
date:   2018-11-20 21:30:00
categories: 100DaysOfCode
---

# IntelliJ Insert Pair brackets / auto-parenthesis generation

Whenever I type a [ o (, Intellij IDEA would be clever and immediately also type the closing one. Even though it is sometimes handy, it more than often is not for me, to the point that it was driving my crazy.

As with so many things in this editor, it was easily disabled. After of course googling for it and learning what the name of the option was.

[How do I turn off auto-parenthesis generation in Intellij IDEA?](https://stackoverflow.com/questions/9103779/how-do-i-turn-off-auto-parenthesis-generation-in-intellij-idea?rq=1)

# Trying out -t stylish instead of -t verbose

I received a [recommendation on Twitter](https://twitter.com/LuytenBram/status/1064399062756151296) for the -t stylish TSLint formatter. 

I tried it out and it's indeed very neat to see all problems organised per source file. However, I did not yet find a way to also have it display the TSLint rule that is being offended.

![Offending rule not clearly visible](../../../../assets/img/2018-11-20-Now-you-dont-see-the-offending-rule.png)

*Edit* The guy who was kind enough to react in the first place immediately responded and made clear that -t stylish also includes the offending rule, but due to a styling issue that I currently don't understand, the text was hidden in my own terminal

![Offending rule visible when highlighted in zsh](../../../../assets/img/2018-11-20-Now-you-see-the-offending-rule.png)

# Getting TSLint configured in IntelliJ IDEA

In order to fix a whole bunch of these problems after writing the offending code. I want to see how I can get IDEA pick up the DSpace 7 Angular TSLint file, and maybe give me pointers in real time. I already have the [SonarLint plugin](https://plugins.jetbrains.com/plugin/7973-sonarlint) configured, so maybe the DSpace TSLint file it can be somehow part of it.

The [TSLint page on jetbrains.com](https://www.jetbrains.com/help/idea/tslint.html) seems to indicate that TSLint is natively supported. 

![TSLint activated in Intellij IDEA](../../../../assets/img/2018-11-20-TSLint-IntelliJ-IDEA.png)

# Shadowed name

```
ERROR: (no-shadowed-variable) src/app/shared/lang-switch/lang-switch.component.spec.ts[141, 55]: Shadowed name: 'LangConfig'
```

[No Shadowed Variable](https://palantir.github.io/tslint/rules/no-shadowed-variable/)

Read the explanation two times and still don't understand it.

[Making Sense of 'No Shadowed Variable' tslint Warning](https://stackoverflow.com/questions/44853057/making-sense-of-no-shadowed-variable-tslint-warning)

In that stackoverflow post, they refer to the [ESLint explanation](https://eslint.org/docs/rules/no-shadow).
So the basic tl;dr on this is: if you have defined a variable in a higher (or global) scope, don't redefine it in a local scope because then it can be confusing what it will actually contain + you can't access the global variable anymore. 

# Array type

```
ERROR: (array-type) src/app/shared/lang-switch/lang-switch.component.ts[19, 16]: Array type using 'Array<T>' is forbidden for simple types. Use 'T[]' instead.
```

Not sure why a strongly typed array of objects is a bad thing.

[What's the rationale for the array-type rule?](https://github.com/palantir/tslint/issues/2609)

Apparently it's a style thing, e.g. assistance to ensure that you adhere to the same style across the project.

# Day 87 Plan

Evaluate the [latest build results](https://github.com/DSpace/dspace-angular/pull/329) of the fixes I pushed upstream.

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