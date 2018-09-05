---
layout: post
title:  "100 Days of Code Day 17 report - CSS"
date:   2018-09-05 06:55:00
categories: 100DaysOfCode
---

# Background image #2

Found another image from  <a href="https://www.freepik.com/kjpargeter">Kjpargeter / Freepik</a> to replace the second image on the page.

When I just replaced it, leaving the current "no-repeat center center scroll" attributes in place, Chrome shows the bottom part of the picture while I wanted the top part.

[W3Schools CSS 3 Background attributes](https://www.w3schools.com/cssref/css3_pr_background.asp)

I found out that I can manipulate it the way I want changing the first "center", the background-position, attribute to top. But I fail to understand how it works, because it seems to fill the entire container that it's in, so i'm not sure what it's positioned against.

Because the image was too busy, I ended up just using the bottom piece of the image that I alraeady had.

# Improvements on mobile

Instead of a fixed width, I now use a percentage width for the homepage Atmire logo, and height set to auto. This solved the initial problem where the image wouldn't resize and stick to its hard coded defined width.

# Scripts need a mandatory type attribute

Intellij IDEA gave me another compliant/warning:
[Element 'script' is missing required attribute 'type'](https://stackoverflow.com/questions/5138543/element-script-is-missing-required-attribute-type). Even though everything seems to be working, I added that type="text/javascript". It's a requirement for HTML4 and XHTML, but not for HTML5. So should not be an issue for browsers rendering HTML5 anyway.

# Day 18 Plan

I more or less completed what I wanted to do, CSS-wise, on the analyzer tool. Tomorrow I want to see if I can identify problems and maybe make improvements to the SEO for the main www.atmire.com site.

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future days - Analyzer.atmire.com work

* Analyzer: Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Analyzer: change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Analyzer: Add recently verified items to the homepage.
* Analyzer: Optimize my hideous methods for getItemcount and getRepoCount.
* Analyzer: re-test the check if we return the right repository to a user who tries to add a new one
* Analyzer: updating a repository: touch/change the base URL or not?
* Analyzer: batch ingest: switch to newer add repository methods.
* Do WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.

# Future Days - other ideas

1. Switch to a different project: start working on DSpace 7 Angular
2. Setup IDEA so I can start editing these blogposts from there, instead of in a text editor
3. Developer productivity: Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)

# Sustainability - Raising the stakes - Looking for sponsors

I have raised the stakes by
* giving €100 to Charity:Water for every day I miss.
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win. These are the rules that I'll apply:

1. I can anticipate or fix a lost day by doing an hour extra the day before, or an hour extra the day after. In theory this means I can maximally compensate a streak of 2 missed days. 
2. Goal is to have a steady frequency, so I can't just do 8h on a sunday to get myself off the hook for the next 7 days.
3. Sponsor commitments are fully voluntarily: any sponsor can back out at any time.
4. My commitment is fully voluntarily: if I want to change the rules or back out, I can at any time.

In September, these are already days that will be very tough:
* Sep 8,9 - FoM Lanparty w friends
* Sep 14,15,16,17 - Abroad for a wedding
* Sep 27,28 - Supernova conference Antwerp

So that's already a lot of exposure to potentially missed days. 

I will raise the stakes this way and gather money for Charity:Water. Let me know if you want to sponsor me and for how much per completed day in September. September 1st is the first successfully completed day.

# September tracking

Will only log the failed days here. No failed days so far.

# Thanks to the following sponsors!

1. Jan & Hilde: €2 per successful day (Yes, these are my parents)


