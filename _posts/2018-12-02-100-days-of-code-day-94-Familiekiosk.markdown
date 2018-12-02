---
layout: post
title:  "100 Days of Code Day 94 - Familiekiosk"
date:   2018-12-02 20:00:00
categories: 100DaysOfCode
---

# Familiekiosk project

A week ago, my dad launched the idea to build the [FamilieKiosk](https://github.com/TeamScheire/familiekiosk) appliance and software for my grandparents for Christmas.

In case you don't live in Flanders or haven't seen the [Team Scheire TV episode about FamilieKiosk](https://www.vrt.be/vrtnu/a-z/team-scheire/1/team-scheire-s1a3/), it is basically a way to keep elderly family members in touch with other members of the family.

The way how FamilieKiosk does that, is by making family pictures available on the TV of the older family member. There was brilliance in the UX insight here: phones, tablets and apps are often too difficult for our grandparents. HOWEVER, the TV remote has been part of their life for a long time. Hell, these people even got used to TeleText back in the days.

FamilieKiosk is powered by a Raspberry Pi, that streams the pictures to the TV. It is connected to a custom made connector, with three simple buttons: next picture, previous picture and like.

To send new pictures in, family members can log into [Telegram](https://www.telegram.org), a message platform inspired by ideals of individual freedom and data privacy. Apparently it has a very elegant API that allows the creation of custom bots.

The bot that we created as part of the setup, listens in on a channel in Telegram, and sends pictures off to the Raspberri Pi, connected to the older family member's TV.

# Learning summaries

* Linux services and [Systemctl](https://www.linode.com/docs/quick-answers/linux-essentials/introduction-to-systemctl/)
* [Raspberri Pi installation](https://www.raspberrypi.org/learning/hardware-guide/) and [Etcher](https://www.balena.io/etcher/) for flashing
* [OMX Player](https://elinux.org/Omxplayer)
* [Telegram Bot API](https://core.telegram.org/bots)

# Telenet Homespot

My grandmother doesn't have her own internet connect. But people in her block have Telenet and the Raspberri Pi has Wifi. So we can use our subscriptions, and use the "Telenet Homespot" to connect her.
Right now, it seems like the login details of Telenet Homespot are being stored, but I wonder how long this "session" is retained and whether it will prompt my grandmother at some point to login again, which would be annoying.

Thinking about FamilieKiosk and Telenet more, I think it would be a killer app for ISPs to build an app like this into their digicorders. If they succeed at keeping the simplicity, this would create added value for elderly and might help them to sell more internet connections.

This would remove the need for separate hardware (raspberri pi + custom controller), because the digibox/set top box is already there and comes with a remote ... 

# Done and TODO

Prior to today, my dad had ordered the parts. We basically put together the whole thing, hardware and software, in a couple of hours. The thing that remains is to deploy/install in my grandmother's home.

But this is for after Christmas since she will get this as Christmas gift.

# Day 95 Plan

Back to DSpace 7 languages.
Continue with the Czech and English po files.
Investigate why some message keys were missing from the automated extraction.

# Future days - DSpace 7 Angular

* Explore if there's any opportunity to extend documentation or tests in other parts of the DSpace Angular code.
* UI for enabling/disabling particular languages
    * Continue with implementing the actions and the reducer for the language switch.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

# Future days - Analyzer.atmire.com work

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

# Future Days - Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

# Future days - Jekyll http://bram-atmire.github.io/ site

* Make it prettier

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.