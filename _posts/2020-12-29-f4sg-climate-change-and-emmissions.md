---
title: Predicting the Philippine's C02 Emissions in 2020
date: 2020-12-29 00:00:00 Z
published: true
tags:
- Data Analysis
- Predictive Analytics
- Social Good
publish: hide
subtitle: In partnership with Eskwelabs and The Climate Realty Project, Eskwelabs'
  Data Science alumni try to predict the PH's C02 emissions in 2020 and analyze if
  COVID-19 has played a major role in it.
comments: false
image: "/images/blog/f4sg-ccxe/cover.jpg"
reading-time: 5
share-img: "/images/blog/f4sg-ccxe/cxc-f4sg-share-img.png"
author_list:
- 4_gab
- e_david
- e_jake
- e_josh
- e_kayecee
- e_jm

layout: post
---

<br>

# The Philippines Holds One Of The Worlds Longest Lockdown

When COVID-19 struck this year, most countries' immediate measure in minimizing infections is having the country in a state of lockdown. Depending on how tightly implemented a lockdown is in a country, most of the regulations have people just staying at their homes, businesses closing down, and minimizing the use of public transportation.

With the Philippines having one of the world's longest lockdown, its very curious to see if the country has recovered the most in terms of C02 Emissions produced in 2020, given how the new normal has changed everyone's behaviors during the pandemic.

## What is Currently Happening?
&nbsp;
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

## Carbon Monitor

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

## Climate Watch

[Climate Watch](https://carbonmonitor.org/){:target="*blank*"} offers open data, visualizations and analysis to help policymakers, researchers and other stakeholders gather insights on countries' climate progress.

They have data on C02 Emissions produced by various sectors:

- Energy
- Agriculture
- Industrial Processes
- Waste
- Land-use Change
- Forestry

<center><b>Aggregated C02 Emisssions per Country</b></center>
![figure4.PNG](/images/blog/f4sg-ccxe/figure5.PNG){: .center-block :}
<figcaption><i><b>Figure 5</b> Countries are now unique from one another</i></figcaption>

With Climate Watch's data, each country is now different from one another based from the C02 emissions they produce from each sector. With this data, predicting C02 emissions will not only base from how a country moves but how each produces C02 emissions as well.

## Predictive Model Layout
![figure6.PNG](/images/blog/f4sg-ccxe/figure6.PNG){: .center-block :}
<figcaption><i><b>Figure 6</b> The entire process of predicting C02 emissions.</i></figcaption>

With everything in place, the diagram above summarizes the entire workflow in predicting C02 emissions. For the model, we used a Random Forest Regression since the model's going to predict the Philippine's C02 levels. So given themodel, the approach we did is more of predicting rather than forecasting since the model will just predict the Philippine's C02 levels based from how other countries move in a given date, considering their individual attributes as well.

## Results

![figure7.PNG](/images/blog/f4sg-ccxe/figure7.PNG){: .center-block :}
<figcaption><i><b>Figure 7</b> The predicted values show a relationship with residential movement</i></figcaption>

Looking at the predictions, it was able to produce the same trend from figure 2 that when residential movement increases, the emissions produced by transport reduces. So we can say that this is definitely an accurate trend line for emissions produced by transport. But what about its levels compared to other countries?

### Predicted Values vs. Other Countries

![figure8.PNG](/images/blog/f4sg-ccxe/figure8.PNG){: .center-block :}
<figcaption><i><b>Figure 8</b> These countries have higher metric tons of C02 emissions produced than the Philppines</i></figcaption>

Among the countries with 2020 c02 data, the Philippines is lower than Brazil, India, Japan, and Russia compared with the predicted values.

![figure9.PNG](/images/blog/f4sg-ccxe/figure9.PNG){: .center-block :}
<figcaption><i><b>Figure 9</b> There are countries that have the same C02 levels as the Philippines</i></figcaption>

But looking at France, UK, Italy, and Spain, these countries have the same levels as the Philippines. We did another prediction for emissions produced by power and the results are more or less the same.

So just basing from our predicted values in this little exercise of ours, <b> the Philippines is not the lowest but is among the countries with low C02 emissions in 2020 </b>. Take our prediction with a grain of salt since the model had a <b>90% test score</b> which makes the model heavily biased with the available datasets, and there are lots of missing factors as well to make the prediction closer to what the actual values may be.

## Caveats to note

![figure10.PNG](/images/blog/f4sg-ccxe/figure10.PNG){: .center-block :}
<figcaption><i><b>Figure 10</b> Climate Watch data of PH, France, UK, Italy, and Spain</i></figcaption>

The reason why the Philippines's predicted emissions are similar to these countries is because they are the countries whose climate watch data are the closest to the Philippines. The reason why these are the only countries similar to the Philippines is because we only used the countries available on Carbon Monitor that have 2020 C02 data, and Carbon Monitor only has 12! It would be helpful to have at least have most of the SEA countries here for a much better comparison of country attributes to countries that are more similar to the Philippines.

Speaking of attributes, other factors should be considered as well like population, investments in transportation, number of businesses, registered vehicles, and other possible factors that could be used as basis to differentiate countries more from one another in order to compare the Philippines to countries that share the same state as us. Because for this model, we only based it on how the Philippines is similar to producing C02 emissions to other countries.

Raw movement data would be helpful as well since the Google Mobility reports aggregate each countries movements from -100 to 100, so if the values were raw, the countries would be more different from one another taking into account the number of people moving per country. The mobility data also covers some areas from each country as well, so it would be great if it covers majority of the country's area to reduce bias.

## Eskwelabs' Fellows for Social Good

This project was done in collaboration with [Eskwelabs](https://www.eskwelabs.com/){:target="*blank*"} and [Climate Reality Project](https://www.climaterealityproject.org/){:target="*blank*"} for Eskwelab's Fellows for Social Good event where alumni work together on small projects that aim to solve social problems through the use of data.
