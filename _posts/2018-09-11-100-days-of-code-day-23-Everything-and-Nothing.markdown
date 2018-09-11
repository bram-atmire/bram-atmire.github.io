---
layout: post
title:  "100 Days of Code Day 23 report - Everything and nothing"
date:   2018-09-11 22:44:00
categories: 100DaysOfCode
---

# Resolving padding issues and alternating background colours

Not solved yet, to be continued tomorrow. Got sidetracked by the things below:

# More classes per div OR more divs with less classes

I found the following in my current code:

```HTML
<section id="getstarted" class="content-section text-center">
    <div class="download-section">
        <div class="container">
            <div class="col-lg-8 col-lg-offset-2">
```

The nested divs didn't seemt to have any other use than adding another css class. I think it's exactly the same as:

```HTML
<section id="getstarted" class="content-section text-center download-section container col-lg-8 col-lg-offset-2">
```

This somehow brought me to the topic of nested selectors and the [inception rule](http://thesassway.com/beginner/the-inception-rule). I remember from my colleagues that SASS compiles to CSS and is assistive to make it easier to write css, including the nested selectors. Added to future ideas to transition from normal CSS to sass.

But it still didn't address my original concern whether it's better to have lots of nested divs, with only a single (or limited) classes per div, versus applying lots of different classes to a single div. Not sure what's style or best practice wise preferred. Likely limiting the number of classes that you need to apply is a first.

[CSS - Multiple vs Single class on an element](https://stackoverflow.com/questions/5568718/css-multiple-vs-single-class-on-an-element) indicates that the number of classes on an element, doesn't really make a performance difference if you're still dealing with relatively small amount of classes.

[Is having multiple classes in an element a good (or best) practice?](https://stackoverflow.com/questions/28376773/is-having-multiple-classes-in-an-element-a-good-or-best-practice) is pretty much my exact concern, but it was closed because it's "opinion based".

So all in all, it's likely just "choose what you want" but best to apply it consistently.

# Container vs Container-fluid

I previously gave a [Container](https://getbootstrap.com/docs/4.0/layout/overview/) object a 100% width to enforce the width. Turns out the better way to achieve this is to use the container-fluid class in Bootstrap instead of modifying width of a container.

But with the non-fluid container class, you can manipulate things like width at each size-breakpoint. Since the analyzer only has sections that can span the entire width of the screen, I'm now re-evaluating if it makes most sense to stick with the regular containers or container-fluid.

# IntelliJ IDEA foreign keyboard layout support

Some of the IDEA standard keymap shortcuts are not working for me on AZERTY and for now I've resisted the urge to write a custom keymap. Basically, I want to fix it and use/rely on the standard keymap.

Today I found a PARTIAL "workaround" for my azerty based shortcuts not working

[Custom property - old key event processing](https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000163784-macOS-keymap-changed-in-2017-foreign-keyboard-layout-)

This seems to fix all my issues with the CMD+1, CMD+2, ... shortcuts but not yet the CMD+/ for turning someting into comments. 

Also, some keys are 

[MacOS: The shortcuts work unexpectedly after 2017.1 update](https://intellij-support.jetbrains.com/hc/en-us/articles/115000616724-MacOS-The-shortcuts-work-unexpectedly-after-2017-1-update)

# Day 24 Plan

* CSS: resolve padding issues and make the background of the "basic principles" section darker again.
* Investigate empty rows with TODO message showing up in the list of recently scanned repos

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* Investigate empty rows with TODO message showing up in the list of recently scanned repos
* Transition from plain CSS to SASS to make it prettier and learn about SASS at the same time

# Future Days - other ideas

1. Switch to a different project: start working on DSpace 7 Angular
2. Setup IDEA so I can start editing these blogposts from there, instead of in a text editor
3. Developer productivity: Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability - Raising the stakes - Looking for sponsors

I have raised the stakes by
* giving €100 to Charity:Water for every day I miss.
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win. These are the rules that I'll apply:

1. I can anticipate or fix a lost day by doing an hour extra the day before, or an hour extra the day after. In theory this means I can maximally compensate a streak of 2 missed days. 
2. Goal is to have a steady frequency, so I can't just do 8h on a sunday to get myself off the hook for the next 7 days.
3. Sponsor commitments are fully voluntarily: any sponsor can back out at any time.
4. My commitment is fully voluntarily: if I want to change the rules or back out, I can at any time.

This month, these are already days that will be very tough:
* Sep 14,15,16,17 - Abroad for a wedding
* Sep 27,28 - Supernova conference Antwerp

So that's already a lot of exposure to potentially missed days. 

I will raise the stakes this way and gather money for Charity:Water. Let me know if you want to sponsor me and for how much per completed day in September. September 1st is the first successfully completed day.

# September tracking

Will only log the failed days here. No failed days so far.

# Thanks to the following sponsors!

1. Jan & Hilde: €2 per successful day (Yes, these are my parents)


