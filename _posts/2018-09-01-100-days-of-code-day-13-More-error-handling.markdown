---
layout: post
title:  "100 Days of Code Day 13 report - More error handling"
date:   2018-09-01 18:00:00
categories: 100DaysOfCode
---

# Improving logging and error messages

Cases I covered today:
* The 403 forbidden response that I blogged about earlier
* Trimming leading and trailing spaces from entered URLs
* Connection timeout where the server doesn't respond in 10s.
* A 404 not found where we have a webserver that responds but can't find the page
* Connection refused
* PKIX path building failed

The case I still need to complete is:
* The URL is not recognized as a DSpace because we can't find the browse-title page

Two problems here:
* the check if there is a valid DSpace browse-title page is buried deep within the void "addRepo" method. I have to get it out there and have it return a proper error method if those browse pages can't be found.
* My check if adding a repository was successful still isn't good enough.

# Day 14 Plan

Proper error reporting for the end user if the submitted url is a working website, but can't be recognized as a DSpace.

# Future days

* Work on SEO for atmire.com
* Setup IDEA so I can start editing these blogposts from there, instead of in a text editor
* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)
* Change CSS styling to true Atmire style.
* Switch to a different project: start working on DSpace 7 Angular

# Sustainability - Raising the stakes - I'm going to do it

I'm raising the stakes by
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