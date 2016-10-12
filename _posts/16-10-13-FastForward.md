---
layout: post
title: FastForward
---


As if movie prices in the city aren't enough from dettering me from going to the movies, spending 2 weeks scraping the web for all the different stats on every possible movie certainly has me sick of the whole industry and makes me never want to go to the cinema again. If you don't know what scraping the web means, heres some background: 

When you go to a website it's usually no big deal to just look at the page with your human eyes, click on links with your human hand, and interpret basic information on the webpage using your human brain. Computers, however, don't have hands, eyes, or brains and when you want them to go to a bunch of websites (say movie pages on boxofficemojo.com) and collect a bunch of information for you (say the Total Gross for each movie), it's REAAALLLY  arduous to tell them exactly what you want (and believe me, they need to know EXACTLY). For starters, you have to talk to them in the language of html (the language used to build websites). Here's a snippet of some html from www.imdb.com. I'd post the whole thing... except the html used to create just the imdb homepage is 60 pages long!

![imdbHTML] (https://rshap91.github.io/assets/imdbHTML.png)


On top of that, not all the pages are layed out the same and the computer is horrible at generalizing. Searching for 
"Star Wars - A New Hope" throws an error and halts my entire program because the movie is actually called "Star Wars: A New Hope" (with a **colon** duh...). 

After all was said and done, I had created a model that was, not surprisingly, not that great at predicting how much movies would make. If it was, I'd be writing this post from the lounge pool in my new 100 ft yacht which I would have bought with all the money I made revolutionizing the movie industry... alas.

The code and powerpoint for the project is available [here](https://github.com/rshap91/Movie_Gross).
