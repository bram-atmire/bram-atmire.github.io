---
layout: post
title:  "100 Days of Code Day 20 report - CSS fixes"
date:   2018-09-08 09:39:00
categories: 100DaysOfCode
---

# CSS Fix one: make navbar white blue, and then fade to white

My colleague Yana pointed out that the contrast between the navbar and the background is not high enough, making the nav bar hard to read. The theme has a feature that fades the background colour of the navbar to dark blue, while keeping the font the same. 

I tried to learn how that fading works, and if I can apply the same to the font, making it fade from blue to white. 

Two things are happening: 
* The nav element gets an extra class, top-nav-collapse, where I see the blue colour of the final background appear.
* the navbar-custom class is using [CSS Transition](https://www.w3schools.com/css/css3_transitions.asp)

```CSS
  .navbar-custom {
    padding: 20px 0;
    border-bottom: none;
    letter-spacing: 1px;
    background: transparent;
    -webkit-transition: background 0.5s ease-in-out, padding 0.5s ease-in-out;
    -moz-transition: background 0.5s ease-in-out, padding 0.5s ease-in-out;
    transition: background 0.5s ease-in-out, padding 0.5s ease-in-out;
  }
  .navbar-custom.top-nav-collapse {
    padding: 0;
    background: #005989;
    border-bottom: 1px solid rgba(255, 255, 255, 0.3);
  }
```

When I deactivate the transitions, the background colour changes is sudden, so it has nothing to do with the adding of the extra class element.

The adding of the extra class element happens in a custom piece of javascript that calls on jquery.

```javascript
$(window).scroll(function() {
    if ($(".navbar").offset().top > 50) {
        $(".navbar-fixed-top").addClass("top-nav-collapse");
    } else {
        $(".navbar-fixed-top").removeClass("top-nav-collapse");
    }
});
```

I added a nav-transition class to the links I wanted to target, and an additional class that I want added and removed, top-nav-collapse font.

```javascript
$(window).scroll(function() {
    if ($(".navbar").offset().top > 50) {
        $(".navbar-fixed-top").addClass("top-nav-collapse");
        $(".nav-transition").addClass("top-nav-collapse-font");
    } else {
        $(".navbar-fixed-top").removeClass("top-nav-collapse");
        $(".nav-transition").removeClass("top-nav-collapse-font");
    }
});
```

So far so good: I can see in inspect element that the class gets added and removed where I want. However, I am currently not able yet to get the css selector right

```CSS
.navbar-custom a {
  color: #005989;
}
.navbar-custom.top-nav-collapse-font a {
  color: white;
}
```

Whatever I have tried so far, the .navbar-custom a rule seems all powerful and I'm not able to correctly tie the white color to links that have the top-nav-collapse-font class.

# Day 21 Plan

Fresh up my knowledge of css selectors by going through the fabulous [CSS Diner](https://flukeout.github.io/) again.

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* CSS: header font dark initially & fade to other colour when scrolling
* CSS: Down button at "basic principles" colour change
* CSS: revisit contrast for sections that are entirely white in background
* Investigate empty rows with TODO message showing up in the list of recently scanned repos

# Future Days - other ideas

1. Switch to a different project: start working on DSpace 7 Angular
2. Setup IDEA so I can start editing these blogposts from there, instead of in a text editor
3. Developer productivity: Get my IntelliJ IDEA Shortcuts in order (CMD+1, CMD+/, ...)

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

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


