---
layout: post
title:  "100 Days of Code Day 28+29 report - Auto deploy"
date:   2018-09-17 21:10:00
categories: 100DaysOfCode
---

# Compensating for yesterday

After a streak of 26 days, the day after the sister of my girlfriend got married was the first one I missed. With the self imposed rules below, I'm compensating by doing 2 hours today instead of one. 

Toughest day so far, since we were in the car from 10pm yesterday until 3pm today: 11 hours of driving mixed with 4 hours of resting. The suitcases have been unpacked, the washing machine is running. As the dust has settled I'm venturing into ...

# CRON job on PROD server to check git master for changes and build automatically

I already started this on [day 27](http://bram-atmire.github.io/100daysofcode/2018/09/15/100-days-of-code-day-27-Recently-Added-Items.html) but wasn't successful so far.

Today I learned that you can [easily check the exit status of the most recent foregrond server command](https://www.cyberciti.biz/faq/shell-how-to-determine-the-exit-status-of-linux-and-unix-command/).

This gave me the most insights: [How to write a shell script that checks if git repository is up to date?](https://stackoverflow.com/questions/13736385/how-to-write-a-shell-script-that-checks-if-git-repository-is-up-to-date)

My current update script that I had to execute manually, originally written by my colleague Ben Bosman, always built and deployed the code, regardless on whether there were any changes on master. I now enhanced the start with:

```bash
git fetch origin
reslog=$(git log HEAD..origin/master --oneline)
if [[ "${reslog}" != "" ]] ; then
```
So that it becomes very light to run in cron.

Also found following way to execute the update script in a way that the timestamp gets added in front of every line of the output

[How to add a timestamp to bash script log?](https://serverfault.com/questions/310098/how-to-add-a-timestamp-to-bash-script-log)

```bash
$HOME/scripts/update.sh | while IFS= read -r line; do echo "$(date) $line"; done >>$HOME/scripts/updatelog
```

On to the last piece of the plan, adding this script execution to cron so that it executes every 5 minutes. Never configured cron myself but heard about it in the office very often, as it's a key component for [DSpace Scheduled Tasks](https://wiki.duraspace.org/display/DSDOC6x/Scheduled+Tasks+via+Cron)

Determining the right execution frequency is not trivial with cron configuration, but [crontab guru](https://crontab.guru/every-5-minutes) makes it easier.

The execution works, but the problem is that even despite the fact that the git fetch for updates is successful, the "${reslog}" != "" check is currently failing, as it's not picking up the updates. 

# Deploy bram-atmire.github.io site locally and upgrade

Managed to deploy the site locally, had to upgrade rvm, ruby and use the suggested answer on [Upgrade Jekyll and Dependencies](https://stackoverflow.com/questions/52344102/upgrading-jekyll-and-dependencies-for-github-pages). Wrote this new blogpost directl in IntelliJ IDEA and also pushed the updates to the gemfile and the gem lockfile.

# Day 30 Plan

* Investigate why the update script doesn't pick up on the available update.

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


