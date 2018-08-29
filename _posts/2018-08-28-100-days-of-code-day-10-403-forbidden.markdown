---
layout: post
title:  "100 Days of Code Day 10 report - 403 Forbidden"
date:   2018-08-29 06:49:00
categories: 100DaysOfCode
---

# 403 Forbidden

Yesterday's [increase of the timeout](http://bram-atmire.github.io/100daysofcode/2018/08/28/100-days-of-code-day-09-favicon-timeout.html) from 5000ms to 10000ms managed to get a few repositories in the list updated, but not as much as I had hoped.  

Today I'm investigating why repositories like [CAS IR GRID](http://www.irgrid.ac.cn/) are returning HTTP 403 (forbidden) requests instead of a normal 200 OK response. 

Because they are [generally faster than a GET request for an entire page](https://stackoverflow.com/questions/16539269/http-head-vs-get-performance), one of the first checks to see if a repository is alive, is to do a HEAD request that only gives me the headers.

[HEAD request receives “403 forbidden” while GET “200 ok”?](https://stackoverflow.com/questions/3454286/head-request-receives-403-forbidden-while-get-200-ok) indicates that this could be a wider problem with web server configuration on the side of the repository.

To exclude that I'm getting rejected on the basis of the user agent (DSpace Site Checker) that I'm using, I tried to change it into a browser-like user agent "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.106 Safari/537.36". It made no difference.

Maybe there was still something weird about the HEAD requests being issued by my HttpClient, so wanted to check if I could do a few with curl from the command line to see if that worked.

[Difference between curl -I and curl -X HEAD](https://serverfault.com/questions/140149/difference-between-curl-i-and-curl-x-head)

Same story for curl:

```
» curl -I http://www.irgrid.ac.cn/
HTTP/1.1 403 Forbidden
Server: Apache-Coyote/1.1
Cache-Control: private
Expires: Thu, 01 Jan 1970 08:00:00 CST
Content-Type: text/html;charset=utf-8
Content-Language: en
Content-Length: 1100
Date: Wed, 29 Aug 2018 04:25:28 GMT
```

So at this point I am pretty convinced that it's webserver config related on the repository side and that I can't really do much about it. EXCEPT for providing better error feedback on my failure page. That failure page is currently generic, with a single message of potential failures, but I can see the value in extending it so it has more meaningful error messages.

# Day 11 Plan

Better logging of updates and more meaningful error messages on the [Analyzer](https://analyzer.atmire.com) failure page.

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
