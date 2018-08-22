---
layout: post
title:  "100 Days of Code Day 03 report"
date:   2018-08-22 06:14:00
categories: 100DaysOfCode
---

In sample webapps you find for Spring MVC, the first page your see is different from all other pages in the app, as it doesn't pull any data from your app. In a simple config, there is a welcome list, that directs you to index.jsp. That's what I was using so far for the [Atmire Analyzer](https://analyzer.atmire.com)

In order to pull some data to the front page, about number of repositories or items already indexed etc, I needed to change this in a proper controller, similar to all other pages are being served. Controllers are basically java classes where methods are annotated with the request path they are targeting.

So today I followed this [Stackoverflow Guide](https://stackoverflow.com/questions/5252065/spring-mvc-how-to-create-a-default-controller-for-index-page) to create a HomeController for the homepage. 

The suggested approach pretty much worked, except for the fact that there was nothing specifically in there about Spring Security. And I suddenly saw that I was promted to login in order to access the homepage. Not good. So in the end I "invested" (lost) most of today's time in figuring out that my Spring Web Security had to change from:

web.ignoring().antMatchers("/index.jsp");

to

web.ignoring().antMatchers("/index.htm");

Because previously, index.jsp was "hard coded" in that welcome list. But now, if you call analyzer.atmire.com/ "root", it immediately referred to index.htm.
  
# Day 04 Plan

Now that I have the controller in place, I want to see how I can get data in there:
- total number of repositories analysed
- total number of items analysed
- list of 5 last analysed repositories
- list of 5 last analysed items

All my other controller are currently centered around one "object", either one specific repository, an item, or the list of repositories. The challenge here is that I want BOTH a few repositories, as well as items.