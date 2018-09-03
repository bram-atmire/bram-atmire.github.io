---
layout: post
title:  "100 Days of Code Day 15 report - CSS Analyzer styling"
date:   2018-09-03 06:55:00
categories: 100DaysOfCode
---

# CSS overhaul for analyzer.atmire.com

After days of being deep in the error detection and handling bowels of the software, it's nice to work on something that is really visible: the look and feel of the application. For my styling overhaul of the site, my goals initial goals are:

1. Introduce the Atmire logo
2. Introduce white backgrounds instead of black
3. Introduce Fira Sans as the font, the official Atmire font

Everything that is now readable should remain readable. Inspect element/source rendering verification of the page should not introduce any new errors that weren't there before (missing files, http links to files etc).

In a second stage, I'd be interested in upgrading to a newer version of the underlying [Bootstrap theme](https://getbootstrap.com/), as well as doublecheck if the site still renders somewhat on mobile devices.
 
# History

The underlying base of the CSS theme was the Bootstrap "Cover" demonstrator theme for Bootstrap 3.1.1. [See here for the 4.1 version](https://getbootstrap.com/docs/4.1/examples/cover/) and the free "Grayscale" theme by StartBootstrap. These are very handy and ensure that I didn't have to reinvent the wheel, but left me with a lot of modifications and things I don't really use, so it's not that clean.

# Developing and debugging CSS

Compared to Java, the nice thing with developing & debugging CSS on an existing application is that you can do most it straight in the devtools of your browser, without waiting for recompilation etc.

# IntelliJ IDEA complaining about missing files

When looking at the sections of the HEAD where CSS gets imported, I often see "false negative" warnings, where IDEA complains that certain files are missing.

[Cannot resolve file warning 
](https://intellij-support.jetbrains.com/hc/en-us/community/posts/206368229-Cannot-resolve-file-warning) and marking the webapp directory as Resources Root was the first thing I tried and didn't work for JSP.

[IntelliJ IDEA resolving web paths in JSP](https://stackoverflow.com/questions/14878548/intellij-idea-resolving-web-paths-in-jsp) covers a different approach: setting up a "web facet" and adding a Web Resource Directory. Turns out everything like that was already configured

So in my index.jsp for example, IDEA complains that it can't finds the directory
```
<link href="css/bootstrap.min.css" rel="stylesheet">
```

When I change it to:
```
<link href="/css/bootstrap.min.css" rel="stylesheet">
```

It DOES find the directory, but issues another complaint, where absolute paths are not recommended in JSP. Even though this is how it is deployed right now, so it does work.

[JSP Absolute Paths](https://stackoverflow.com/questions/15759549/jsp-absolute-paths) finally got me to the right advice in my context.

```
<link href="<%=request.getContextPath() %>/css/bootstrap.min.css" rel="stylesheet">
```

This was what I needed and I already had it like that in some of my other jsp files :/ The benefit here is that if I ever deploy it somewhere different than straight under the root of the domain, it will still work.

# Font weight and letter spacing

For me it was surprising to (re-)discover that parameters like letter-spacing and font-weight give you a lot of control over the font. [See the CSS that is actually deployed](https://analyzer.atmire.com/css/grayscale.css)

Right now, all the titles I use everywhere in the application have the same kind of styling and that is something I need to get rid of, to make it work in specific contexts like the page of a repository, where the repository name/title can potentially become very long.

# Shipped it uglier than it was

Even though it's far from finished yet, still decided to ship the update to https://analyzer.atmire.com, so you can follow along the transformation.

# Day 16 Plan

Already inverted the white and black, but now I have to find new background imagery. Introduce separate styling for separate kinds of titles.

# Future days - Analyzer.atmire.com work

* Analyzer: Change CSS styling to true Atmire style.
* Analyzer: Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Analyzer: change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Analyzer: Add recently verified items to the homepage.
* Analyzer: Optimize my hideous methods for getItemcount and getRepoCount.
* Analyzer: re-test the check if we return the right repository to a user who tries to add a new one
* Analyzer: updating a repository: touch/change the base URL or not?
* Analyzer: batch ingest: switch to newer add repository methods.

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


