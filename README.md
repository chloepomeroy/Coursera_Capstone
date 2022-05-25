# K-Means-Similarities-in-Canadian-Neighbourhoods

This project was completed in Python using web scraping, the foursquare places api, and the k-means algorithm using sk-learn.

## Introduction

When moving from one city to another, it’s often difficult to know what each neighbourhood is like and house-hunting can feel like you're going in blind. This is particularly relevant for people who need to relocate for work but have never been to the city they're relocating to. In this project I analyzed the neighbourhoods of 4 Canadian metropolitan cities (Vancouver, Montreal, Ottawa, and Calgary) to find which neighbourhoods in different cities are most similar based on venues.

## Methodology
I found geonames.org which contains all the neighbourhood names, postal codes, boroughs, and cities for all of British Columbia, all of Alberta, all of Ontario, and all of Quebec. I scraped those pages and then dropped all rows that refer to cities other than Vancouver, Calgary, Ottawa, or Montreal. I also used foursquare to extract the most common venue types in each neighbourhood, which will be used as a feature to help determine similarity when training my model.

I chose a k-value of 6 because I found that with a larger number of clusters, most clusters only contained data from one city, which wouldn’t work for my use case.

Finally, I wrote a function that, when the name of any valid neighbourhood is input, will return all other neighbourhoods in the cluster. I also added an option to exclude all results from the cluster that were in the same city as the given neighbourhood, to tailor it more to the use case of someone who is moving from one city to another.
