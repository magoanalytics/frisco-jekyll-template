---
layout: post
title: News Awareness of Filipinos in Social Media
subtitle: Using TF-IDF and machine learning to analyze the state of the Filipino people's priorities in the news.
gh-repo: gabrieldaos/eskwelabs-capstone-filipino-newstweets
gh-badge: [star, fork, follow]
tags: [Esklwelabs, Capstone, Machine Learning]
comments: true
share-img: /img/capstone-images/sona_vs_bjg.PNG
---

This capstone project deals with analyzing where the attention of the Filipino people lie with regards to the news tweets being published daily. Ridge regression was used to make the predictions of a tweet's performance (Likes & Tweets) from tweets that were converted to TFIDF vectors.



### How the project came to be

![sona_vs_bjg](/img/capstone-images/sona_vs_bjg.PNG){: .center-block :}

As a daily social media user in the Philippines, I noticed that the Bea, Julia, and Gerald scandal (A scandal between these celebrities in our country) took over social media on the same week that our President gave his State of the Nation Address. Despite having lots of nationwide issues brought up in that SONA, people were more concerned about who cheated on whom between the 3 celebrities I mentioned earlier.

Because of the scenario that happened, I wanted to explore this hypothesis:

## Filipinos are interested in celebrities than social issues that the country has.

By exploring this hypothesis, we'll figure out by using machine learning how we can get Filipinos more engaged with the relevant problems in the Philippines.

![hootsuite](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/hootsuite.PNG?raw=true){: .center-block :}

Based from a recent statistic made last January 2019, roughly 61% of Filipinos that are using social media are between the ages of 18-34 . We now live in an age where people would tune into their smartphones to get the latest news updates instead of their television. This is why I'll be using **Twitter** as a medium for this study.

In order to confirm the hypothesis, we'll need to answer these three questions in order to understand what's currently going on in social media.

1. What are the top news tweets of 2019 based from likes & retweets?

2. What are the similarities of the popular news tweets?

3. Can we predict how popular a tweet will be based on the features it has?


![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/methodology.PNG?raw=true){: .center-block :}

In order to answer the questions earlier, this is the methodology that I went through. I'll be posting a separate post on how I did web scraping on Twitter.

## 1. Which news tweets has gathered most of the Filipino's attention this 2019

{: .box-note}
**Note:** Data is only until September 2019 since that's when the project was done.

![methodology](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/distribution.PNG?raw=true){: .center-block :}

To give a brief overview, these are the total number of tweets that was gathered from each news source I web scraped from in Twitter. This is just to show that the data is not skewed to one news source in this data analysis.

### President Duterte and other National News Headlines are consistently present each month

![word_cloud_freq](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/word cloud freq.gif?raw=true){: .center-block :}

If we're going by frequency of tweets, President Duterte gets the most coverage out of all the topics this past year. These tweets about President Duterte are followed by national news headlines like the elections, storm warnings, Catriona Gray, China, and etc.

![top_tweets](https://github.com/soadleirbag/soadleirbag.github.io/blob/master/img/capstone-images/top_tweets.PNG?raw=true){: .center-block :}

But if we're going to base it by likes, most of the top news tweets involve at least a popular figure in the Philippines, mostly people involved in social media, issues, and pop culture.

## 2. How are these popular tweets similar to one another?

![sim_tweets](/img/capstone-images/sim_tweets.PNG){: .center-block :}

We know that the top news tweets involve a popular figure, but the most similar ones usually involved ABS-CBN stars in their news tweets if we actually stack the number of likes each person has on all of them.

There are a few outliers in this finding like Dela Rosa and Alden Richards, but probably because he recently worked on a movie with Kathryn Bernardo, an ABS-CBN star, but another person who stands out among the people  in the list is Mayor Isko Moreno.

## 3. Can a machine learning model predict a tweet's performance?

Based on what was discussed earlier, we now know that:

1. Top news tweets involve a popular figure.

2. Most of these news tweets are about ABS CBN stars.

With these things established, can a machine learning model take this into account and predict a tweet's performance based on its content?

By using TF-IDF and ridge regression for the machine learning model, these are outputs made with roughly 70% accuracy for both predicting likes and retweets based on its content.

![pred1](/img/capstone-images/pred1.PNG){: .center-block :}

In the sample above, these are the following tests attempted:

1. A typical news tweet about the SOGIE bill.

2. Adding a political figure in the news tweet.

3. Change the political figure into an ABS-CBN star.

4. Change the news provider to ABS-CBN News.

For every changes I made in the content, the number of likes and retweets increase. We can now clearly see which features/content of a news tweet greatly affects its performance.

![pred1](/img/capstone-images/new_pred2.PNG){: .center-block :}

The same tests are done above for the Farmers in the Philippines. The predictions were just the same as the test earlier.

# Conclusion

### Our country has a Celebrity driven culture where stories are relevant when there’s a popular figure involved in it.

I know that some of you may already know that adding a celebrity to something is always equal to more exposure, but now I have shown you quantifiable evidence of the degree that most of the Filipinos care more about other people's lives than the other relevant issues in our country.

Now it's easy to say that perhaps to further increase the Filipinos' attention to the social issues in our country is perhaps having these celebrities as the people presenting the problems to the public (which some NGOs already do) or maybe change the news format into something the audience is familiar with what they're currently watching, but do you guys remember the outlier I mentioned earlier?

**Mayor Isko Moreno**, now this guy has figured out how to spread awareness to his campaigns and the issues he's bringing up in Manila. He's doing the same things that other celebrities does, he levels with his audience, learns how to talk their language, and makes his problems and life relatable to the people. Now those things get the Filipino people's attention, which is seen with the findings earlier in # 2.

Our government should not be going all fancy and just say I'm going to this and that and just tell people they have to do this. They must learn how to step down to our level in order to get their point in peoples' heads, otherwise it's just gonna pass through and they'll just go back to figuring out whatever it is going on between the Barretos and such.
