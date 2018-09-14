---
layout: post
title:  "100 Days of Code Day 26 report - input boxes"
date:   2018-09-14 22:00:00
categories: 100DaysOfCode
---

# CSS: Text in input boxes can't be selected

My colleagues noted that the several input boxes suffer from a problem where the text is no longer selectable, likely due to the inheritance of a transparancy parameter.

The grayscale theme I copied had the following CSS rules in, and after removing them the problem was resolved, as the text became selectable again.

```CSS
::-moz-selection {
    text-shadow: none;
    background: #fcfcfc;
    background: rgba(255, 255, 255, 0.2);
}
::selection {
    text-shadow: none;
    background: #fcfcfc;
    background: rgba(255, 255, 255, 0.2);
}
img::selection {
    background: transparent;
}
img::-moz-selection {
    background: transparent;
}
body {
    webkit-tap-highlight-color: rgba(255, 255, 255, 0.2);
}
```

I'm not entirely sure why you'd want to change this in the first place. Even though it could be part of a design, I'd personally prefer that a website behaves as close to what a user would expect by default. Anything that would happen that's counter intuitive and needs extra thinking from the user could better be avoided. Unless you want to deliberately surprise/delight the user with something non standard.

Learned about [::selection](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection) and [-webkit-tap-highlight-color](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-tap-highlight-color)

# CSS: Fixed nav bar on mobile viewport and pages other than home

The dynamic nav where the colour switches was broken on mobile and on other pages of the system, resolved a few more problems there, hope I got them all now.

# Day 27 Plan

* Add recently verified items to the homepage.

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
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


