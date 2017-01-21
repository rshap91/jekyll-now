---
layout: post
title: Organic Data Munging
---




For my third project at Metis I looked at county level data from the American Community Survey (ACS) as potential indicators for whether or not that county had a Whole Foods.

I feel one of the stigmas about Whole Foods is that they have narrow focus in terms of who they are marketing towards. By looking at demographic data from the ACS I hoped to find what demographics served as indicators for Whole Foods locations.

Some companies are known to specifcally open locations nearby related buisnesses hoping to steal some of their customers away.
For a time, Long John Silvers strategically opened restaurants right next to McDonalds and marketed itself as a "burger alternative" hoping to appeal McD goers who were tired of the big mac. I wondered if maybe Whole Foods had any such strategy so I also included locations of some related and competing buisnesses in my model. Store locations I used in my model were those for Starbucks, McDonalds, Target, Walmart, and Trader Joes.

As apposed to basic descriptive analysis, I decdied to build a model that would make a prediction on whether or not a county had a Whole Foods based on the demographic data and the locations of related buisnesses. Doing so had a few benefits:

  - Going through over 100 demographic statistics by hand is unweildy even with computer assistance. A Predictive model yields information on which features are most relevant to it's predictions and helps focus attention on the most salient demographics
  - Looking at counties that my model got wrong could be areas worth exploring as possible locations for new Whole Foods Stores
 
I'll highlight some of my findings below, but the fun part of this is really the visualization I built in d3:

http://bl.ocks.org/rshap91/raw/7d83217a05828988c6f543acfa2f887c/

You can choose a data point from the drop down menu to color the map according to the values for each county. For example if you choose "Starbucks", the map will change colors so that counties with more Starbucks locations are colored darker red. Hover your mouse over the map to see exactly how many there are in a given county. 

You can then click the "Show Actual" checkbox to show all the counties that have a Whole Foods and you'll see that they all fall in counties that also have a Starbucks. This isn't much of a surprise given that Starbucks has over 10,000 locations in about 1,000 different counties, but the overlap is still strong enough to boost the model performance. If your county doesn't have a Starbucks... it doesn't have a whole foods
 
You could also look at Trader Joes locations to see a strong overlap there as well. In fact, 77% of counties that have a Trader Joes also have a Whole Foods.

In terms of demographics it was interesting to note that obesity rates were negative indicators of Whole Foods locations while higher percentage of college grads were positive indicators. A whopping 92% of counties that had at least 1 Whole Foods had obesity rates below the national average (31%). 

While it's tempting to draw conclusions from that statistic, I must remember that correlation does NOT imply causation. Therefore further analysis is required. 

The full project can be found on my [github] (https://github.com/rshap91/WholeFoods)
 
