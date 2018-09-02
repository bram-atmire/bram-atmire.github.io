---
layout: post
title:  "100 Days of Code Day 14 report - Add Repository refactoring"
date:   2018-09-02 20:30:00
categories: 100DaysOfCode
---

# Refactoring the add repository method

My void method to add a repository doesn't add a repository in every case. It starts with a valid URL but still doesn't add a repository if we can't find a valid browse-title page from where we can determine the item count.

I need to pull apart the searching/checking for a valid browse URL, and put those in inspector methods that preceed the invocation of "addRepo".

The case I completed to day is the one where the URL is not recognized as a DSpace because we can't find the browse-title page.

I shipped my latest results to https://analyzer.atmire.com. I'm done with robustness and error handling for a while: try to enter any DSpace or non DSpace url in there now, and see if you can still break it without getting a decent error message!

# Updating an existing repository in the list: automatically touch the base URL or not?

I'm wondering about my method to update a repository: this method updates all attributes of the repository EXCEPT for its baseURL. By not touching the base url, we play it safe, ensuring that we're not changing it into the baseURL of another repository that already exists in the list. But I've seen cases where the update routine fails, because the baseurl is now redirecting to something else. 

# Make sure we return the right, successful result to the user 

One challenge that I still have left here:

My check if adding a repository was successful still isn't good enough. At the end of the process of adding a repository, I fetch the last repository added to the list. If that repository is updated on the day the person executes the add operation, I return this repository. I used to have a method here that compared the URLs of the offered repository and the last added one, but I can not use that anymore because the matched URLs could be totally different (the https://baylor-ir.tdl.org/ vs http://beardocs.baylor.edu)

# Day 15 Plan

CSS overhaul for analyzer.atmire.com

Start getting rid of the custom, dark style of the site. Switch to white and to the official Atmire branding!

# Future days - Analyzer.atmire.com work

* Analyzer: Change CSS styling to true Atmire style.
* Analyzer: Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Analyzer: change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Analyzer: Add recently verified items to the homepage.
* Analyzer: Optimize my hideous methods for getItemcount and getRepoCount.
* Analyzer: re-test the check if we return the right repository to a user who tries to add a new one

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - other ideas

1. Switch to a different project: start working on DSpace 7 Angular
2. Setup IDEA so I can start editing these blogposts from there, instead of in a text editor
3. Developer productivity: Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)

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

