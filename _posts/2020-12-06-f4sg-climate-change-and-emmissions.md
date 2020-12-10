---
title: Predicting the Philippine's C02 Emissions in 2020
date: 2020-12-06 00:00:00 Z
tags:
- Data Analysis
- Predictive Analytics
- Social Good
subtitle: In partnership with Eskwelabs and The Climate Realty Project, Eskwelabs'
  Data Science alumni try to predict the PH's C02 emissions in 2020 and analyze if
  COVID-19 has played a major role in it.
comments: false
image: "/images/blog/f4sg-ccxe/cover.jpg"
reading-time: 5
share-img: "/images/blog/d4g-ph-traff/share.png"
author_list:
- 4_gab
layout: post
---

<br>

## The Philippines Holds One Of The Worlds Longest Lockdown

When COVID-19 struck this year, most countries' immediate measure in minimizing infections is having the country in a state of lockdown. Depending on how tightly implemented a lockdown is in a country, most of the regulations have people just staying at their homes, businesses closing down, and minimizing the use of public transportation.

With the Philippines having one of the world's longest lockdown, its very curious to see if the country has recovered the most in terms of C02 Emissions produced in 2020, given how the new normal has changed everyone's behaviors during the pandemic.

## What is Currently Happening?

### Google COVID-19 Mobility Report

To gain more context on how COVID-19 has changed each countries' behavior, data from [Google's COVID-19 Mobility Report](https://www.google.com/covid19/mobility/){:target="*blank*"} shows the total amount each Southeast Asian country has invested towards the improvement of their respective transport infrastructure.

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

As for C02 Emissions in 2020, [Carbon Monitor](https://carbonmonitor.org/){:target="*blank*"} is a global initiative that uses science-based estimates to monitor daily CO2 emissions of different countries by region across different sectors

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
![figure4.PNG](/images/blog/f4sg-ccxe/figure4.PNG){: .center-block :}
<figcaption><i><b>Figure 4</b> Most countries follow similar movement trends</i></figcaption>

Despite having movement data, most of the countries' trends are the same. So if we train a model just using these data, the Philippines would just imitate the C02 emissions of the country with the most similar movement to itself. In order to fix this, we need another dataset that makes the countries more distinct from one another besides their movement data.

### Climate Watch

[Climate Watch](https://carbonmonitor.org/){:target="*blank*"} offers open data, visualizations and analysis to help policymakers, researchers and other stakeholders gather insights on countries' climate progress.

They have data on C02 Emissions produced by various sectors:

- Energy
- Agriculture
- Industrial Processes
- Waste
- Land-use Change
- Forestry
