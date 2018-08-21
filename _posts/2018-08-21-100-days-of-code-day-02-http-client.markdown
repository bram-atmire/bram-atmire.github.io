---
layout: post
title:  "100 Days of Code Day 02 report"
date:   2018-08-21 06:44:00
categories: 100DaysOfCode
---

# 100 Days of Code - Day 02 Report

Working according to the plan, I found out that bumping the crawler commons version created a maven dependency conflict between the version of httpclient that was loaded by crawler commons and the 4.3.3 version I had pinned down in the project.

I used the diagram > Maven dependency viewer in IntelliJ IDEA for the first time. Most lines in there were blue, but some of them were red.
These meant conflicting or unsatisfied dependencies according to https://www.jetbrains.com/help/idea/2016.3/working-with-maven-dependencies.html

Clicking on one particular dependency reveals which version is being used where. I decided dropping my own pinned down version, as it turned out that crawlercommons was already providing a newer one.

In this piece on Stackoverflow: https://stackoverflow.com/questions/32447650/how-to-maven-dependency-hierarchy-in-intellij there was also some praise for this particular Maven Helper plugin: https://plugins.jetbrains.com/plugin/7179-maven-helper but I didn't have to use it yet.

Since I had a little bit of time left, I also took care of a few http font inclusion references that were causing mixed content (security) warnings on the homepage of the app, by switching them over to https.

So now on Day 02, feeling good for shipping my first fix.

After deploying, I was able to use the analyzer on a repository that was blocked because of crawler-commons SSL related problems that were now fixed, https://kb.osu.edu.

When running through DSpace item analysis for this tool, I found a particular case that I want to revisit at a later point in time: https://analyzer.atmire.com/item/get.htm?itemID=3080

This item DOES have its bitstream successfully indexed in Google Scholar, but Scholar is not linking a reference to the DSpace item metadata page. Would be interesting to see if there is a pattern and what can be done to resolve it.
  
# Day 03 Plan

For day 3 I would like to start working on adding some stats to the Analyzer frontpage:
- total number of repositories analysed
- total number of items analysed
- list of 5 last analysed repositories
- list of 5 last analysed items

Likely, this will be a multi day job, because I might need to change the welcome list approach to a proper controller. The Analyzer tool is a Spring Web MVC app.
