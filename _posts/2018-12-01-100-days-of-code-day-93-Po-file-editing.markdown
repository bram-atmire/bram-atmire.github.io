---
layout: post
title:  "100 Days of Code Day 93 - Po files editing"
date:   2018-12-01 16:50:00
categories: 100DaysOfCode
---

# Upgrading IntelliJ IDEA to 2018.03 release

Following improvements in the [What's new overview](https://www.jetbrains.com/idea/whatsnew/) sparked my interest.
* Support for Github Pull requests
* Improvements ot the built in Terminal, including storing of the last working directory
* Improved Angular support
* More flexibility for TS Lint

# IDEA trick: having two files open sideways and jumping between them

On Day 92, I was using "compare to clipboard" to have the old JSON catalog open alongside the new .po catalog, but I couldn't find how to jump the cursor between the two editors.

Today I found that you can use "Split", to split the active editor window either horizontally and vertically, and then use the control+tab "Switcher" to jump between the two.

# Migrating the current .json catalogs to .po

I migrated all the Dutch keys from the .json to the .po file by hand. Wondered whether there would be an automated convertor and found [Translate Toolkit](http://docs.translatehouse.org/projects/translate-toolkit/en/latest/index.html)

Installed translate toolkit on Mac using homebrew. In the process, homebrew also recommended me to upgrade Git as well.

All these funky upgrades ... broke my built in terminal in IntelliJ IDEA. Got hit by [This particular issue](https://github.com/robbyrussell/oh-my-zsh/issues/7033) and an upgrade to zsh fixed it.

# Automated migrations from .json to .po 

Running json2po from Translate toolkit didn't work entirely out of the box with the default options, as it produced:

```
#: .item.page.abstract
msgid "Kurzfassung"
msgstr ""
```

While the goal was

```
msgid "item.page.abstract"
msgstr "Kurzfassung"
```

Didn't find a way to improve the transformation, so I tried to transform these erroneous results with the IntelliJ IDEA [Multiple Cursors feature](https://blog.jetbrains.com/idea/2014/03/intellij-idea-13-1-rc-introduces-sublime-text-style-multiple-selections/)

# Investigation into missing keys

On day 92, I found out that following keys were not identified in the automated extraction:

* bitstreamformats.formats.table.supportlevel.0
* bitstreamformats.formats.table.supportlevel.1
* bitstreamformats.formats.table.supportlevel.2
* collection.page.news
* collection.page.license
* error.validation.*
* home.title

Today I found more:
* search.filters.applied

# Keys extracted that were not part of the original json

Also found following keys in the automated extraction that weren't part of the original json files

* search.results.no-results-link

# Day 94 Plan

Continue with the Czech and English po files.
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