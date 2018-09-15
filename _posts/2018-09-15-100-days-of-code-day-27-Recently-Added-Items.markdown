---
layout: post
title:  "100 Days of Code Day 27 report - Recently Added items"
date:   2018-09-15 12:08:00
categories: 100DaysOfCode
---

# List of recently added items

When spinning the new code up for the first time, I ran into a runtime error that a hibernate property couldn't be found.

```
@Temporal(TemporalType.TIMESTAMP)
@Column(name= "last_modified")
private Date lastModified = new Date();
```

In my methods, I was calling last_modified, but apparently if you're calling hibernate properties, you just need to call the java class members. Changed to lastModified and we were in business.

# Background colour and opacity on panels

On the item detail page, the text wasn't clear in the information panels. I played around with the background colours. 

* [CSS RGB function - in 2018 supported by all browsers](https://stackoverflow.com/questions/5135019/css-opacity-only-to-background-color-not-the-text-on-it)
* [CSS RGBA function](https://www.w3schools.com/cssref/func_rgba.asp)
* [Coolors to the rescue for selecting the colour](https://coolors.co/63b3de-3e3e3e-f7f4ea-ded9e2-c0b9dd)

# CRON job on PROD server to check git master for changes and build automatically

Right now, every time I push a change to the master branch on the Atmire git server, I manually login to the PROD machine for the analyzer tool, to run a one line update script to deploy the latest code. That could be faster. I thought about two ways:

* Look into gitlab functionality & "hooks" to execucte the update script on the prod server at every commit on the master branch. The challenge there would be to give the gitserver the right authorizations to execute shell against the prod server
* Build a bash script and put it in the CRON scheduled jobs on the prod machine, poking git every five minutes or so to see if there are any changes, and if there are, to deploy them.

I was looking into the second option but no success so far. Found following related posts and started the creation of the bash script, but it's not successful yet.

[Check for changes on remote origin Git repository in shell script](https://www.christianengvall.se/check-for-changes-on-remote-origin-git-repository/) looks useful but for my purposes I'm wondering if there are any shorter solutions.

[How can I check in a Bash script if my local Git repository has changes?](https://stackoverflow.com/questions/5143795/how-can-i-check-in-a-bash-script-if-my-local-git-repository-has-changes)

[How to make a file (e.g. a .sh script) executable, so it can be run from terminal](https://askubuntu.com/questions/229589/how-to-make-a-file-e-g-a-sh-script-executable-so-it-can-be-run-from-termina)

# Day 28 Plan

* Find a method to detect for upstream changes on master.

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
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whever something is committed to master.

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


