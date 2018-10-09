---
layout: post
title:  "100 Days of Code Day 47 - DSpace 7 Language"
date:   2018-10-09 07:00:00
categories: 100DaysOfCode
---

# Local differences in yarn.lock

Tried to resolve this by deleting my local yarn.lock file, and running yarn install with the flag to skip the integrity check.
That didn't work, as the integrity entries were still there.
I ended up doing:

```
git reset HEAD yarn.lock
git checkout -- yarn.lock
```

And that got me rid of my local changes. I'm not quite sure what exact benefit I'm getting out of yarn.lock being under version control. Might be interesting to discuss with my colleagues at work.

# Adding a third language to the language switcher - On stackblitz example

To address my problem from yesterday, I first tried to get it to work in the [NGX-Translate Example](https://stackblitz.com/github/ngx-translate/example). I created a little nl.json file in the assets directory, with translations for the two message tags there.

But when adding it to the matcher and trying to do the switch, I always got:

```
Http failure during parsing for https://llqimpww.github.stackblitz.io/assets/i18n/nl.json
```

Ran the contents of the file through https://jsonlint.com/, where it stated that the contents were ok. The other option was that stackblitz was somehow unaware of this new file added in the assets dir. Was not able to solve this yet.

# Back to DSpace - commenting out the matcher for browser language

DSpace was complaining about the following:

```
TypeError: Cannot read property 'match' of undefined
```

So for now, I commented out the part where it tries to set the language based on the language of the user:

```typescript
    const browserLang = translate.getBrowserLang();
    translate.use(browserLang.match(/en|nl|cs/) ? browserLang : 'en');
```

Right now, this piece is sitting in the constructor of the main app component, so maybe at that time the browserlang is just not available yet.
Commenting this out did the trick, and I now had a working, yet ugly language switcher, with two languages, German and English.

# Added additional languages

Also added Dutch and Czech to the switcher.

# Yarn start not picking up changes live like ng-serve does

I keep experiencing that I have to kill yarn start and run it again, for it to pick up changes. Likely I'm doing it wrong and there must be a faster way to recompile/reload changes.

# Day 48 Plan

Style the ugly language switcher.

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