---
layout: post
title:  "100 Days of Code Day 84 - Angular Testing"
date:   2018-11-18 08:00:00
categories: 100DaysOfCode
---

# Default language as a separate configuration variable

Before today's work, the language configuration was represented by an array of LangConfig objects, that looked like this:

```typescript
export interface LangConfig extends Config {
      code: string;
      label: string;
      active: boolean;
      default: boolean;
}
```

The goal was to make the variable default optional, and to use false as the standard value if it would not be filled out.
The definition of default language is the following:

_DSpace tries to render the repository user interface in the active browser language of the user. If the user's browser language is not present in the DSpace configuration of active languages, it will render the repository in the default language_

With this definition, only one language can be flagged as the default one. But by leaving it as a variable on the languages themselves, it is not prevented that the repository administrator would set this to true on several languages.

Since the loading of this config is giving me issues anyway, I'm going to experiment with extracting defaultlang as a separate variable, and keep it on the level of global-config.interface.ts 

# Cleaning up the final contribution

In order to measure coverage and get my code cleanly into the DSpace Angular mainline, I want to:
* rebase my code against the last master
* Squash all my commits into a single commit

[Merge all changes from another branch as a single commit](https://stackoverflow.com/questions/3697178/merge-all-changes-from-another-branch-as-a-single-commit) helped me to do this.

1. Made sure my local master branch was up to date with origin master
2. Made a new local branch
3. Merged my changes with the --squash flag
4. Proposed as a new pull request.

# Done?

After issuing the new pull request, I noticed there are now new JS lint issues that still need to be addressed.

# Day 85 Plan

Resolve JS Style lint issues

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