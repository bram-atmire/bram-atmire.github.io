---
layout: post
title:  "100 Days of Code Day 12 report - Adding error codes"
date:   2018-08-31 06:50:00
categories: 100DaysOfCode
---

# Improving logging and error messages

Where I can, I want to stick to the conventions for javadoc. Today I was struggling with the @return information, since I have multiple possible outcomes for a method. [Should I write multiple @return tags in javadoc](https://stackoverflow.com/questions/37607531/should-i-write-multiple-return-tags-in-javadoc) was exactly what I was wondering about. Single line, just saying in general what your return.

The cases that I have already isolated and for which I now return meaningful error messages
* URLs that don't start with http:// or https://
* URLs with a domain that doesn't resolve
* SSL Handshake error where a sysadmin hasn't configured the Apache "ServerName" attribute
* The general HTTP 500 / Internal server error codes

Cases that I would still like to cover:
* The URL is not recognized as a DSpace because we can't find the browse-title page
* The server responded too slow

And do proper testing for all of these cases.

# Day 12 Plan

Further improvements to logging of updates and more meaningful error messages on the [Analyzer](https://analyzer.atmire.com) failure page.

# Future days

* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)
* Change CSS styling to true Atmire style.
* Switch to a different project: start working on DSpace 7 Angular

# Sustainability - Raising the stakes (No change here)

Just keeping this section in the report. It was already in here earlier, didn't change or makeup my mind yet.

I'm strongly thinking about raising the stakes by
* giving an amount to charity for every day I miss
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win. Still doubting about which rules I should put in place. For now, I'm thinking along the lines of:

1. I can anticipate or fix a lost day by doing an hour extra the day before, or an hour extra the day after. 
2. Goal is to have a steady frequency, so I can't just do 8h on a sunday to get myself off the hook for the next 7 days.
3. Sponsor commitments are fully voluntarily: any sponsor can back out at any time
4. My commitment is fully voluntarily: if I want to change the rules or back out, I can at any time

Thinking further about September, these are already days that will be very tough:
* Sep 8,9 - FoM Lanparty w friends
* Sep 14,15,16,17 - Abroad for a wedding
* Sep 27,28 - Supernova conference Antwerp

So that's already a lot of exposure to potentially missed days. Not sure if raising the stakes this way will be productive or not.
