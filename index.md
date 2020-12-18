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

Because confidence in job security will likely affect a person's economic behaviors, there is a high incentive to anticipate its evolution in the near feature. 

# How we can predict consumer confidence
A first step towards guessing how confidence will evolve in the near future is to acknowledge the seasonality of the phenomenon. 

{% include monthly_percentage.html %}

As you can see, Americans typically feel less confident about their jobs when the summer hits (and they have to announce to their boss they are taking an unplanned 2 month break). Also, it is reasonable to assume that their confidence doesn't change drastically from one month to another. What this means for us is that we can get a good idea of how people are going to feel about their jobs in the coming month just by knowing the monthly history and using a autoregressive model. 

In this concrete example, it appears that job confidence 1 and 6 months before are the most relevant measurements for predicting it at any given time:    

{% include regression_table.html %}

To test how well we are able to make predictions for the future, we can see what our result our model would have given, knowing only previous values and compare that to the actual observations: 

INSERT A BASELINE MODEL PERFORMANCE VISUALIZATION
{% include baseline_plot.html %}

## Enters Google Trends
But can we really not do any better than this in the age of data ? Actually, you can use Google Trends - a website by Google which lets you see how many users make certain queries in any region of interest during a period of your choice. By seeing what people are searching in real time, you can gain a competitive edge and make more reliable predictions of the future evolutions of the market. Coming back to confidence in joby security, the idea is very simple. If there is an overnight boom of Google queries for job opportunities, then there must be a growing concern about job security in the general population - no need to wait for the University of Michigan to publish their next report in a few weeks!

To get the most out of Google Trends, you'll need to carefully think about what queries are relevant. If you cannot read people's minds, or are lazy, then you'll benefit from having an automated way of selecting those. 


SHOW FEATURE SELECTION

For feature selection we used Bayesian technique called Spike and Slab, which gives us estimated probabilities that certain queries should be included in our model. 
{% include Spike_slab.html %}

SHOW FINAL RESULTS

Results:


{% include all_forecasting.html %}

{% include trends_improvement.html %}


