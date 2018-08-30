---
layout: post
title:  "100 Days of Code Day 11 report - Improving error logging"
date:   2018-08-30 06:26:00
categories: 100DaysOfCode
---

# Improving logging

My error page was a very generic error page that did not reveal any particular error message. I have extended that view, by supporting a text reason that can be passed down to that view.

When looking deeper, I saw that I have lots of boolean methods like "returnsOK", that either return true when something works as expected, and false when something is wrong. The problem here is that I sometimes swallow a whole bunch of different errors, with generic catch (Exception e) blocks.

I once read in Effective Java that Java Exception handling should primarily only be used for really exceptional things that go wrong. So if I know that I'm using a user input field for a URL, it's not really an exceptional thing that somebody enters an invalid URL, for example starting with gttp instead of http. So to avoid the performance hit that it takes to roll off exceptions, I better catch these specifically, return some more meaningful error codes and provide a correct error message.

But that will require refactoring of those generic "returnsOK" methods into the more meaningful ones.

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
