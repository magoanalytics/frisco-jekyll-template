---
layout: post
title: Predicting the Philippine's C02 Emissions in 2020
subtitle: In partnership with Eskwelabs and The Climate Realty Project, Eskwelabs' Data Science alumni try to predict the PH's C02 emissions in 2020 and analyze if COVID-19 has played a major role in it.
tags: [Data Analysis, Predictive Analytics, Social Good]
comments: false
image: /images/blog/f4sg-ccxe/cover.jpg
reading-time: '5'
share-img: /images/blog/d4g-ph-traff/share.png
author_list: [4_gab]
---
<br>
## The Philippines Holds One Of The Worlds Longest Lockdown
 When COVID-19 struck this year, most countries' immediate measure in minimizing infections is having the country in a state of lockdown. Depending on how tightly implemented a lockdown is in a country, most of the regulations have people just staying at their homes, businesses closing down, and minimizing the use of public transportation.

 With the Philippines having one of the world's longest lockdown, its very curious to see if the country has recovered the most in terms of C02 Emissions produced in 2020, given how the new normal has changed everyone's behaviors during the pandemic.

## What is Currently Happening?

### Google COVID-19 Mobility Report
To gain more context on how COVID-19 has changed each countries' behavior, data from [Google's COVID-19 Mobility Report](https://www.google.com/covid19/mobility/){:target="_blank_"} shows the total amount each Southeast Asian country has invested towards the improvement of their respective transport infrastructure.

The Community Mobility Reports show movement trends by region, across different categories of places:
- Grocery & pharmacy
- Retail & recreation
- Parks
- Transit stations
- Workplaces
- Residential

<center><b>Aggregated Movement Data in 2020</b></center>
![figure 1](/images/blog/f4sg-ccxe/figure1.png){: .center-block :}
<figcaption><i><b>Figure 1</b> Aggregated movement data of all countries</i></figcaption>

From March onwards, movement for areas outside homes like workplaces, parks, and recreation drastically went down while residential areas went up since people have mostly stayed at home during the pandemic, giving us an idea that residential movement is greatly correlated with how people move during the pandemic.

### Carbon Monitor
As for C02 Emissions in 2020, [Carbon Monitor](https://carbonmonitor.org/){:target="_blank_"} is a global initiative that uses science-based estimates to monitor daily CO2 emissions of different countries by region across different sectors

![emissions_sec](/images/blog/f4sg-ccxe/emission_sec.png){: .center-block :}

For this study, we focused on Power and Ground Transport CO2 emissions since they're closely tied with movement data.

<center><b>Residential Movement vs C02 Produced</b></center>
![figure 2](/images/blog/f4sg-ccxe/figure2.png){: .center-block :}
<figcaption><i><b>Figure 2</b> Residential Movement vs Ground Transport & Power Emissions of all countries</i></figcaption>

We can see that as residential movement increases, the C02 emissions for transport and power go down. Since there is a correlation with movement data and C02 data, we have a way to predict C02 emissions through machine learning.

<center><b>Philippines Movement Data</b></center>
![figure 3](/images/blog/f4sg-ccxe/figure3.png){: .center-block :}
<figcaption><i><b>Figure 3</b> The Philippine's movement data in 2020</i></figcaption>

The Mobility Data set has a complete movement data for the Philippines. Since we have the movement & C02 data of other countries, we can train a model that understands how C02 is produced based on movement data and have it predict the Philippine's C02 based from its movements.


## Data Limitations
<center><b>Country Movement Comparison</b></center>
![figure 4](/images/blog/f4sg-ccxe/figure4.png){: .center-block :}
<figcaption><i><b>Figure 4</b> Most countries follow similar movement trends</i></figcaption>

Despite having movement data, most of the countries' trends are the same. So if we train a model just using these data, the Philippines would just imitate the C02 emissions of the country with the most similar movement to itself. In order to fix this, we need another dataset that makes the countries more distinct from one another besides their movement data.

### Climate Watch
[Climate Watch](https://carbonmonitor.org/){:target="_blank_"} offers open data, visualizations and analysis to help policymakers, researchers and other stakeholders gather insights on countries' climate progress.

They have data on C02 Emissions produced by various sectors:
- Energy
- Agriculture
- Industrial Processes
- Waste
- Land-use Change
- Forestry



## The Philippines is on its way to be third in yearly cyclist deaths

![sea budget](/images/blog/d4g-ph-traff/chart5.PNG){: .center-block :}
<figcaption><i><b>Figure 4.1</b> Cyclist Road Traffic Deaths in the Philippines, 1990 - 2017</i></figcaption>

Another relevant point to focus on is cycling. Public transport has been on halt at the start of the pandemic. Thus, Filipinos have turned to biking to get from place to place.

Compared with to other countries, an interesting trend is the one for cyclists in SEA. The red trend line represents the Philippines. Comparing this trend with others, our country appears to be on its way to have the third highest mortality rate for cyclists. Given the increase in biking since the pandemic, could there be a rise in mortalities this 2020?

## The Philippines has the lowest number of railways implemented

![sea budget](/images/blog/d4g-ph-traff/chart6.PNG){: .center-block :}
<figcaption><i><b>Figure 5.1</b> Railroads built for transportation in SEA</i></figcaption>

The data from the [International Union of Railways](https://data.worldbank.org/indicator/IS.RRS.TOTL.KM){:target="_blank_"} illustrates that the Philippines has the least amount of railways available.

![sea budget](/images/blog/d4g-ph-traff/chart7.PNG){: .center-block :}
<figcaption><i><b>Table 1.1</b> SEA Countries Investments vs Railroads Implemented</i></figcaption>

If we compare the transport investments to the total railroads per country, some countries have invested less than the Philippines yet, have a higher number of railroads.

## What should the Philippines do?

In summary, these are potential points of focus to improve the transport infrastructure in the Philippines:
- Effective measures in reducing pedestrian casualties
- Invest in cycling infrastructure
- Improve railway systems

Our country has already started implementing improvements like the [BRT system in Cebu](https://www.pna.gov.ph/articles/1094751){:target="_blank_"} This system not only improves bus transport but also pedestrian safety. We also have investments in road extensions like the [3 hour trip from Manila to Baguio via TPLEX](https://www.sunstar.com.ph/article/1863854/Pampanga/Local-News/TPLEx-reduces-Manila-Baguio-travel-time-to-3-hours){:target="_blank_"} and the [Ortigas - BGC bridge](https://www.topgear.com.ph/news/motoring-news/bgc-ortigas-bridge-meet-a962-20200807){:target="_blank_"} These can potentially reduce road traffic. However, most of these developments are geared towards private vehicles.

In order for the Philippines to reduce private vehicle dependence, investments should be made towards alternative transport, such as walking, biking, and commuting. To achieve this, safe and efficient infrastructure must be in place.

<i>“A developed country is not a place where the poor have cars. It’s where the rich use public transportation” – Gustavo Petro, Mayor of Bogotá</i>

## Data for Good Hackathon

This data analysis got second place on the [Data for Good Hackathon](https://www.unsdsn.org/data-for-good-hackathon-philippines){:target="_blank_"}. The United Nations Sustainable Development Solutions Network (SDSN) partnered with Eskwelabs, a data-science bootcamp in the Philippines, to host a Data for Good hackathon. The virtual hackathon was designed for those who were eager to learn more about how the Philippines is doing in achieving the United Nations Sustainable Development Goals (SDGs). Further analysis could be done by using updated datasets, if available.

[You can watch the presentation of Mago Analytics here.](https://www.facebook.com/Eskwelabs/videos/2434475030179439/?t=5110){:target="_blank_"}
