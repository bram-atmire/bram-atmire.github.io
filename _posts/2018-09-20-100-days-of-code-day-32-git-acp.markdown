---
layout: post
title:  "100 Days of Code Day 32 - Git add commit push"
date:   2018-09-20 07:00:00
categories: 100DaysOfCode
---

# Shorthand for git add, git commit, git push to origin master

I ran into weird terminal [crashes yesterday](http://bram-atmire.github.io/100daysofcode/2018/09/19/100-days-of-code-day-31-bash-continued.html) when trying to create a lazygit function in my .zshrc file that would perform a git add, commit and push.

To circumvent the problem, I'm trying another approach from the [git add, commit and push commands in one?](https://stackoverflow.com/questions/19595067/git-add-commit-and-push-commands-in-one) thread, the one where the alias is added in the gitconfig, and not in the shell config.

From what I can tell now, the following is working and has no side effects so far unlike yesterday's attempt.

```bash
[alias]
        acp = "!f() { git add -A && git commit -m \"$@\" && git push origin master; } ; f"
```

And I can now just do git acp "Day 32 post", to do all three at once.

# DSpace 7 and Angular

There's a lot of information out there on DSpace 7 and the Angular work. It feels daunting and I don't really know where to start.
Here's what I've looked at so far:

* [DSpace 7 code demonstrator](https://dspace7-demo.atmire.com/home)
* [DSpace 7 Angular UI Development](https://wiki.duraspace.org/display/DSPACE/DSpace+7+-+Angular+UI+Development) 

In the past I had already installed & deployed the DSpace 7 Angular UI project for the workshop at the Open Repositories 2018 conference.
While trying to spin this up again, it complained that my node version was out of date and that node 8 or newer was required.

I had node version manager (nvm) already installed before, but the alias seemed to be broken. Learned that brew installations of nvm are officially unsupported by the developers of nvm, so removed my brew installed version of nvm entirely. Had to manually add lines to .zshrc to get the nvm alias working there, but after that I was able to easily install and use the latest LTS version of node.

In the end, the yarn install successfully completed.

# Day 33 Plan

* Go through first steps of Atmire Angular training to develop a GDPR cookie consent popup for DSpace 7

# Future days - DSpace 7 Angular

* Translate of the standard messages keys in Dutch, to learn how i18n in Angular works
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* UI for enabling/disabling particular languages

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


