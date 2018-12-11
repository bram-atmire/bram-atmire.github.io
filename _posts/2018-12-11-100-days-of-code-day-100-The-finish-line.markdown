---
layout: post
title:  "100 Days of Code Day 99 - Missing messages"
date:   2018-12-10 07:0:00
categories: 100DaysOfCode
---

# Messages missing from automated extraction

On [Day 92](http://bram-atmire.github.io/100daysofcode/2018/11/29/100-days-of-code-day-92-Message-extract.html) I 
noticed that following messages were missing from the automated extraction:

```
bitstream-formats.formats.table.supportLevel.0
bitstream-formats.formats.table.supportLevel.1
bitstream-formats.formats.table.supportLevel.2
collection.page.news 
collection.page.license
error.validation.*
home.title
```

One reason could be that these keys were defined in the catalog, but that the developer who defined them never 
actually used them. Trying to use search to find where these keys are used.

# Case 1 - Dynamically defined message keys

In the first example, bitstream-formats.formats.table.supportLevel.*, the message key is defined dynamically, see the
 code at [bitstream-formats.component.html](https://github.com/DSpace/dspace-angular/blob/master/src/app/+admin/admin-registries/bitstream-formats/bitstream-formats.component.html#L30)

It seems here that the component itself is agnostic about how many potential values there can be for the support level, and delegates that all to the messages. In case we would want to offer different functionality depending on the support level, or 
apply different CSS rendering, it might make more sense that the component itself is aware of these different values.

# Case 2 - unused keys

For following keys, I found no use or reference in the code

```
collection.page.news
```

On [the place where I would expect that key](https://github.com/DSpace/dspace-angular/blob/master/src/app/+collection-page/collection-page.component.html#L24), I'm seeing community.page.news instead, maybe that's just a typo or maybe I
 don't understand the logic properly.

# Case 3 - key used, but only gets into translation pipe after parameter is renamed

When someone defines a [comcol-page-content](https://github.com/DSpace/dspace-angular/blob/master/src/app/+collection-page/collection-page.component.html#L34) component, 2 parameters need to be supplied: a title and a content parameter. They are not translated at that moment.

Only [in the actual component itself](https://github.com/DSpace/dspace-angular/blob/master/src/app/shared/comcol-page-content/comcol-page-content.component.html#L2), that message key is actually put in the translation pipe

This might get addressed by invoking the translation at the point where the message is inserted, rather than in the component when the message is already generic.

# Conclusion

There doesn't seem to be anything wrong with message extraction and there's usually a good reason why something is not extracted.
The examples found, in my opinion, give even stronger motivation to put the (English) messages directly into the code, rather than working with the level of indirection/obscurity introduced by the message keys.

It may also help developers to see immediately when a certain message fiels wrong, for example too long, for a specific place.

# Day 100 Plan

No coding. Perform some soul searching. Determine whether to stop or continue, and if continuing, in which shape or form.

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
* explore utteranc.es for adding commenting possibility (thank you Philip)

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.
Look into web.dev from google for this (thank you Philip)

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.