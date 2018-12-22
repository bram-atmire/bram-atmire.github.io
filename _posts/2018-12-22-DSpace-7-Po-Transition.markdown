---
layout: post
title:  "DSpace 7 - PO transition"
date:   2018-12-22 20:00:00
categories: DSpace7
---

# Coding in Poland

Went to bed at 7pm yesterday night. Got up at 1.30am. Drove 1100km to Poland. 
My girlfriend is off with her mother and sister for shopping. Her father doesn't speak enough English and I don't speak 
enough Polish to get more than a very basic conversation going so I'm turning to ...

# Yarn lock conflicts

The master branch of DSpace 7 Angular has been upgraded to Angular 6, but I have additional dependencies as part of the language work that are not in the standard DSpace yarn.lock file, causing conflicts. For now, I have committed my lock file locally, but this will be a merge conflict to be resolved later.

Also noticed I still had [NGX Transate Extract](https://github.com/biesbjerg/ngx-translate-extract) installed in the package.json
of the project locally, that was initially used to extract message keys. Removing this again as I'm not sure it will still be needed or useful going forward.

# Work on the patfile for repren batch message key replacement

Given that I previously found that it worked well for a single string replace, I'm now building a pattern file (patfile) 
the entire message catalog.

## The key "title"

Skipping the key "title" rename to DSpace as this message key is likely too generic and would potentially match too much.

## search.description

That key currently has no translation in the en.po file. Have to figure out later where this is used.

# First go with the patfile

Did a first run on the codebase, changing 59 files at once with [my first full patfile](../../../../assets/2018-12-22-patfile).
You can see the results in this [published commit](https://github.com/bram-atmire/dspace-angular/commit/5fd920489177bb4e918b6fa7387a34a6b8dce196)

## Changes of labels in ts files instead of html files

In HTML files, we're generally OK, since the message keys are replaced right before the | translate pipe.
However, I'm not 100% sure if it's cool that the same thing happens in .ts files.

For example, [item.page.collections changing into "Collections" in collections.component.ts](https://github.com/bram-atmire/dspace-angular/commit/5fd920489177bb4e918b6fa7387a34a6b8dce196#diff-dffefd5090fe7329dc0fa74e916f969eR24)

Another example in a [routing module](https://github.com/bram-atmire/dspace-angular/commit/5fd920489177bb4e918b6fa7387a34a6b8dce196#diff-2c92a2e3af2545e27b8a7a4a478c1b42R9)

## Longest possible matching patterns should come FIRST in the patfile

The patfile had these replace instructions:

```
item.page.files	Files
item.page.filesection.description	Description:
item.page.filesection.download	Download
item.page.filesection.format	Format:
```

The problem was that the first of these patterns matched all of the following. As a result, 
```
item.page.filesection.description
```

Was replaced with 
```
Filesection.description
```

instead of being replaced by "Description:"

## Messed up imports

There were also cases of parts of [import statements being equal to specific message keys](https://github.com/bram-atmire/dspace-angular/commit/5fd920489177bb4e918b6fa7387a34a6b8dce196#diff-a93eb0e4691b23ce802219eee5358e27R11).

# Cleaned up what I could fix

Made manual fixes for the problems above and [published these changes](https://github.com/DSpace/dspace-angular/compare/master...bram-atmire:issue-331-migrate-json-language-catalogs-to-po?expand=1).

# TODO

Now that the keys have been replaced with the English original messages, the .po files for Czech, German and Dutch also
have to be updated so that the strings don't appear anymore. Should be a piece of cake with another repren replace.

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