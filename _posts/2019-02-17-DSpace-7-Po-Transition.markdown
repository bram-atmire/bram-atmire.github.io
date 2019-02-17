---
layout: post
title:  "DSpace 7 - PO transition"
date:   2019-02-17 20:00:00
categories: DSpace7
---

# Picking up finalization of the PO file translation again

Hard to imagine it's been since Dec 22nd since working on this. 

# Curly braces and pattern replacements

Before throwing out the message keys, this used to work

```
  {{ 'footer.copyright' | translate:{year : dateObj | date:'y'} }}
```

However, now that the English messages are replacing the keys, the following became part of the code:

```
{{ 'copyright © 2002-{{ year }}' | translate:{year : dateObj | date:'y'} }}
```

Where the interpolation of the additional curly brackets become a problem. I was able to get around the problem with:

```
{{ 'copyright © 2002-{'+'{ year }'+'}' | translate:{year : dateObj | date:'y'} }}
```

Effectively breaking two consecutive curly brackets into different string concatenations. Credit to:

[How do I escape curly braces for display on page when using AngularJS?](https://stackoverflow.com/questions/16868024/how-do-i-escape-curly-braces-for-display-on-page-when-using-angularjs)

# Phasing out message keys in the .pot catalog and the .po files for German and Czech

Similar to how in my Dec 22nd work, I executed repren on the entire codebase, I now just executed it on the catalog and on the German and Czech file, and that seemed to work.

# Rebasing on master

Rebased my work on the latest master, as I was considerably behind on the new theme etc.

# Next actions

I spotted several places where keys are not part of the catalogs yet. I can continue and enrich the catalogs with more of these keys before the json catalogs can be deleted.

## DSpace 7 Angular

* Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.
* UI for enabling/disabling particular languages
    * Continue with implementing the actions and the reducer for the language switch.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

## Analyzer.atmire.com work

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
* Create a new item test to check if the publication date is correct, or has a high chance of being wrong

## Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

## Jekyll http://bram-atmire.github.io/ site

* Make it prettier

## Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.
Look into web.dev from google for this (thank you Philip)

## Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)