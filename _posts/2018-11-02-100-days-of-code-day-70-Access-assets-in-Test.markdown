---
layout: post
title:  "100 Days of Code Day 70 - Access assets in Test"
date:   2018-11-02 07:20:00
categories: 100DaysOfCode
---

# Accessing assets in Test

The tests are currently failing because the code can't find the /assets/i18n files that it needs.

## Tell Karma test runner where to find the assets folder

Instead of addressing it for a single test, you can tell the Karma test runner where the assets folder is.
Thanks to [How do I serve assets when I run ng test using latest angular-cli (beta 15 w/webpack)?
](https://stackoverflow.com/questions/40088462/how-do-i-serve-assets-when-i-run-ng-test-using-latest-angular-cli-beta-15-w-web). Because the language files can become large, I think it will make sense that DSpace 7's karma test runner configuration would also serve the assets.

This method of using a pattern and proxy configuration is not what the [NGX-Translate example app](https://github.com/ngx-translate/example/blob/master/angular.json#L72) does. There, it just seems to include a section that says "assets" into the test configuration of Angular.json. So not even in the Karma configuration itself.

The [Karma Documentation](http://karma-runner.github.io/3.0/config/files.html) goes in detail about what you can and can't include in the files array configuration.

DSpace 7 relies on WebPack, that also has its own [specific way of dealing with assets](https://webpack.js.org/guides/asset-management/).
So since the languages are already working and being loaded when you do a normal build, something must be already in there to put the language files in place.

Right now, it's in [webpack.common.js](https://github.com/DSpace/dspace-angular/blob/master/webpack/webpack.common.js#L98) where the effect takes place that language files under /resources/i18n in the codebase show up under /assets/i18n. But why is or isn't that webpack.common.js file used or executed for tests?

[Webpack.config.js](https://github.com/DSpace/dspace-angular/blob/master/webpack.config.js) doesn't mention anything about the test builds at all, so I'm assuming it's unrelated.

Rather, [karma.conf.js](https://github.com/DSpace/dspace-angular/blob/master/karma.conf.js#L7) points to webpack.test.js at the start. So basically, webpack.test.js is the only webpack file considered and used for the test builds.

So at the end of the hour I'm thinking webpack.test.js should be modified to load the assets and will check this idea with my colleagues. 

# Day 70 Plan

Access the assets and hopefully get a successful test run in place

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