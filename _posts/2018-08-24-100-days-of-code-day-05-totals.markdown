---
layout: post
title:  "100 Days of Code Day 05 report"
date:   2018-08-24 06:50:00
categories: 100DaysOfCode
---

Stackoverflow provided to be the unbeatable resource for today's challenges again. I have a very limited understanding of Spring MVC's "ModelAndView" concept. For now, I had just been using it to return a single object, and have my views (pages) retrieve values from that object type. Since yesterday, I was already returning a very limited list of repositories to the homepage view, so I needed to find a way to return multiple, different objects, as I want to list the total number of items and total number of repositories.

[Can i return two models in ModelAndView in Spring MVC](https://stackoverflow.com/questions/5068892/can-i-return-two-models-in-modelandview-in-spring-mvc) was exactly what I needed. Now I have a more generic model, where I can just add any Java object, and the JSPs are magically able to retrieve values from them without any type of casting. Blew my mind that it "just works".

Once I had the number, I needed a way to format the thousands separator, and I learned about the JSTL fmt library. Again, the normal docs are way way way too dense. But an example based solution provided me exactly what I needed. [JSTL formatNumber for JSP custom pattern independent from language](https://stackoverflow.com/questions/16899343/jstl-formatnumber-for-jsp-custom-pattern-independent-from-language).

So there you have it, was able to ship again on day 5. Visit the [Analyzer Homepage](https://analyzer.atmire.com) to discover how many repositories, were already analysed with the tool and how many items they hold together.

The amazing high number of the item count brings me to the next challenge: improving my duplicate detection and avoidance for entries in the list. Many institutions have huge challenges to keep their repository URLs consistent. A few flavors of the problem

* http vs https links
* academic domains of repositories changing (kuleuven.ac.be to kuleuven.be) for example
* institutions deliberately keeping different urls alive for persistence purposes instead of working with proper HTTP redirects
* IP based links being exposed, as well as the properly named hosts
* Institutions running multiple DSpace repositories, so you can't assume that you can only have one valid repository per domain

Luckily I have a bag of tricks, for example comparing the item count, the country of origin for a repository etc. Still, I have SOME duplicates left in the list, explaining the high item count.

  
# Day 06 Plan

Work on duplicates

# Future days

* CSS Bonanza: Change styling to true Atmire style.
* Add recently verified items to the homepage.
* Optimize my hideous methods for getItemcount and getRepoCount.

# Sustainability

Five days in, I feel like I will seriously have to raise the stakes if I want to make it until 100 days.
[The original medium post](https://medium.freecodecamp.org/join-the-100daysofcode-556ddb4579e4) recommends that you only miss at max one day every two weeks. It also emphasizes the importance of not missing 2 days in a row. Yikes!

In terms of positive reinforcement, I'm thinking of getting myself a Really Big Present if I can last until 100 days.

In terms of more negative reinforcement, one option would be to donate an amount of money to charity every time I miss a day.

After seeing one of my colleagues take a nap on the sofa yesterday afternoon, it hit me that I could also use that, since afternoons are pretty challenging right now. So instead of having the sofa in our common kitchen, me and her moved the sofa to one of our meeting rooms to support short post-lunch corporate naps. [The science is with us on this one as well](https://sleepfoundation.org/sleep-topics/napping).


