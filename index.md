---
layout: page
title: Predicting perceived job security using Google Trends
cover-img: /assets/img/gtrends.png
subtitle: Using the University of Michigan's surveys of consumers
---

# Do Americans feel secure about their jobs ?
Every month, the University of Michigan updates its *[surveys of consumers](https://data.sca.isr.umich.edu/data-archive/mine.php "Link to the surveys")* in which it collects people's opinion on their current financial situation. One of the questions respondants are asked is:
>During the next 5 years, what do you think the chances are that you (or your husband/wife) will lose a job that you wanted to keep ?

On average, the answer is typically around 20%. However, it can evolve rapidly, depending on the political and financial situation in the *US*:

{% include mean_plot.html %}

Because confidence in job security will likely affect a person's economic behaviors, there is a high incentive to anticipate its evolution in the near feature - for example before making investment or marketing decisions. 

# How we can predict perceveived job security
A first step towards guessing how job security confidence will evolve in the near future is to acknowledge the seasonality of the phenomenon. 

{% include monthly_percentage.html %}

As you can see, Americans typically feel less confident about their jobs when the summer hits (and they have to announce to their boss that they are taking an unplanned 2 month break). Also, it is reasonable to assume that their confidence doesn't change drastically from one month to another. What this means for us is that we can get a good idea of how people are going to feel about their jobs in the next month just by knowing the monthly history and using a autoregressive model. 

In this concrete case, it appears that knowing what the job security confidence was 1 and 6 months before is the most relevant measurements for predicting it at any given time. 
In order to test how well we are able to make predictions for the future using only these two anterior values, we can compare actual observation to what this model would have predicted: 

INSERT A BASELINE MODEL PERFORMANCE VISUALIZATION
{% include baseline_plot.html %}

Not too bad: on average, this model is off by MAE?? %.

## Enters Google Trends
Can we really not do any better than this in the age of data ? 
Actually, you can use Google Trends - a website by Google which lets you see how many users make certain queries in any region of interest during a period of your choice. By seeing what people are searching in real time, you can gain a competitive edge and make more reliable predictions of the future evolutions of the market. Coming back to confidence in job security, the idea is very simple. If there is an overnight boom of Google queries for job opportunities, then there must be a growing concern about job security in the general population - no need to wait for the University of Michigan to publish their next report in a few weeks!

To get the most out of Google Trends, you'll need to carefully think about what queries are relevant. If you cannot read people's minds, or are lazy, then you'll benefit from having an automated way of selecting those. After automatically generate a list of candidate queries, we used a Bayesian technique, called Spike and Slab, which computes estimated probabilities that certain variables should be included in the model. 
{% include Spike_slab.html %}

By using the queries for which inclusion probabilities are high (*Loan* and *Crisis*), we obtain a lower mean absolute error: 

{% include all_forecasting.html %}

|Baseline MAE | Google Trends MAE  | Improvement of MAE(%)
|:----------------------------: | ------------------------ | --------------
|1.1430 | 1.1293 | 1.1970%

While this improvement is not that impressive overall, it appears that Google Trends is very useful in predicting the behavior of the time series in uncertain times, like the Great Recession or the COVID-19 Recession:

{% include trends_improvement.html %}

|Baseline MAE (COVID-19) | Google Trends MAE (COVID-19) | Improvement of MAE(%)(COVID-19)
|:----------------------------: | ------------------------ | --------------
|2.266| 1.59 | 29.8239%

This improvement is much more important, because in these periods, timely adaptation is crucial. 



# What we learned






