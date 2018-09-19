---
layout: post
title:  "100 Days of Code Day 31 - Bash continued"
date:   2018-09-19 08:30:00
categories: 100DaysOfCode
---

# Bash auto update script

At the end of the session yesterday, the if statement that I had introduced in my bash update script was [not evaluating correctly](http://bram-atmire.github.io/100daysofcode/2018/09/18/100-days-of-code-day-30-bash.html).

When I was trying the if statement and the results, I mixed up the exit codes. 0 is true and 1 is false, not the other way around. The following did not work:

```bash
if [ "$reslog" = "*not up to date*" ]
``` 

But the new statement does:

```bash
if [ "$reslog" = "not up to date" ]
```

Apparently it doesn't make a difference if I use the string expand ${reslog} or not, they both work. As to why the star operator doesn't work: from what I could find, that * operator only works with the more modern double bracket test operator, which is not available on all shells. 

Related things I explored on this topic:
* [What is the difference between double and single square brackets in bash?](https://serverfault.com/questions/52034/what-is-the-difference-between-double-and-single-square-brackets-in-bash)
* [What is the difference between test, \[ and \[\[ ?](http://mywiki.wooledge.org/BashFAQ/031)
* [In bash, how can I check if a string begins with some value?](https://stackoverflow.com/questions/2172352/in-bash-how-can-i-check-if-a-string-begins-with-some-value)
* [https://stackoverflow.com/questions/5725296/difference-between-sh-and-bash](https://stackoverflow.com/questions/5725296/difference-between-sh-and-bash)

My first auto update was deployed!

# Shorthand for git add, git commit, git push to origin master

With these blog updates, as well as with code updates, the end always involves 3 different commands.
* Git add to stage the changed files
* Git commit to commit the change and add a commit message
* Git push, to push my local changes on master to the remote origin master

An exception here is larger work on a local feature branch, that I always first merge to master before pushing upstream.
I was wondering of the three can't be done in a single operation.

* [git add, commit and push commands in one?](https://stackoverflow.com/questions/19595067/git-add-commit-and-push-commands-in-one)
* [Adding a function() to .zshrc](https://stackoverflow.com/questions/44647789/adding-a-function-to-zshrc)

Adding this function to my .zshrc file doesn't seem to be entirely error free. In IDEA, it kills my terminal every time I type "git" now. Possibly due to some auto completing feature. But I'm also using oh-my-zsh, so maybe there's a conflict in there as well. Will continue this tomorrow. In the non-IDEA terminal I've also seen crashes that I can't explain right now. Wonder if there's a log that can tell me more about these kinds of crashes.

# Day 32 Plan

* Fix my short hand alias for git add, git commit and git push origin master on zsh/oh-my-zsh.

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


