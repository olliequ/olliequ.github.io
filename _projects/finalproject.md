---
name: FinalProject
tools: [Python, HTML, vega-lite]
image: assets/pngs/cars.png
description: Submission for the Final Project
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# A deep-dive into data surrounding the Olympic Games!
## This was completed by Oliver Quarm (NetID: oquarm2, Group 10) for IS445's Final Project

## Introduction
For the final project I analysed extensive data for the Olympic Games, spanning over a century! My goal was to obtain the most interesting data among the datasets I looked at, and present them in the most interesting way possible! To complete my mission, I used Altair and Vegalite.

My notebook can be found here by clicking the button below:

<div class="center">
{% include elements/button.html link="https://github.com/olliequ/olliequ.github.io/blob/main/python_notebooks/part3.ipynb" text="The Notebook!" %}
</div>

## Primary Dataset/Visualization
My primary dataset was a massive CSV of individual entries of Olympic athletes, including their age, height, weight, but more importantly their nation, event, and any medals won. The dataset is titled '*120 years of Olympic history: athletes and results*'. The dataset is from Kaggle, posted by the user `@rgriffin`, accessible here: https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results. This user gathered the data from an organization called `sports-reference`, whose Olympic data has now branched off as `Olympedia`. It's a dataset spanning 120 years of Olympic Games statistics revolving around athelete & medal information.

Below is my main visualization (it's interactive!) for this dataset:

<vegachart schema-url="{{ site.baseurl }}/assets/json/main_dashboard.json" style="width: 100%"></vegachart>

## Contextual Dataset/Visualization
For the contextual dataset, I looked at more high-level, wholistic data for each Olympic Games host nation. I made 2 visualizations: 1 was the spending amount for various host nations, and the second was the number of events various host nations had for their Olympic Games. I sourced this dataset from [here](https://data.world/sports/olympics/workspace/file?filename=outturn+sports-related+costs+of+the+Olympic+Games+.csv). The 2 visualizations are displayed below:

<vegachart schema-url="{{ site.baseurl }}/assets/json/cost_per_country.json" style="width: 100%"></vegachart>

<vegachart schema-url="{{ site.baseurl }}/assets/json/athletes_per_host_nation.json" style="width: 100%"></vegachart>

## What's happening in the charts?
### Primary Visualizations:
I have a main dashboard, which was created using `mark_rect()` from Altair. It shows for each country that's participated in the Olympic Games, the number of medals they've won overall at each Olympic Games city location that's ever happened. The more medals a country has won in a specific city, the dark the shade of the box!

I've made it interactive such that:
- Hovering over box gives you details on which country, city, and medal tally you're looking at. This is useful considering the chart is big, and you can get easily lost!
- There is another visualization below. By default, it shows the amount of medals ever collected in total for all nations, split by the type of medal. **When you click on a box** though, this visualization will instantly update to the medal tally for that specific nation at that specific Olympic Games host city.
- Furthermore, when you click on a box all other boxes 'fade away' -- that is, their colour dims and the box you've selected vividly changes colour and becomes apparent.

I think this visualization dashboard is really visually appealing. I think it's also useful for spotting trends. I found it interesting for example that when a given nation performs in a city of their own, they have a higher medal count than if they were competing in a different city. Look at GBR's performance in the London games, Australia's performance in the Sydney games!

### Contextual Visualizations:
For the contextual dataset, I made 2 bar graphs. One was illustrating how many events various host cities put on. For each country there is 1 total bar, but within the bar can be many shades of blue. The number of shades is equal to the number of different times that country has hosted the Olympic Games. The USA holds the record for hosting it 5 times, and so naturally has held the most events in total ever. For a single instance of an Olympic Games, China actually holds the record for the most events offered at `302`.

The second bar chart shows cost various countries have endured when hosting the games. Like the first chart, for each country there is 1 total bar, but within the bar can be many shades of blue. The number of shades is equal to the number of different times that country has hosted the Olympic Games. Interestingly, even though the USA has hosted the most amount of Games, it hasn't spent the most money! Russia has for its 2014 Sochi Winter Games -- a staggering USD$21.89 billion!

### References:
- https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results
- https://data.world/sports/olympics/workspace/file?filename=outturn+sports-related+costs+of+the+Olympic+Games+.csv