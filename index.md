---
layout: page
title: Nowcasting confidence in job security using Google Trends
cover-img: /assets/img/gtrends.png
subtitle: Using the University of Michigan's surveys of consumers
---

# Do Americans feel secure about their jobs ?
Every month, the University of Michigan updates their [surveys of consumers](https://data.sca.isr.umich.edu/data-archive/mine.php) in which they collect the people's opinion on their current financial situation. One of the questions respondants are asked is:
"During the next 5 years, what do you think the chances are that you (or your husband/wife) will lose a job that you wanted to keep ?". 

{% include mean_plot.html %}

As this figure shows, the answer the average American gives varies rapidly in time. Because confidence in job security will likely affect a person's economic behaviours, there is a high incentive to anticipate it's evolution in the near feature. 

# How we can predict consumer confidence
A first step towards guessing how confidence will evolve in the near future is to acknowledge the seasonality of the phenomenon. 

INSERT MEAN BY MONTH GRAPH

## Baseline model
![Dataset](DATA/Dataset.png)
## Baseline model
Here you can see baseline model.

Why t-1 and t-6:
{% include regression_table.html %}

Results:

{% include baseline_plot.html %}

Ok.
