---
layout: post
title:  "100 Days of Code introduction + Day 01 report"
date:   2018-08-20 06:39:00
categories: Crawler-Commons
---

# 100 Days of Code Introduction

This weekend I read about [100 Days of Code](https://www.100daysofcode.com/) and decided I want to give it a shot. The goal is to code for one hour every day, for the next 100 Days. I hope this gives me some time to work on things I want to work on already for a long while, but can't find the time for coding in my current schedule. A few specifics about the approach i'm trying out

## What is coding for me?

For me, it's all of the following
* Learning 
* Adding/deleting code
* Testing
* Resolving problems on my local IDE
* Resolving problems on the servers/environments where I deploy
* Planning for the next day of coding
* Defining the scope of what I will or won't do

## Build into the morning routine

I want to try the following:
* 5.30 Get up
* 6.00 Start coding
* 6.30 Wrap up & plan/prepare the coding of the next day
* 6.45 Blog/report progress
* 7.00 Breakfast, rest of the "normal" morning routine

I hope that by including this planning for the next day in here, I can get the motivation going and make it easy to get started the next day, since the strategy/goal for the next day should already be laid out.

## List of things I'd love to devote time to

* DSpace 7
  * Accessibility/WCAG compliance
  * End user test plans
  * i18n
* analyzer.atmire.com
  * upgrade dependencies to get rid of a few bugs
  * add stats to the homepage
* New volunteer project website
  * Setup from scratch
* Google Spreadsheet API development
  * Become a magician like my colleague Benoît Wéry
  
# Day 01 report

For the first day, I wanted to upgrade the crawler commons library in the analyzer.atmire.com project. Turns out the latest releases removed all of http fetcher to a [separate dependency](https://github.com/crawler-commons/http-fetcher) that is currently not available from maven central.

Instead of going with 0.10, I went with the latest one that still had these dependencies inside, v0.7 but I'm getting following error in there:

```
java.lang.NoClassDefFoundError: org/apache/http/conn/ssl/NoopHostnameVerifier
	crawlercommons.fetcher.http.SimpleHttpFetcher.createSSLConnectionSocketFactory(SimpleHttpFetcher.java:1065)
	crawlercommons.fetcher.http.SimpleHttpFetcher.init(SimpleHttpFetcher.java:982)
	crawlercommons.fetcher.http.SimpleHttpFetcher.request(SimpleHttpFetcher.java:533)
	crawlercommons.fetcher.http.SimpleHttpFetcher.get(SimpleHttpFetcher.java:529)
	crawlercommons.fetcher.BaseFetcher.get(BaseFetcher.java:84)
	crawlercommons.robots.RobotUtils.getRobotRules(RobotUtils.java:99)
```

# Day 02 Plan

Work on the error in v0.7 of crawler commons. If that doesn't work out, identify how http-fetcher could be used with v0.10
