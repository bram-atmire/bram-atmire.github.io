---
layout: post
title:  "100 Days of Code Day 87 - Resolving comments on 2 open pull requests"
date:   2018-11-21 07:00:00
categories: 100DaysOfCode
---

# Checks passing on the Language Switch pull request!

Very happy to start this morning, seeing that the [checks have passed on the Language Switch pull request](https://github.com/DSpace/dspace-angular/pull/329). Hope that it gets merged before the weekend!

# Issue 321 Home news rewording

I [broke a protractor test](https://github.com/DSpace/dspace-angular/pull/322) with one of my pull requests from the last day of October (Hacktoberfest). 

My colleague Art already suggested a fix from another commit and I tried to cherry pick it.

To ensure I had the entities branch locally that Art referred to, I did

```
» git pull origin        
From https://github.com/DSpace/dspace-angular
 * [new branch]      configurable_entities -> origin/configurable_entities
```

However, trying to cherry pick the branch was not immediately successful

```
» git cherry-pick e39879b                    
fatal: bad revision 'e39879b'
```

[How to cherry pick from a remote branch](https://stackoverflow.com/questions/13788945/how-to-cherry-pick-from-a-remote-branch)

So I figure I don't have the pull request branches locally. [Testing with pull requests](https://wiki.duraspace.org/display/DSPACE/Development+with+Git#DevelopmentwithGit-TestingPullRequests) in the DSpace documentation was a helpful reminder there.

```
git config --add remote.origin.fetch +refs/pull/*/head:refs/remotes/origin/pr/*
```

As the DSpace github repo is called "origin" on my local machine.
So once I had the pull requests all locally, the cherry pick went fine.

# issue 323 comcol page logo bottom padding

Art recommended to use classes for margin and padding instead of hardcoding a number.
[Bootstrap 4 Spacing utilities](https://getbootstrap.com/docs/4.1/utilities/spacing/)

# Day 88 Plan

If these open pull requests are merged, proceed with the challenge to allow an admin to turn off particular languages.

# Future days - DSpace 7 Angular

* UI for enabling/disabling particular languages
    * Continue with implementing the actions and the reducer for the language switch.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
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