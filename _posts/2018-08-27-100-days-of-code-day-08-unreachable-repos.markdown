---
layout: post
title:  "100 Days of Code Day 08 report - Unreachable repositories"
date:   2018-08-27 06:59:00
categories: 100DaysOfCode
---

# PKIX Path building failed - RESOLVED

A number of HTTPS based repositories currently can't be updated due to following error [Unable to Connect to SSL Services due to PKIX Path Building Failed](https://confluence.atlassian.com/kb/unable-to-connect-to-ssl-services-due-to-pkix-path-building-failed-779355358.html). I have been able to solve this previously by updating to a more recent version of java, cfr the hint all the way at the end of the article.

Again, this seems to be the cause, as my local java is newer than the server and is able to successfully process one of the repositories that is producing the PKIX Path building error on the server. Cause established, at least for SOME of the failures.

Because there are [quite a few distributions of JDK 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) it was not trivial to know which one to take. Looked at the java directories of the javas already installed on the server and found that the "release" file in the jdk directories reveals what version it exactly was. 

After putting the new java version in place, I hit permission errors and had to update execution permissions to following java binaries for it to work: 

* chmod a+x /usr/bin/java
* chmod a+x /usr/bin/javac
* chmod a+x /usr/bin/javaws

After this update, a number of repositories are updating correctly, unfortunately, not all of them. Here are a few for which the problem is still occuring and for which it needs to be investigated in more detail:

* http://repositorio.iaph.es/
* http://repositorio.ucp.pt/
* https://dspace.lu.lv/dspace/
* http://repositorio.sena.edu.co/
* https://scholarworks.unr.edu/
* http://repository.nauss.edu.sa/
* http://repository.unri.ac.id/xmlui/
* https://vtext.valdosta.edu/xmlui/

Mystery to me at this point why HTTP based links are producing the problem as well.

Also need and learned about following little grep tip, [to get preceeding or following lines](https://stackoverflow.com/questions/9081/grep-a-file-but-show-several-surrounding-lines).

# Day 08 Plan

I currently have a single timeout implemented, in which the repositories have to respond before they are marked as unresponsive. A number of repositories, including some from China, are effectively up but are not responding within the time. I will try to implemented an update mode with a longer timeout, and see if I have to go for a longer timeout across the board, or if I can put something in place that only applies it in very specific situations.

# Future days

* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)
* Change styling to true Atmire style.
* Switch to a different project: start working on DSpace 7 Angular

# Sustainability - Raising the stakes?

I'm strongly thinking about raising the stakes by
* giving an amount to charity for every day I miss
* asking people to sponsor me and to give an amount to a charity for each day I successfully complete

This way, every day would be a win. Still doubting about which rules I should put in place. For now, I'm thinking along the lines of:

1. I can anticipate or fix a lost day by doing an hour extra the day before, or an hour extra the day after. 
2. Goal is to have a steady frequency, so I can't just do 8h on a sunday to get myself off the hook for the next 7 days.
3. Sponsor commitments are fully voluntarily: any sponsor can back out at any time
4. My commitment is fully volunatirly: if I want to change the rules or back out, I can at any time

Thinking further about September, these are already days that will be very tough:
* Sep 8,9 - FoM Lanparty w friends
* Sep 14,15,16,17 - Abroad for a wedding
* Sep 27,28 - Supernova conference Antwerp

So that's already a lot of exposure to potentially missed days. Not sure if raising the stakes this way will be productive or not.
