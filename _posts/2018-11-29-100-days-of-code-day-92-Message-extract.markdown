---
layout: post
title:  "100 Days of Code Day 92 - Message extract"
date:   2018-11-29 07:30:00
categories: 100DaysOfCode
---

# Transform current JSON catalog and translations to .po

On [Day 91](http://bram-atmire.github.io/100daysofcode/2018/11/27/100-days-of-code-day-91-My-little-po-file.html), I established that the current message keys and their translations can be loaded with the .po format and the .po loader.

Instead of manually re-writing the catalogs to update them to the new format, I want to see if I can do it automatically, using [NGX-Translate-Extract](https://github.com/biesbjerg/ngx-translate-extract)

# Fix version number of dependency?

Last time I used IDEA's suggestion to add @biesbjerg/ngx-translate-po-http-loader as a dependency to package.json.
I now saw that it has done this without a specific version:

```
"@biesbjerg/ngx-translate-po-http-loader": "latest"
```

Likely it's better to pin down the version, but when I look at the tags in that repository, the 2.0.1 tag dates from november 2017, even though there have been commits on master this august. 

So for now, I'm keeping this at latest but this probably still has to be pinned down going forward.

# Reverting to an older version of extract

Ran into [SyntaxError - Unmatched selector #87](https://github.com/biesbjerg/ngx-translate-extract/issues/87) and resolved it as suggested by pinning down version 2.3.2 of ngx-translate-extract

The extraction worked. At the moment it doesn't retrieve the source code reference yet, for which the .po format has support in the \#: comments, but this functionality has already been proposed in [PR 102 for ngx-translate-extract](https://github.com/biesbjerg/ngx-translate-extract/pull/102).

# Message IDs not extracted

From the following piece:

```
      "bitstream-formats": {
        "title": "DSpace Angular :: Bitstream Format Registry",
        "head": "Bitstream Format Registry",
        "description": "This list of bitstream formats provides information about known formats and their support level.",
        "formats": {
          "table": {
            "name": "Name",
            "mimetype": "MIME Type",
            "supportLevel": {
              "head": "Support Level",
              "0": "Unknown",
              "1": "Known",
              "2": "Support"
            },
            "internal": "internal"
          },
          "no-items": "No bitstream formats to show."
        }
      }
```

Those message ids ending in 0, 1 and 2 were not extracted automatically. To be investigated in the code if they are perhaps not used at the moment.

Same goes for collection.page.news, collection.page.license, error.validation.*, home.title

# Day 93 Plan

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