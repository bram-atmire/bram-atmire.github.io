---
layout: post
title:  "100 Days of Code Day 43 - ng-book 2 p73-82"
date:   2018-10-03 07:00:00
categories: 100DaysOfCode
---

# sort() and arrow functions

In a one line example on p82, both sort() and Arrow (=>) functions are introduced.

```typescript
sortedArticles(): Article[] {
return this.articles.sort((a: Article, b: Article) => b.votes - a.votes);
}
```

I went through part of the docs on [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) and [Sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) but both of them were quite deep rabbit holes.

What I get from it is that sort() gives you a default unicode sort operation on an array, but can also take in a comparator function, in order to sort by a specific comparison.

The arrow functions in their turn, make it easier to write shorter functions. But I have the feeling those are docs I'll need to refer again to later. 

# Day 44 Plan

Take a break from ng-book and have a look at DSpace 7. Goal would be just to look around the documentation of what's already done, and go through the codebase, and write down everything I don't understand yet. This set of questions/topics might give me a good direction of knowing what to look for, as I plow further through the book.

# Future days - DSpace 7 Angular

* Finish angular.io tutorials
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