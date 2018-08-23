---
layout: post
title:  "100 Days of Code Day 04 report"
date:   2018-08-23 07:01:00
categories: 100DaysOfCode
---

With a proper controller in place for the homepage of the [Atmire Analyzer](https://analyzer.atmire.com), I was now able to add some data from the list of repositories I have in the back end. The repository list class already had a method of pulling repositories from a specific date range. Went ahead and pulled the repositories from the last 12 months.

Dove into the index.jsp and the JSTL tag library again to see how I could iterate over the list and have them displayed. Still very rough around the edges but I managed to ship this first rudimentary version.

If you now scroll down on the homepage of [Atmire Analyzer](https://analyzer.atmire.com), you can see all of the recent repositories that people have analysed with the tool.
  
# Day 05 Plan

I want to write a method that sums up the item counts for all repositories analysed by the tool and have that displayed as a stat on the homepage as well.