---
layout: post
title:  "100 Days of Code Day 25 report - DB reset"
date:   2018-09-13 23:30:00
categories: 100DaysOfCode
---

# Database reset

In order to investigate the problem with empty repository rows appearing on the homepage of the tool, I wanted to bring the database of the remote server back to my local laptop.

A pgdump SQL export gets created every day on the server as a backup, but I couldn't remember how to actually import that locally.

After trial and error, and seeing a lot of strange errors including "invalid command \N" and syntax errors, I did get my PROD data loaded into my local DB. I'm not entirely sure my full database is consistent now, but I do see the same data in the UI of the app as on the live PROD system.

There were likely a few issues:
- the DB users & roles on the prod server are not the same as locally, as I have "bram" locally setup as my postgres super user, while it's "postgres" on PROD.
- I don't know exactly what pg_dump export options were used. Because of the different ways and formats on how you can create an export, you need to tweak the way how you import it.

Primarily for my own future self if I ever try this again: 

psql -U dspacesitechecker -d dspacesitechecker -1 -f dspacesitechecker.sql

totally failed from the command line, but the IntelliJ IDEA "Restore" dialog was successful.

# Investigating and resolving the empty rows in the recently scanned repository overview

The empty rows were caused by the Title tag among the HTML HEAD attributes not being filled out. So in the JSPs, I entered a conditional check to render "Repository Title Not Set" as the message to show when there was no title.

JSTL has a very handy "empty" operator that basically made this thing a one liner.

Thank you again Stack Overflow for [Evaluate empty or null JSTL c tags]
(https://stackoverflow.com/questions/2811626/evaluate-empty-or-null-jstl-c-tags)

# Day 26 Plan

* CSS: Solve text selection issues in the input boxes

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
* Try to make the navbar text white all the time on mobile. 

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


