---
layout: page
title: Predicting perceived job security using Google Trends
cover-img: /assets/img/gtrends.png
subtitle: Using the University of Michigan's surveys of consumers
---

# Do Americans feel secure about their jobs ?
Every month, the University of Michigan updates their *[surveys of consumers](https://data.sca.isr.umich.edu/data-archive/mine.php "Link to the surveys")* in which they collect people's opinion on their current financial situation. One of the questions respondants are asked is:
>During the next 5 years, what do you think the chances are that you (or your husband/wife) will lose a job that you wanted to keep ?

The answer the average American gives varies rapidly in time:

{% include mean_plot.html %}

Because confidence in job security will likely affect a person's economic behaviours, there is a high incentive to anticipate it's evolution in the near feature. 

# How we can predict consumer confidence
A first step towards guessing how confidence will evolve in the near future is to acknowledge the seasonality of the phenomenon. 

INSERT MEAN BY MONTH GRAPH

As you can see, Americans typically feel less confident about their jobs when the summer hits (and they have to announce to their boss they are taking an unplanned 2 month break). What this means for us is that we can get a good idea of how people are going to feel about their jobs in the coming month just by knowing the monthly history. 

INSERT A BASELINE MODEL PERFORMANCE VISUALIZATION

In this concrete example, it appears that job confidence 1 and 6 months before are the most relevant for predicting it at a given time:    

{% include regression_table.html %}

## Enters Google Trends
But can we do better than this ? What if you wanted to use data science to gain a competitive edge by making more reliable predictions of the future evolutions of the market ?
You can use Google Trends to see what people are searching in real time. This can give insights about the current feel of the general population about the economical situation or any other trending topic really. Coming back to job security, the idea is quite simple. If overnight, there is a boom of Google queries for job opportunities, there's obviously people worried about their jobs, right ?

To get the most out of Google Trends, you'll need to carefully think about what queries are relevant. If you cannot read people's minds, or are lazy, then you'll bed very interested in having an automated way of selecting those. 

SHOW FEATURE SELECTION

SHOW FINAL RESULTS

Results:

{% include baseline_plot.html %}


