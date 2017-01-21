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
 
 
 
