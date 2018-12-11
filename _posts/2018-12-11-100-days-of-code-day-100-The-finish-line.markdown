---
layout: post
title:  "100 Days of Code Day 100 - The finish line"
date:   2018-12-11 07:00:00
categories: 100DaysOfCode
---

# Installing utteranc.es for comments on the blog

My colleague [PhilipVis](https://github.com/PhilipVis) pointed me to utteranc.es, a commenting system based on Github issues. 
Installing it on this site was a pretty flawless proces, kudos to [jdanyow](https://github.com/jdanyow).

# How it all started

Why did I even start this in the first place ? [Day 01](http://bram-atmire.github.io/crawler-commons/2018/08/20/100-days-of-code-day-01-crawler-commons.html) takes me back. This attempt was not planned, I didn't spend much time thinking about it before I committed.

I basically committed to this when I was on an impulsive, positive high. Can't remember where I read this particular advice or quote, but going along with small sparks of motivation and nurturing them into a bigger fire has worked well for me. As I value control a lot, avoiding the word control-freak, I tend to kill a lot of these sparks by overthinking them.

>> "Studies have shown that the most successful people make decisions rapidly because they are clear on their values and what they really want for their lives. The same studies show that they are slow to change their decisions, if at all. On the other hand, people who fail usually make decisions slowly and change their minds quickly, always bouncing back and forth. Just decide!"
>> — Anthony Robbins, Awaken the Giant Within, p. 49

# Learning and imposter syndrome

One of my hopes was that by committing to a daily practice, I would become a "better" or even maybe a "real" developer. 
During many of these past 100 days, I got stuck and felt like an idiot. Often it was only due to assistance of my colleagues that 
I got "unstuck". Why does this take me several hours, when someone else just glances at this for 10 seconds and helps me right away?

Questions that popped up several times along the way:
* Do I have enough patience for this?
* Am I intelligent enough?
* Others must be better at this
* Who am I kidding and what am I trying to prove here?

Reading tweets of other people on #100DaysOfCode was a great way of realising, day after day, that I'm not alone in this.
Everyone is different here and there is no defined "optimum" to strive for. The meme by [gbroussard](https://imgur.com/gallery/dzbQCj4) captures this perfectly for me:

![gbroussard Two States of Every Programmer](../../../../assets/img/2018-12-11-gbroussard-two-states.png)

Especially when looking at contributions to the DSpace project, I just find solace in the idea that: If I take a stab at some problem that is not fully addressed right now, even if I don't solve it entirely myself, if I do this in the open I might help or inspire others to address it together with me. Even if I fail, and if I document my failures as well as my successes, I can help my future self to avoid making the same mistakes, and might even prevent others from being stuck or making similar mistakes.

But it never ends. There will be always more to learn and I will never "feel" like a pro. And that's probably alright. Better to take the humble attitude of a newbie, than an obnoxious know it all. Because you never know it all and there is always an opportunity to learn from others.

# So what's next?

Honestly, I don't know yet.

## I want to stop

1. Feeling guilty for missing a day, obsessing over when I will get my hour of code in if I don't do it in the early morning

## I want to continue

1. contributing to DSpace 7 in one shape or form
2. maintaining the [Analyzer](https://analyzer.atmire.com) and build new features for it
3. taking 30 minute naps after lunch at work, even if I stop getting up at 5.30

## Frequency & habit?

I'm a big believer in frequency and routines. The daily commitment and routine of #100DaysOfCode is so simple, straightforward
and powerful. Once you found a daily slot that you want to commit to, the planning itself requires no thinking, only execution.

But daily, weekday and weekend, just FEELS like too much right now. I feel like I want to get a few hours in every week, and wonder how much I exactly need to get to a dose that keeps me from getting rusty but at the same time, is maybe healthier.

## Conflicts

In September, I enrolled in Polish classes for which exams are coming up and the speed and level of difficulty of the classes are steadily increasing. I need to find a way to commit more time to this.

## Plan

Before the start of 2019, I want to get my head straight on how I'm going to tackle this in 2019. Until then, not sure how much or little I will do in the meantime.

## One more thing

I'm getting myself a big present, more on this once I pull the trigger.

# TODO

## DSpace 7 Angular

* Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.
* UI for enabling/disabling particular languages
    * Continue with implementing the actions and the reducer for the language switch.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

## Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* Transition from plain CSS to SASS to make it prettier and learn about SASS at the same time
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whenever something is committed to master.
* Add documentation to the methods of the item controller
* Change the back button on the item page with a real link back to the repository analysis, instead of the current history -1 hack.
* Create a new item test to check if the publication date is correct, or has a high chance of being wrong

## Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

## Jekyll http://bram-atmire.github.io/ site

* Make it prettier

## Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.
Look into web.dev from google for this (thank you Philip)

## Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)