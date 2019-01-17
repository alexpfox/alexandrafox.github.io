---
layout: post
title: 'Metis Project 1'
categories: [project]
tags: [metis, statistics, data science]
---

A few months back I applied to [Metis](https://www.thisismetis.com/) - a Data Science and Machine Learning bootcamp -  on a bit of a whim. I'd been looking for a new path into the future for a while - one that wouldn't involve quite as much emotional labor as I'd been putting out (I spent the last 3.5 years as the primary support engineer for a small startup) and that would challenge me more intellectually. 

I taught myself just enough calculus, matrix math, statistics and python to take their acceptance exam (a full 48 hours long, plus a live interview!) and despite all odds, was accepted for their cohort starting January 7th. 

I've had my head down since, working on teaching myself enough to not flounder too badly when we started. Metis assigns 80+ hours of prework before you begin so that everyone is more or less on the same page when we start, though of course our backgrounds are varied. I'm now a week and a half in and so far so good! I have a ton of thoughts on how it feels being back in school after what would be considered a rough go of things nearly a decade ago, but those are for another post.

Metis' curriculum is largely project based, which is a large part of what drew me to the program (in addition to being fully accredited, focusing on developing Machine Learning skills [which was very literally a childhood dream of mine] and their extensive career support.) 

Our first week in class involved getting to know each other and our new workflow with a group project. The goals for the project were deliberately vague (though specifying our use of the dataset from MTA), allowing us to creatively interpret a prompt the class received in order to capitalize on MTA turnstile data from the last two years. We decided to assist a theoretical women-in-tech outreach group canvass NYC subway entrances to maximize outreach for an upcoming event of theirs held in July of this year.

<p align="center">
<img src="/assets/images/2019/1/benson.png">
</p>

During this project I rediscovered a deeply held love for building keynote presentations. I'm more than a little bit excited to share our insights (and memes) with you.

Before we sat down to dig into the data we found through [data.ny.gov](https://data.ny.gov/Transportation/Turnstile-Usage-Data-2017/v5y5-mwpb) we wanted to make sure we understood our problem and how to solve it:

<p align="center">
<img src="/assets/images/2019/1/MTA_presentation_2.png">
</p>

The most important takeaway here was that we needed to focus our efforts on an appropriate and relevant date period, on the people (women!) we wanted to bring into our event, and that we needed to optimize how and when we were engaging with our potential invitees. 

But how to do that?

<p align="center">
<img src="/assets/images/2019/1/MTA_presentation_3.png">
</p>

First things first - this data is nasty. Capital-N Naaaasty. Whitespace, negative counts, buffer overflows galore. Irregular readings? Of course. Missing readings? You betchya. So we spent [a ton of time](https://www.forbes.com/sites/gilpress/2016/03/23/data-preparation-most-time-consuming-least-enjoyable-data-science-task-survey-says/#facfcdb6f637) on fixing all of that and moved on with our lives. 

Next up: daily averages for the months preceding the event we're helping. This graph was an excellent exercise both in learning [seaborn](https://seaborn.pydata.org/) (a very popular graphing library used by most data scientists) and in figuring out where to focus our efforts further. Note that 23rd St Station here is actually a cumulative count of three unique stations with 23rd in the name - we had limited time to work on this project so we ignored this specific result in favor of those stations that were obviously larger "fish" we could fry.

<p align="center">
<img src="/assets/images/2019/1/top10_pipeline_edit.png">
</p>

We had our daily averages, but we needed to go deeper. Which days of the week were people riding the trains most often?

The answer to this is a bit obvious (commuting making up the bulk of ridership numbers) but it was worth proving out with the data.

<p align="center">
<img src="/assets/images/2019/1/weekly_ridership.png">
</p>

Look at that beautiful dropoff. Couldn't be clearer. Now - what *times* should we be at our posts, soliciting female tech workers to join us for our event?

<p align="center">
<img src="/assets/images/2019/1/weeklytop5.png">
</p>

This visualization showed us that there were some obvious peaks in ridership at our high-ridership stations during the morning and evening commutes, dependant on which stations you looked at. You can also tell I learned how to make backgrounds transparent with seaborn.

But what if we can go *even deeper*? How do we best target *women* in tech, not just tech workers OR women?

<p align="center">
<img src="/assets/images/2019/1/map-cropped.png">
</p>

It was clear after some digging that there was a distinct pattern revealed when we looked into who was employing women in the tech sector in NYC. The area shown in our map here represented a particularly dense area containing tech companies [Forbes](https://www.forbes.com/pictures/56e1922ae4b0c144a7f7119b/which-big-tech-companies-/#1d57f6845855) says employ a large number of women. Even better is that it happened to overlap heavily with the areas served by our busiest train stations. I love when things come together like this.

One of my favorite parts of this project (okay, it was actually just my favorite graph) was an insight my group member Marc Kelechava brought to the table. It turns out that the MTA also provides live data, and from that we were able to pull statistics that showed us which platforms/lines were most often experiencing higher than average delays. Ie, we were able to predict which stations would contain a high number of bored and waiting travelers. We cross referenced line data with this live data in order to recommend where to put boots on the ground and interact with waiting passengers on the platforms themselves, not just at entrances and exits.


<p align="center">
<img src="/assets/images/2019/1/platform_wait.png">
</p>

Our recommendations based off of this statistical analysis are as follows:

<p align="center">
<img src="/assets/images/2019/1/MTA_presentation_8.png">
</p>

For those of you who didn't grow up during the turn of the millenium, those penguins are taking over Manhattan as part of the movie Madagascar. It felt appropriate at the time.

Here's our citations slide, I'll update this with links when I'm not short on sleep. In the meantime they're available on GitHub.


<p align="center">
<img src="/assets/images/2019/1/MTA_presentation_12.png">
</p>
