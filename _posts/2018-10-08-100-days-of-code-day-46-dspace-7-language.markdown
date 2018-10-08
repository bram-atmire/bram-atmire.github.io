---
layout: post
title:  "100 Days of Code Day 46 - DSpace 7 Language"
date:   2018-10-08 07:00:00
categories: 100DaysOfCode
---

# Local differences in yarn.lock

Due to recent executions of the yarn install and yarn start build commands, my local yarn.lock file got altered with an "integrity" entry for each dependency, containing a hash value.

As yarn.lock is managed in version control for the project, I'm unsure if I can safely overwrite these local changes by getting the latest yarn.lock file from the server.

Keeping my local changes stashed for now.

# Yarn start does not pick up changes

When trying to make the language dropdown, I'm currently seeing no changes. Yet, the terminal where yarn start runs doesn't tell me if there were any compilation errors. If I shut it down, run yarn start again, it does show me where the errors occur. Wondering whether stopping & starting 'yarn start' again all the time is the normal way to go, probably not.

# Currently stuck at

Immediately at runtime I get:

```
TypeError: Cannot read property 'match' of undefined
```

As I had introduced a new match operation, it's probably related to:

```typescript
//Adding all languages for which we currently have catalogs. TODO make this dynamic so all files that are present get loaded
    translate.addLangs(['en', 'nl', 'cs']);
    // the lang to use, if the lang isn't available, it will use the current loader to get them
    translate.setDefaultLang('en');

    const browserLang = translate.getBrowserLang();
    translate.use(browserLang.match(/en|nl|cs/) ? browserLang : 'en');
```

# Day 47 Plan

Continue work on the language switch.

# Future days - DSpace 7 Angular

* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Translate of the standard messages keys in Dutch, to learn how i18n in Angular works
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* UI for enabling/disabling particular languages

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

# September sustainability challenge - Completed

[The money has been wired](https://my.charitywater.org/bram-luyten/code-for-water) and I'm closing the books on the September sustainability challenge where I was sponsored for every successful day and where I would punish myself for every missed day.

# New sustainability challenge - Finish before Christmas

With today being day 43, there are 57 days of coding left. Setting the goal to get there before Dec 25th gives me a little more flexibility while still requiring a high frequency.

In terms of positive motivator, I'm currently thinking along the lines of a big reward at the end, while at the same time still wondering about something more incremental for Oct/Nov, or to have a self-punishment system in here as well.