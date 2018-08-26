---
layout: post
title:  "100 Days of Code Day 07 report"
date:   2018-08-26 17:16:00
categories: 100DaysOfCode
---

# Git: delete merged branches with confidence 

Very small thing I had to use today, that I had looked up in the past: version-control wise, I have been using Atmire's Gitlab server for this project. Every time I want to create a solution for a particular problems, I create an issue in my Gitlab project, and use the number of that issue as the name of my branch.

After I consider something ready for deployment to prod (https://analyzer.atmire.com), I merge my branch locally with master, and push my master branch upstream to the Atmire Gitlab server. So my issue-fix branches actually never go to the server.

So after a while, I'm now sitting here with a bunch of local branches, of which most of them have been merged, pushed upstream ad deployed.

[This stackoverflow post](https://stackoverflow.com/questions/6127328/how-can-i-delete-all-git-branches-which-have-been-merged) has a super handy command for deleting branches that have already been merged into master, with peace of mind.

In my [post from yesterday](http://bram-atmire.github.io/100daysofcode/2018/08/25/100-days-of-code-day-06-duplicates.html) I mentioned the challenges around duplicates.

# Back to dealing with duplicates

The basic duplicate qualification algorithm I use is checking:
* if the item count of the repository is the same
* if they are based in the same country

Aside from this, I also test if the URL already appears in a similar form. HTTP vs HTTPs etc.

Since I wasn't entirely finished, I'm now iterating over the stated problem cases to confirm if I totally got them now:

## SOLVED: Problem case 1: Partially different hostnames, still same repo

http://theses.ucalgary.ca/  
http://prism.ucalgary.ca/   

http://theses.ucalgary.ca/ actually redirects to https://prism.ucalgary.ca/handle/1880/100029. Because I now also check on partial url matches of what's already in the DB, AFTER following the redirect, this was solved.

http://research.wsulibs.wsu.edu/xmlui/  
https://research.libraries.wsu.edu/xmlui/

This case is also addressed, because I now regard items from the same country, with the same head title and the same item count, as identical, regardless of their URLs.

## SOLVED: Problem case 2: item counts need to be up to date all the time

If I want to do any useful item count comparison, I have to make sure all item counts are up to date all the time. Currently, the list of repositories doesn't automatically update itself, so I have to look into making some kind of scheduled task that runs the update every night for all repositories in the list.

Solution: every time when I compare against a potential duplicate candidate, I make sure that potential duplicate candidate is updated as well.

## SOLVED: Problem case 3: Domain names that partially overlap

https://www.openstarts.units.it/    
http://www.openstarts.units.it/dspace/  

Pretty obvious that this is the same repository, but it slipped through the initial domain detection because of the extra subdomain. This can be fixed by first getting the item count, and only then rejecting it as a duplicate if the item counts match.

Another variation of the same, institutions running both JSPUI and XMLUI webapps, the two different user interfaces of DSpace:

http://dspace.sctimst.ac.in/xmlui/  
http://dspace.sctimst.ac.in/jspui/  

==> Both of these are now solved as well

## SOLVED: Problem case 4: Completely different TLD, same repository

https://beardocs.baylor.edu/xmlui/
https://baylor-ir.tdl.org/baylor-ir/

Here it's getting harder for being really sure we don't exclude false negatives. If a repository is in the same country and has the same item count, it can HAPPEN that they are genuinly different repositories. 

If they both point to the homepage and not to a specific collection name, they should have the same page title. So there, I could do a check if these urls serve the homepage & if they have the same name.

==> Solved by implementing this strategy
  
# Day 08 Plan

Try to find an automated way to cleanup "dead" repositories that are no longer online. How long after not being able to reach a repository should I delete it from the list? Are there still repos that ARE alive but that I can't properly update because of the ways they are configured or customized?

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




