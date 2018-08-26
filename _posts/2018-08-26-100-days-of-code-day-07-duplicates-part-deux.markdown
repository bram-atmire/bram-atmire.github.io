---
layout: post
title:  "100 Days of Code Day 06 report"
date:   2018-08-25 11:00:00
categories: 100DaysOfCode
---

I try to use as many keyboard shortcuts as possible. An IntelliJ IDEA plugin that helps you to get trained in them is called Key Promoter X. Basically every time you repeatedly do something that can be done with a shortcut, it reminds you about the shortcut. Very.freaking.handy

But being on an AZERTY keyboard, I notice that powerful shortcuts to switch from the edit window CMD+1 (Project) to for example CMD+4 (RUN) window where you see the debugger, do not work.

[Stackoverflow](https://stackoverflow.com/questions/27922876/some-general-keymap-doesnt-work-anymore-intellij?rq=1) already pointed me in the right direction, showing me the "Find shortcut" feature of the keymap window.

Turns out that IDEA thinks that just pressing the 1 symbol (without shift), is &. Fair enough, that's right. But SHIFT + the same key, is recognized as SHIFT+1 and not as 1.

[IntelliJ IDEA Forum](https://intellij-support.jetbrains.com/hc/en-us/community/posts/205801639-Some-shortcuts-doesn-t-work-with-an-Azerty-keyboard-Ubuntu-) other people struggling with this.

[Force intellij to use a specific keyboard layout?](https://stackoverflow.com/questions/22450256/intellij-set-of-shortcuts-not-working)

I have already lost enough time with this, but I really want to avoid assigning custom shortcuts & diverging from the standard keymap. But I would really like the CMD+1, CMD+2, ... shortcuts, as well as the ones for comment blocks CMD+/. Will add as a challenge for the future.

CMD+ALT+back cursor, jump back to where you came from. Previously I was using Command+E to see recently added files, but this is faster. Found out that my plugin to learn shortcuts, Key Promoter, received a completely new rewrite, Key promoter X. Updated the plugin.

The basic duplicate qualification algorithm I use is checking:
- if the item count of the repository is the same
- if they are based in the same country

## Problem case 1: Partially different hostnames, still same repo

http://theses.ucalgary.ca/  
http://prism.ucalgary.ca/   

http://research.wsulibs.wsu.edu/xmlui/  
https://research.libraries.wsu.edu/xmlui/

To PREVENT this duplicate, I can't do an exact hostname match. But if the item count is the same, and the country is the same, I should do an additional, PARTIAL domain match to avoid it.

Checking on the repository titles here can be tricky, because JSPUI and XMLUI might expose a different title for the repository in the list.

## Problem case 2: item counts need to be up to date all the time

If I want to do any useful item count comparison, I have to make sure all item counts are up to date all the time. Currently, the list of repositories doesn't automatically update itself, so I have to look into making some kind of scheduled task that runs the update every night for all repositories in the list.

## Problem case 3: Domain names that partially overlap

https://www.openstarts.units.it/    
http://www.openstarts.units.it/dspace/  

Pretty obvious that this is the same repository, but it slipped through the initial domain detection because of the extra subdomain. This can be fixed by first getting the item count, and only then rejecting it as a duplicate if the item counts match.

Another variation of the same, institutions running both JSPUI and XMLUI webapps, the two different user interfaces of DSpace:

http://dspace.sctimst.ac.in/xmlui/  
http://dspace.sctimst.ac.in/jspui/  

## Problem case 4: Completely different TLD, same repository

https://beardocs.baylor.edu/xmlui/
https://baylor-ir.tdl.org/baylor-ir/

Here it's getting harder for being really sure we don't exclude false negatives. If a repository is in the same country and has the same item count, it can HAPPEN that they are genuinly different repositories. 

If they both point to the homepage and not to a specific collection name, they should have the same page title. So there, I could do a check if these urls serve the homepage & if they have the same name.
  
# Day 07 Plan

Do further testing and cleanup of duplicates.
Try to find an automated way to cleanup "dead" repositories that are no longer online.

# Future days

Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)
Change styling to true Atmire style.
Add recently verified items to the homepage.
Optimize my hideous methods for getItemcount and getRepoCount.

# Sustainability

I'm strongly thinking about raising the stakes by
* giving an amount to charity for every day I miss
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win.


