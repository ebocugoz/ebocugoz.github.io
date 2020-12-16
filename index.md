---
layout: page
title: Nowcasting confidence in job security using Google Trends
cover-img: /assets/img/gtrends.png
subtitle: Using the University of Michigan's surveys of consumers
---

# Dataset presentation
Data was obtained from [the University of Michigan's surveys of consumers](https://data.sca.isr.umich.edu/data-archive/mine.php) (Table 17).
It shows the evolution of the average American's confidence that they (or their spouse) can maintain their job position in the next 5 years, if they desire to. Respondants were asked:  "During the next 5 years, what do you think the chances are that you (or your husband/wife) will lose a job that you wanted to keep ?". They were asked to answer an integer from 0 to 100. 

## Data Exploration
### Plots 
Here is mean plot.

{% include mean_plot.html %}

Ok. 
## Baseline model
![Dataset](DATA/Dataset.png)
## Baseline model
Here you can see baseline model.

Why t-1 and t-6:
{% include regression_table.html %}

Results:

{% include baseline_plot.html %}

Ok.