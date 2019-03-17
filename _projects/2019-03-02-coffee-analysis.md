---
layout: post
title: Coffee Grader Analysis
date: 2019-03-02 00:00:00
featured_image: "/assets/images/2019/3/tree.jpg"
---
<p align="center">
<img src="/assets/images/2019/3/flavor_wheel.png">
</p>


Many years ago I worked as a barista at Flat Black Coffee Company in Boston, MA. One of my bosses was a Quality grader - someone the [Coffee Quality Institute](https://database.coffeeinstitute.org/) has certified to score coffee beans according to a standardized set of tasting guidelines developed for differentiating "specialty" coffee from "commodity" coffee. A judge's score of 80/100 points or more is sufficient for the coffee to be considered specialty grade - anything with a total score of 79 points or fewer is regarded as commodity grade. Coffee is judged on its aroma/fragrance, flavor, aftertaste, acidity, body, balance, uniformity, "clean cup", sweetness and "overall" qualities.

My experience as a barista left me with questions about how scientific a process something as subjective looking as tasting a cup of coffee could really be - aren't individual palates *too* individual to provide consistent and fair feedback regarding the balance of a cup of coffee? A Q-grader's decision impacts the sale price of potentially an entire season's harvest of beans for many small farms in Central America, Africa and other socioeconomically disadvantaged regions of the globe. Should we be relying on humans to judge this without bias?

<p align="center">
<img src="/assets/images/2019/3/coffee-tasting-table.jpg">
</p>

I decided to dig into how the judging and cupping process worked - if there were clear and consistent trends within a dataset of all bean lots cupped through 2018, would that mean the process was reliable? My industry knowlege and personal experience tasting different single origin roasts led me to believe that different regions were known for being stronger in certain flavors or cupping notes than others because the terroir of a country contributes to the tasting notes in much the same way as it affects wine. I would expect to see this pattern in the data if the judges were not biased in ways out of line with fairness or reality.

I built a classifier out of my dataset that could help me predict the region of the country a cup came from based on the tasting notes and scores awarded to the cup by the Q graders. I had a small dataset to work with here, so I binned my countries into regions to ensure a basic classifier could even theoretically function in order to test my hypothesis: that Q-graders were unbiased or well-trained enough to be reasonably fair and consistent when judging beans for import.

<p align="center">
<img src="/assets/images/2019/3/xgboost_trained.png">
</p>

It looks like we can do pretty well predicting what part of the world a coffee came from on our holdout set after training our classifier on a subset of the original data, so there does appear to be a consistency with which the quality graders are judging the farms' output across the globe. This indicates to me a sufficiently rigorous approach on the part of the Coffee Quality Institute's training and scoring. There is always room for universal bias or pre-conceived notions (like my assertion about flavors appearing more in certain regions) but we can at least call them internally consistent - in theory they're doing a good job scoring coffee producers against themselves.

We can learn more about coffee by digging into the trends revealed with some simple analysis, and perhaps also make a few guesses about what causes them:


<div class="gallery" data-columns="1">
	<img src="/assets/images/2019/3/total_points.png">
	<img src="/assets/images/2019/3/balance.png">
	<img src="/assets/images/2019/3/aroma.png">
</div>


Haiti is relatively new to the coffee growing game when it comes to specialty coffee. You can see in the graphs above that they barely enter the specialty grade, ranking low in the pack. Another newcomer, Japan, is so new that only one farm actually ranks - but they rank highly, perhaps because of Japan's overall culture of taking special care and attention to detail. Countries like Mexico and Ethiopia on the other hand seem to be producing consistently great beans with their years of expertise and favorable climates. I hope to see Haiti's average scores climb as they recover from the semi-recent natural disasters they've experienced.

My favorite insight from this exploration has to be the strong tie between aroma and countries that use a wet ferment process in the harvest. This fermentation period /should/ increase smelly aromas, and countries known to use this process seem to smell more strongly, just like you'd expect!

Based off of the data available I recommend purchasing coffee from Papua New Guinea, earning the best scores overall.