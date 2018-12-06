---
layout: post
title:  "100 Days of Code Day 96 - Po concerns"
date:   2018-12-06 07:10:00
categories: 100DaysOfCode
---

# Using the English string instead of the message key

In the [Github issue covering the transition to the .po format](https://github.com/DSpace/dspace-angular/issues/331), 
helix84 made the point that the community using .po normally doesn't any abstract message keys/ids. Instead, the English 
message gets into the source code and serves as the message key. If the contents of two keys are identical, but the use 
is different, a "context" field gets added. It's actually the combo of context + message that has to be unique.

When talking this through with my colleagues over lunch, this idea was not totally shot down, but a few concerns were
 voiced:
 
 * Escaping of special characters: would we need to escape more characters than only the double quotes?
 * Dealing with length: won't it be too messy in the code if we get really large blocks of text in there?
 * How does the context field/string work exactly
 
So in order to alleviate these concerns, I thought I'd build prototypes/tests for each of these.

# Escaping of special characters

Did not get to this yet, see lower
 
# Merging with Angular 6 latest master code

Before I started, I merged master back into my feature branch and now I can't run 'yarn run watch' anymore:

```
/Users/bram/Development/IdeaProjects/dspace-angular-2018/src/dspace-angular/node_modules/webpack-cli/bin/cli.js:244
				throw err;
				^

Error: Cannot find module 'uglifyjs-webpack-plugin'
    at Function.Module._resolveFilename (module.js:548:15)
    at Function.Module._load (module.js:475:25)
    at Module.require (module.js:597:17)
```

Because this dependency doesn't appear in the package.json file on master, I'm a little reluctant to add it just in 
order to resolve this, so I'll poke my colleagues for some advice here.

# Day 97 Plan

Continue with the experiments of replacing message keys with actual English messages, to serve as the keys going 
forward.
Investigate why some message keys were missing from the automated extraction.

# Future days - DSpace 7 Angular

* Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.
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