---
layout: post
title:  "100 Days of Code Day 09 report - Favicon and Timeout"
date:   2018-08-28 06:59:00
categories: 100DaysOfCode
---

# Favicon

The Atmire.com site already had an updated favicon and the mission was just to copy it into the Analyzer project. Turns out the modern web doesn't need the archaic .ico extension anymore and that icons up to 32x32 pixels are supported, in PNG. If you're interested, more information is available on [Favicon dimensions?](https://stackoverflow.com/questions/2268204/favicon-dimensions)

# Timeout

I already had three different timeout configurations in place in my HttpClient configuration, used to send out requests to analysed respositories, all set to 5000ms. 

The differences between ConnectionRequestTimeout, ConnectTimeout and SocketTimeout are beautifully explained here: [why setConnectionRequestTimeout doesn't stop my 1 min get request?](https://stackoverflow.com/questions/31611861/why-setconnectionrequesttimeout-doesnt-stop-my-1-min-get-request)

I decided to:
* Increase ConnectionRequestTimeout to 20000, because waiting for local connections to become available has nothing to do with the remote repositories and might come in handy in case the Analyzer would ever get really popular
* The ConnectTimeout seems to be the key one, the general time it takes for a server to respond and setup the connection. Going with 10000 as an experiment.
* I'm not sure at this point if it makes any sense to keep Socket Timeout, for speed between different packages, any shorter than the original connection timeout. If I find and want to scan a repository that is slower, I should also allow it to send its packages slower. So going with 10000 for that as well for now.

Unfortunately, I got confronted with failure as these changes still haven't enabled me to get updates for one of the major Chinese DSpace repositories, [CAS IR GRID](http://www.irgrid.ac.cn/)

Today's time only allowed for a little bit of debugging, but it currently seems that this repository is returning a 403 Forbidden response, so it has nothing to do with timeouts and I'm currently doing a poor job at properly logging these kinds of responses.

# Day 10 Plan

Investigate the case of [CAS IR GRID](http://www.irgrid.ac.cn/) and see if there's anything we can do in terms of logging and working around the 403 forbidden responses.

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
4. My commitment is fully volunatirly: if I want to change the rules or back out, I can at any time

Thinking further about September, these are already days that will be very tough:
* Sep 8,9 - FoM Lanparty w friends
* Sep 14,15,16,17 - Abroad for a wedding
* Sep 27,28 - Supernova conference Antwerp

So that's already a lot of exposure to potentially missed days. Not sure if raising the stakes this way will be productive or not.
