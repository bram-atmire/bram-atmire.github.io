---
layout: post
title:  "100 Days of Code Day 90 - .po and .pot translation files"
date:   2018-11-24 15:47:00
categories: 100DaysOfCode
---

# Migrate from JSON to .po and .pot translation files

Instead of continuing the use of the JSON translation files that ngx-translate supports, there seems to be [more advantages in switching over to the use of the .po file format](https://github.com/DSpace/dspace-angular/issues/306). 

As I'm unfamiliar with the .po format, here is what I'm learning.

# One source version of a particular string is used as the ID.

In the current JSON format, each message has a particular key. The keys are organised in a hierarchy. For example:

```json
"community": {
    "page": {
      "news": "News",
      "license": "License"
    },
``` 

So basically community.page.news is the key and "News" is the message. These keys are used in the code with the pipe | translate to use the applicable translation.

[The PO Format](http://pology.nedohodnik.net/doc/user/en_US/ch-poformat.html) seems to indicate that such keys don't exist in the .po format and that one translation, for example the English one, of a particular string, works as the key. 

# You should never change the msgid

In 2.1.3 of [The PO Format](http://pology.nedohodnik.net/doc/user/en_US/ch-poformat.html) I'm reading the following:

```
The third, so to say, consequence, though more of a remark for clarity, is this: you should never modify the msgid string. Not only that doing so would have no purpose, but if the msgid is modified, the consumer of the translated PO file will not see the message as translated, since it will fetch messages by matching their msgid strings.
```

But if msgid is the reference string in one of the source languages, I assume it IS possible that it can change, if the wording of the original message effectively needs to change. But maybe the better way around it, when such a change is necessary, is to introduce a NEW msgid instead of changing the original one.

# Each combination of msgctxt and msgid needs to be unique

msgctxt is a variable that is optional, but can be used to give more clarification in which context a msgid is used. The uniqueness constraint in po files is not ONLY on msgid, but is on the PAIRs of msgctxt and msgid. 

So the recommended approach if you have to exactly the same strings in English, that are still used for different things, is to provide a msgctxt for them.

# Extracted comments VS translator comments

The creators of the language file can give guidance to translators using "extracted comments" that start with the hash tag immediately followed by a period. An agreed word like "TRANSLATORS:" could be used to clarify that a statement is indeed one of these "extracted comments" meant as guidance for the translators.

As a translator, you can leave comments in the translated file as well, using a translator comment which is just a hashtag, followed by a space.

```
#. TRANSLATORS: watch out for ...
# Translator comment
```

# Dealing with plurals

The .po file format has an elegant way of dealing with plurals, taking into account that plural forms can differ across languages.

The nplurals variable indicates how many plural forms there are. The plural heading expresses which of the plural forms for a particular language, needs to be used in which case.

# .po vs .pot

.po is a file with message ids and translations, while .pot is the template file that ONLY has the msgids and doesn't have translations.

# Fuzzy and previous string comment

When merging an old po file with a new version of the .pot file, it's possible that msgids or msgctxt have changed and that the previous translation not entirely applies anymore. That's why the hashtag-pipe "previous string" comments were introduced, to give you information on what the previous msgid was. And the hashtag-comma comment followed by "fuzzy" is intended, I think, to highlight the attention of the translator.

The fuzzy flag has to be removed once the ambiguity is resolved. Because the interpreters of the .po format will treat msgids with the fuzzy flag as untranslated.

# ngx-translates vs angular-gettext

Ended up on [Angular-gettext](https://angular-gettext.rocketeer.be/) and wondering what the similarities and overlaps are with ngx-translate. 

Very likely, Angular-gettext is only meant for AngularJS (Angular 1) and probably not compatible with Angular (6). [Working with ngx-translate](https://blog.neptune-ubi.com/working-with-ngx-translate/) seems to confirm this.

# Example project and files?

I tried to find an example Angular project that was actually using .pot and .po files, but couldn't find one. 
For tomorrow, I'll try to manually create a .pot and .po file and see if I can get the Po file loader for ngx-translate to work.

# Day 91 Plan

Make a .pot and .po file for Dutch and English. Try to get it to load.

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