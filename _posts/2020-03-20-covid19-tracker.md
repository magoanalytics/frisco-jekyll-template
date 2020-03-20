---
layout: post
title: How we created a COVID-19 Tracker Using News Articles
subtitle: How webscraping and NLP can be used in tracking the COVID-19 cases in the Philippines.
gh-repo:
gh-badge:
tags: [Webscraping, NLP, Mapping]
comments: true
image: /img/capstone-images/sona_vs_bjg.PNG
---

Starting last January, the Philippines has been alert of the Coronavirus outbreak that's happening all around the world. Flights are being suspended, people are being quarantined, and most of all people are always speculating where could the virus could be most likely present in our country.

### One of the Popular Solutions

![sona_vs_bjg](https://external-preview.redd.it/6rSm9gRiWrR2NhxlCbrt9JuKN9NcxfgDUtLBr01JUBc.jpg?auto=webp&s=5dc516ed30373d8690a30e04a97e9d9922b66a49){: .center-block :}

One of the popular mapping that's done out there is by John Hopkins where it tracks all the types of COVID-19 situations in the world: cases, deaths, and recovered.  But one of its current downsides is that the data is not on a granular level that if I want to observe one country's situation, it's only on an aggregated level. Plus you can't really observe the trend here, its just more of where are the places the virus is mostly active.

## Current Attempts on Mapping the COVID-19 in the Philippines

![hootsuite](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/hootsuite.PNG?raw=true){: .center-block :}

One of the efforts made is done by La Salle where they manually get all the COVID-19 information from news articles in the country.

![wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/COVID-19_Outbreak_Cases_in_the_Philippines_by_region.svg/220px-COVID-19_Outbreak_Cases_in_the_Philippines_by_region.svg.png)
{: .center-block :}

Another effort done is through Philippines coronavirus outbreak Wikipedia page. It reflects data from the DOH website and various news articles as well. It clearly shows which areas have suspected and confirmed cases of the Coronavirus but there is only minimal control of the visualization.

## Our Own Methodology in Tracking COVID-19

![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/distribution.PNG?raw=true){: .center-block :}

Instead of waiting for the official announcements from WHO or DOH, getting updates from news is much more faster since they are the people who are actually on the sites of each cases. So we've scraped all the news articles from various news sources in the country in that are related to the COVID-19. Using ReGex, we took all the numbers that are beside words for each article to get the counts of suspected or confirmed cases and the province they belong to. These articles would then go through LDA Topic Modeling in order to summarize what the article is all about with a few keywords, in order to identify which articles are about confirmed or suspected cases of the virus. All the parsed data are then summarized and reflected in an interactive map that shows the trend of the virus in our country.

![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/distribution.PNG?raw=true){: .center-block :}

This is an example of how ReGex gathers all the counts in one news article. All Philippine provinces would also be parsed by ReGex as basis for the locations of the virus.

![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/distribution.PNG?raw=true){: .center-block :}

Topic modeling is simply the process of identifying topics in a given group of text by analyzing the patterns of words, which saves you the time of reading the entire text just to get the context. Latent Dirichlet Allocation was used for topic modeling, where its approach doesn't care about the arrangement of words but how many times did a word appear on a given number of topics. So the more frequent a word appears in a topic, the more likely it is to be a keyword that summarizes the article. With the two examples above, you can already get the gist of the article by just reading the LDA topics, which is highly useful in identifying whether an article's about a confirmed case or not.

![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/distribution.PNG?raw=true){: .center-block :}

The data that we have would then go through a series of other preprocessing methods to finalize the locations and counts for each area in order for us to get this final dataset to be used for mapping.

## Our Prototype Map

![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/distribution.PNG?raw=true){: .center-block :}

Using the final dataset, the results are mapped out using Keppler, an open source mapping software that is easily used and also has a time slider that allows you to control the state of the map by choosing a given time period. What we found out at the time of development was most of the virus was just located on the Visayas and Mindanao regions, so there's not that much reason for us here in Luzon to panic so much about the virus, but staying vigilant is still something we should do. Please do note that the map is still on its prototype stages and should not be used as basis in getting the official counts of cases in the Philippines.

## Our Next Steps

Currently, the map is just good at identifying areas that have cases of COVID-19 in the Philippines. Our methodology is still having problems identifying the correct counts for suspected or confirmed cases, mainly because:
- There are articles that repeatedly talk about the same thing, which on some cases the parsed data takes the wrong count.
- There are some keywords that possibly signify suspected cases in an article that we missed taking into account.
- There are also some wrong counts being used because the article is mistaken to take place in the Philippines whereas the location was just only mentioned in an COVID article.

To address these concerns we are looking into the following solutions:
- Increase our news sources, because currently we're only using two for the Prototype
- With the increased sources, a voting system will then be put into place whether a count is actually true or not.
- An EDA of n-grams in an article to analyze the keywords that may be used for identifying articles that talk about confirmed cases.
- Using word2vec as a data preprocessing method in order to further strengthen the topic modelling by taking into account word arrangements.

Once these problems are fixed, this will unlock the map's full potential. By simply changing the keywords, this will not only be able to track COVID-19 cases but other kinds of events as well whether you want to track Polio cases, storm victims, dengue, and etc. Hopefully once the capabilities of this mapping system are realized, different sources would allow us to directly connect their data in order to make Filipinos more aware of what's happening with our country with these kind of events.
