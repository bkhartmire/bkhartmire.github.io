---
layout: post
title:      "CLI Data Gem: Lessons Learned"
date:       2017-12-07 07:41:19 +0000
permalink:  cli_data_gem_lessons_learned
---


Woo! First project complete! 

Eager to demonstrate to myself what I’ve learned so far, I approached the prospect of programming something without the guidance of lab instructions and pre-written tests with excitement. But ngl, there was some apprehension too. But growth and comfort aren’t meant to co-exist, right? 

My gem scrapes data from *The New York Times* website to return info about their current Best Sellers list. Here’s a basic breakdown of my initial program design:

1.	Program greets user and asks whether they’re interested in fiction or nonfiction
2.	The program returns a list of the titles and authors of the current top 5 best sellers from the user’s preferred genre
3.	Program asks user which book they’d like to learn more about
4.	Based on user input, program returns a summary of the book with a link to where it can be purchased on Amazon
I ended up achieving all this except for the purchase link (more on that later). 

Based on some of the major roadblocks I faced, here are the major lessons I’ve extracted from this project:

**Do not allow any language to intimidate you simply because it’s unfamiliar.**

My previous blog post goes into this in greater detail. There you can read all about how it took me hours to get my bin file working. (Go ahead and laugh at me, because I definitely did.)

**Be flexible and creative! There are probably several different ways to execute your design or a similar output.**

So you know how *The New York Times* is always thirsty for subscriptions? I cancelled my subscription a while ago, but still enjoy my a few free articles/month and email newsletter privileges. Well little did I know that every time I opened up their bestsellers list or even refreshed the page I was eating up one of my free articles of the month. Low and behold, one time when I had to reconnect to Wi-Fi and refresh the page to inspect its elements I was hit with a giant “YOU HAVE REACHED YOUR FREE ARTICLE LIMIT FOR THE MONTH” pop-up. (And there’s still three weeks left in December! *Weep.*)  Crap. Instead of caving into their marketing, I fished around for a different webpage on nytimes.com that included the information I needed but wasn’t technically classified as an ‘article.’ I had to redo all of my CSS selectors and refactor my scraper class, but that’s life.

**Ask for help.**

Struggling to solve a problem on your own is a valuable learning experience but it has diminishing returns. Sometimes you reach a point where asking for help is not only the most efficient route to a solution but also the most valuable. It’s okay. You’re not a cheater. That isn’t what this is about. Turns out that the Amazon purchase link I couldn’t figure out how to scrape wasn’t meant to be scraped using Nokogiri at all. The link I was attempting to scrape was within a dropdown menu was embedded with JavaScript. I didn’t realize this until it was explained to me by Learn instructor. 

Now that I’m looking at my refactored code, it doesn’t look too complicated at all. It certainly doesn’t look like anything that should’ve caused so many wrestling matches inside my brain. Everybody says this about coding but I’m appreciating its simple truth now more than ever: you learn by doing.

