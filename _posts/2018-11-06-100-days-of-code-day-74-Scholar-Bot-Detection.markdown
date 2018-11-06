---
layout: post
title:  "100 Days of Code Day 74 - Scholar Bot Detection"
date:   2018-11-06 07:00:00
categories: 100DaysOfCode
---

# Google thinks analyzer.atmire.com is a robot

A first glance at the additional logging I implemented yesterday revealed that Google Scholar is currently showing a captcha to my server so it can prove it is not a robot.

The code is exactly the same as what I'm running locally, so I would assume that it's not the code itself that sets off these triggers, but maybe rather the volume of requests, the frequency or perhaps the IP it's coming from.

# Tunneling to click the captcha

The first thing I'm trying to do is to route a few page requests to google scholar over the server, to my own machine, so I can click the captcha and maybe as a one-off, get past this.

[How to Use SSH Tunneling to Access Restricted Servers and Browse Securely](https://www.howtogeek.com/168145/how-to-use-ssh-tunneling/) led me to the instructions for Dynamic port forwarding, enabling me to send all my browser traffic through my server.

Clicking around a few times on Google Scholar did not show me the captcha, so I wasn't able to click it. Maybe because my browser also has Javascript enabled while the server has not.

# scholar.py experiences

People using the scholar.py script have been running into the same issue. [How to deal with "Please show you're not a robot"](https://github.com/ckreibich/scholar.py/issues/66) links out to three other issues where people have offered suggestions.

From the suggestions, I'm already collection and setting cookies by initially hitting the homepage before doing any queries.
I also already set a user agent.

# Changing the target url

My queries used to go out to http://scholar.google.com. When I'm making a few curl commands from the server, I get a redirect to https://scholar.google.com and another one from there to https://scholar.google.be. So just to ensure that these redirects are not the issue, I've updated the code to do all calls straight to https://scholar.google.be

# No luck so far

Whenever I try to lookup an item url, the server is still getting "Please show that you're not a robot".
If the current restrictions are IP bound, maybe there is a way how I could get the requests go out via other proxies so not all requests are arriving at Scholar from the same IP.

Otherwise, I just may have to accept that people will have to do their item verifications manually, instead of doing those for them.

# Day 74 Plan

Do a test to see if issuing the requests from other IPs could give different results.

After that, ask my colleagues for assistance to access the assets and hopefully get a successful test run in place for the language switch.

# Future days - DSpace 7 Angular

* Investigate writing of tests and write tests for the original language switch.
* Continue with implementing the actions and the reducer for the language switch.
* Continue implementation of the action to deactivate a language.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* UI for enabling/disabling particular languages
* Learn how to write tests and write them for the language functionality
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* Transition from plain CSS to SASS to make it prettier and learn about SASS at the same time
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whever something is committed to master.

# Future Days - Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

# Future days - Jekyll http://bram-atmire.github.io/ site

* Make it prettier

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.