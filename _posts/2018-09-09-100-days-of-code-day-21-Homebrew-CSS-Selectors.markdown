---
layout: post
title:  "100 Days of Code Day 20 report - Homebrew CSS Selectors"
date:   2018-09-09 10:47:00
categories: 100DaysOfCode
---

# Sublime text alias and homebrew broken

Lost some time today after I wanted to merge my fix for the header font

» git merge issue-39 
subl -n -w: subl: command not found
error: There was a problem with the editor 'subl -n -w'.
Not committing merge; use 'git commit' to complete the merge.

The alias I had set for Sublime Text ("subl"), didn't seem to work anymore.
I thought I had installed with the homebrew cask install but I can't find any trace of that install. [Homebrew](https://brew.sh/) is a package manager for Mac OS X. Within the whole Homebrew ecosystem, [Homebrew Cask](https://github.com/Homebrew/homebrew-cask) goes beyond the installation of CLI packages, but also takes care of nicely installing bigger entire Mac OS X Applications automatically, like in my case, the Sublime Text editor.

Normally, I try to install *everything* with Homebrew cask, because, as is now the case, I run into trouble wondering if I installed something manually or through cask.

And when running "brew cask list", instead of getting the list of installed casks, it's now suddenly complaining about my java7 cask with

```
Error: Cask 'java7' is unreadable: undefined method `undent' for #<String:0x00000001032f89c0>
```

Found out it was not my fault and applied the current one liner solution [that gets suggested here](https://github.com/Homebrew/homebrew-cask/issues/49716).

Noticed that the cask sublime-text3 is no longer maintained, and that it's now just called sublime-text. Uninstalled the old sublime-text3 cask and installed the new, generic one.

I failed to uninstall the sublime-text3 cask, but it seems like my new installation of the sublime-text cask next to it just works and also fixed the alias for 'subl'.

In case I ever want to fix it further, here are the errors I got during uninstalling/zapping:

```
» brew cask uninstall sublime-text3
==> Uninstalling Cask sublime-text3
==> Running uninstall process for sublime-text3; your password may be necessary
==> Quitting application ID com.sublimetext.3
Error: It seems there is already an App at '/usr/local/Caskroom/sublime-text3/3103/Sublime Text.app'.
 ✘ bram@Sugarsmooth  ~ 
» brew cask zap sublime-text3
==> Implied "brew cask uninstall sublime-text3"
==> Running uninstall process for sublime-text3; your password may be necessary
==> Quitting application ID com.sublimetext.3
Error: It seems there is already an App at '/usr/local/Caskroom/sublime-text3/3103/Sublime Text.app'.
```

# CSS Fix one: make navbar white blue, and then fade to white
Where I was stuck yesterday:

```CSS
.navbar-custom a {
  color: #005989;
}
.navbar-custom.top-nav-collapse-font a {
  color: white;
}
```

Fix I ended up implementing that worked, by sheer trial and error and not by really understanding (yet) how the overrides really work & what takes preference over what. Deployed!

```CSS
.navbar-custom a {
  color: #005989;
}
a.top-nav-collapse-font {
  color: white;
}
```

# Day 21 Plan

* CSS: Down button at "basic principles" colour change
* CSS: revisit contrast for sections that are entirely white in background
* Investigate empty rows with TODO message showing up in the list of recently scanned repos

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* CSS: Down button at "basic principles" colour change
* CSS: revisit contrast for sections that are entirely white in background
* Investigate empty rows with TODO message showing up in the list of recently scanned repos

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

In September, these are already days that will be very tough:
* Sep 8,9 - FoM Lanparty w friends
* Sep 14,15,16,17 - Abroad for a wedding
* Sep 27,28 - Supernova conference Antwerp

So that's already a lot of exposure to potentially missed days. 

I will raise the stakes this way and gather money for Charity:Water. Let me know if you want to sponsor me and for how much per completed day in September. September 1st is the first successfully completed day.

# September tracking

Will only log the failed days here. No failed days so far.

# Thanks to the following sponsors!

1. Jan & Hilde: €2 per successful day (Yes, these are my parents)


