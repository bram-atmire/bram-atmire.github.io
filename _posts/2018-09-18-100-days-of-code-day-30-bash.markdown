---
layout: post
title:  "100 Days of Code Day 30 - Bash"
date:   2018-09-18 07:00:00
categories: 100DaysOfCode
---

# Bash auto update script

Continuing the [challenge from yesterday](http://bram-atmire.github.io/100daysofcode/2018/09/17/100-days-of-code-day-28-29-auto-deploy.html), I'm investigating why the script:

```bash
git fetch origin
reslog=$(git log HEAD..origin/master --oneline)
if [[ "${reslog}" != "" ]] ; then
```

Doesn't pick up on the available update. When executed manually in the src directory, it produces the following result:

```bash
dspacesitechecker@atmire3:~/src$ git log HEAD..origin/master --oneline
142b138 Adding Google Scholar reference to HEAD TITLE
```

Some of the things I learned included
* the square braces operator is the equal to the command test
* with $? you can get the result of the previous command

What finally worked to positively evaluate the string comparison statement was the following:

```bash
reslog=$([ "`git log --pretty=%H ...refs/heads/master^ | head -n 1`" = "`git ls-remote origin -h refs/heads/master |cut -f1`" ] && echo "up to date" || echo "not up to date")
if [ "$reslog" = "*not up to date*" ] ; then
```

Assuming that I had something going on with leading or trailing spaces.
I could also look into removing these leading or trailing spaces cfr [how do I trim leading and trailing whitespace from each line of some output?](https://unix.stackexchange.com/questions/102008/how-do-i-trim-leading-and-trailing-whitespace-from-each-line-of-some-output), but did not have the time to do this yet.

But frustratingly enough, the update script still doesn't evaluate and update correctly. To be continued tomorrow.

# Day 31 Plan

* Fix the execution of the update script.

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

# Future Days - other ideas

1. Switch to a different project: start working on DSpace 7 Angular
2. Setup IDEA so I can start editing these blogposts from there, instead of in a text editor
3. Developer productivity: Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)

# Future days - Jekyll http://bram-atmire.github.io/ site

* Make it prettier

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


