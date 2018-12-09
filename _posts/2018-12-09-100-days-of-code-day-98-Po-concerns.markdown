---
layout: post
title:  "100 Days of Code Day 98 - Po concerns"
date:   2018-12-09 08:49:00
categories: 100DaysOfCode
---

# Wondering about Max line length

The [DSpace Code Style guidelines](https://wiki.duraspace.org/display/DSPACE/Code+Style+Guide) mention a max line 
length of 120 characters.

However, the aids that it has in place, the [tslint config](https://github.com/DSpace/dspace-angular/blob/master/tslint.json#L33) and 
[.editorconfig](https://github.com/DSpace/dspace-angular/blob/master/.editorconfig) are currently not enforcing this. Wonder 
why and will ask my colleagues, as I can't see a reason for NOT enforcing it if it's a rule after all.

We had a discussion on this over lunch earlier this week. One of the points that was made there is that automatically
 cleaning up/making lines shorter doesn't work, because it's best that a developer makes a conscious choice about how
  and where to break the line.

# Errors in yesterday's blog

When writing about escaping in the previous blog, I didn't take into account that some escaping might had to be in 
place to make the blog render correctly. Turns out that it's problematic in several places but not a high priority 
right now to fix it there. You can always find the [raw version of the blog](https://github
.com/bram-atmire/bram-atmire.github.io/blob/master/_posts/2018-12-07-100-days-of-code-day-97-Po-concerns.markdown) here if you're interested.

# Demonstrator for the context field

In the current approach, where each message has a unique message ID, you can very easily have two different message 
keys that have the same value. For example, you could assign the string "Home" or "Back" to different message keys 
for different places where they would be used.

If the message itself will be used as the key, it's not trivial anymore to have several occurences of the same 
original message (in English). Gettext and the .po format solve this by the optional parameter msgctxt.

For the demonstrator, I was looking into ways to express context through the translate pipe. Let's say I have two 
different places where I want to use the string "Home", but still allow translators in different languages to have 
different translation in both of these places

```
{{ 'Home' | translate }}
{{ 'Home' | translate }}
```

Looking through the documentation, as well as the code of ngx-translate and the additional po loader, I can only 
conclude that this feature of Gettext/.po is currently not yet supported. However, there seems to be a pull request 
where it is being introduced:

[Retrieve context, comments and reference via translate directive](https://github
.com/biesbjerg/ngx-translate-extract/pull/102)

But if we were to adopt .po right now in DSpace, I think we have to live with the fact that a single original message
 can only have a single translation right now.

# Day 99 Plan

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
* explore utteranc.es for adding commenting possibility (thank you Philip)

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.
Look into web.dev from google for this (thank you Philip)

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.