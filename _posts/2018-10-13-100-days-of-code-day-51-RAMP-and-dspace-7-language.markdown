---
layout: post
title:  "100 Days of Code Day 51 - RAMP and DSpace 7 Language"
date:   2018-10-13 16:35:00
categories: 100DaysOfCode
---

# Small break from Angular: getting DSpace repositories integrated with RAMP

[RAMP](http://ramp.montana.edu/) is an initiative to aggregate and learn from institutional repository usage statistics.
As the common data underpinning this initiative, RAMP leverages Google Search Console / Google Webmaster Tools. I've been in communication with the RAMP team to make adoption by the DSpace community as smooth as possible, looking into ways of making initial verification/authentication to Google Search console data as easy as possible.

# Styling for language dropdown

My colleague Antoine helped me to figure out why following rule was not applying to my language switch:

```css
.navbar-dark .navbar-nav .nav-link {
    color: rgba(255, 255, 255, .5);
}
```

I was assuming that this syntax meant that the colour gets applies on every element that would have one of these classes. But the css syntax when class names are separated with a space means that all of the classes should be present, either on the element itself or on its parents.
If they would be separated with comma's, it would mean that it would get applied on each of these classes individually. And if there would be no separator at all, it means that all classes have to be present on the same element in order for the rule to apply.

# Rebased my branch a hundred times until it was ready to issue as a pull request

Cleaned up my code, moved the languages to the environment config file and finally issued a pull request.

# Day 52 Plan

Either investigate how to write tests for the angular code, or look into the feature of deactivating a language.

# Future days - DSpace 7 Angular

* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
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