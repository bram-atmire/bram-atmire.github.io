---
layout: post
title:  "DSpace 7 - PO transition"
date:   2018-12-17 07:09:00
categories: DSpace7
---

# DSpace 7 i18n transition to Po Files - current status

Both from my own team as from community members, there has been [no objection so far](https://waffle.io/DSpace/dspace-angular/cards/5bfcd397e35a9403d585abb7) for getting rid of the intermediate message keys, and use the English messages as keys instead.

So right now we have:
* a .pot file that only has the intermediate message keys - not very useful right now in the transition
* a .po file that has the message keys and the English messages
* The source code, only referencing the message keys.

This means the challenge is to make a CLI script with [grep / awk / sed](https://stackoverflow.com/questions/7727640/what-are-the-differences-among-grep-awk-sed) that:
1. iterates over the message keys in the .po file
2. searches the source code for a key
3. replaces the key with the message in the source code

# Step one: make it work for ONE key

Let's take following key as the test case:

```
 msgid "404.help"
 msgstr "We can't find the page you're looking for. The page may have been "
 "moved or deleted. You can use the \"Back\" button below to get back to the home page. "
```

It has:
* a message over multiple lines
* a single quote, that has to be escaped when we put it in Angular code
* a double quote, that is escaped right now, but likely doesn't (?) need to be escaped in Angular

Tried to Google if anyone has already did this particular challenge before, but didn't find it, so I guess we're on our own.

## Grep: finding the key

A recursive grep, only looking in the .src folder seems to do the trick. Doing this one directory higher brings up too many results, including the language files themselves.

```
grep -r "404.help" ./src  
./src/app/pagenotfound/pagenotfound.component.html:  <p>{{"404.help" | translate}}</p>
```

But after all, I may not need to use grep at all, since sed can also [find a pattern recursively](https://stackoverflow.com/questions/11392478/how-to-replace-a-string-in-multiple-files-in-linux-command-line).

## Sed: replacing the key

I have used this long long ago, so need to [brush up my knowledge](http://www.grymoire.com/Unix/Sed.html#uh-62h).

Sed has so many options and was pretty daunting ... got lost in the many examples that were not entirely applicable.

In [How to replace a string in multiple files in linux command line](https://stackoverflow.com/questions/11392478/how-to-replace-a-string-in-multiple-files-in-linux-command-line) I learned about repren

## Replacing strings with repren

The [Repren tool](https://github.com/jlevy/repren) seems to be designed exactly for what I want to do, example:

```
» ./repren --from 404.help --to "We can't find the page you're looking for. The page may have been moved or deleted. You can use the \"Back\" button below to get back to the home page. " --full --dry-run .
Dry run: No files will be changed
Using 1 patterns:
  '404.help' -> 'We can't find the page you're looking for. The page may have been moved or deleted. You can use the "Back" button below to get back to the home page. '
Found 3 files in: .
- modify: ./another-file.html: 1 matches
- modify: ./intro.html: 1 matches
Read 3 files (23029 chars), found 2 matches (0 skipped due to overlaps)
Dry run: Would have changed 2 files (2 rewritten and 0 renamed)
```

When executed without the dryrun flag, it makes backup copies of the files to be changed into .orig files.
This first try already worked pretty well, however, the single quotes still needed to be escaped.

For multiple replaces, Repren supports pattern files with per line, a string that has to be replaced, a tab character, and the pattern by which it needs to be replaced.

My first pattern file:

```
404.help	"We can't find the page you're looking for. The page may have been moved or deleted. You can use the \"Back\" button below to get back to the home page. "
404.link.home-page	"Take me to the home page"
```

Unlike the first individual example, this one does copy the surrounding double quotes as well, so the pattern file can't contain those double quotes.

```
404.help	We can't find the page you're looking for. The page may have been moved or deleted. You can use the \"Back\" button below to get back to the home page.
404.link.home-page	Take me to the home page
```

Right now, I think I'll just put the single quote escaping into the pattern file itself.

# TODO

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