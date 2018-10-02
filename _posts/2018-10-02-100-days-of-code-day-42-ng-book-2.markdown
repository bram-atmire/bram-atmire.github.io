---
layout: post
title:  "100 Days of Code Day 42 - ng-book 2 p60-72"
date:   2018-10-02 07:00:00
categories: 100DaysOfCode
---

# Carrying over monday's hour into tuesday

The hour I did yesterday was the catchup with the missing sunday. So today I'm catching up with yesterday and hope to add in another hour this evening for the normal tuesday hour. Anyway, September is over, so I could theoretically stop the €100 punishment for a missed day. But I haven't made up my mind about continuing to do it the same way in the following months. 

# Reformat code vs auto indent lines

Whenever copying parts of code, I would always use auto-indent or reindent lines. But with the ng-book examples, I often found that they came out garbled, so I was looking for a tool that would also tidy up across multiple lines. I found it in IDEA's [Reformat Code](https://www.jetbrains.com/help/idea/reformat-file-dialog.html) feature

# Click handlers and propagation of the click events (source: p68)

JavaScript, by default, propagates the click event to all the parent components. Because the click event is propagated to parents, our browser is trying to follow the empty link, which tells the browser to reload.

Click handler events have to return boolean values, and return false to ensure that the browser won't try to refresh the page due to the propagation of the click event.

# Separate model classes

In earlier tutorials, it always looked like the component.ts file was both the controller and the model. This tutorial introduced the concept of adding and using separate model classes in the component.

# Optional parameters as input in methods

When a parameter is optional, it's enough to simply add a question mark after the variable name.

# Day 43 Plan

Continue on p73 of [ng-book 2](https://www.ng-book.com/2/)

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

# Sustainability - Continuing the donation commitment in October?

I have not made up my mind about continuing the donation experiment in October. I have also started Polish classes, which now means I have to be in class on Wednesday events from 6pm until 9.30pm, which makes it hard to combine with coding in the morning.

# Sustainability - Raising the stakes in September

In September, I have raised the stakes by
* giving €100 to Charity:Water for every day I miss.
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win. These are the rules that I'll apply:

1. I can anticipate or fix a lost day by doing an hour extra the day before, or an hour extra the day after. In theory this means I can maximally compensate a streak of 2 missed days. 
2. Goal is to have a steady frequency, so I can't just do 8h on a sunday to get myself off the hook for the next 7 days.
3. Sponsor commitments are fully voluntarily: any sponsor can back out at any time.
4. My commitment is fully voluntarily: if I want to change the rules or back out, I can at any time.

I will raise the stakes this way and gather money for Charity:Water. Let me know if you want to sponsor me and for how much per completed day in September. September 1st is the first successfully completed day.

# September results

According to the rules above, missing Saturday September 29th was the only day I didn't properly fix afterwards or anticipated beforehand. 
So I owe Charity:Water €100 for that day.

For the 29 days that I completed successfully, Jan and Hilde are adding €2 per day, so that makes another €58.

I'll try to get this all sorted out before the end of the week.