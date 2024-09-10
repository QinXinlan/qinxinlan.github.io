---
page_id: project_4
layout: page
title: Statistics
description: An unerring compass guiding towards the truth
img: assets/img/statistical_significance.jpg
importance: 3
category: work
related_publications: true
---

## 🎓 What we know 🎓

### How many people for a new experiment
The bigger the effect, the smaller the sample size. Or in other words, if you can easily spot the signal of interest (SOI) amid all the noise, you don't need a lot of data to be confident in your findings.

The problem is that with EEG signals, the effect size is very small. And a bigger problem is that often the effect size is unknown (as well as the other parameters needed). 

That’s where the Fitted Distribution Monte Carlo (FDMC) method comes in [% cite guttmannflury2019apss %]. 

Recipe for FDMC:
1. Collect data from a historical dataset with similar characteristics to what you plan to collect, or run a small-scale propspective power analysis
2. Find the variable(s) that best describe the SOI
3. Fit this (these) variable(s) to a common distribution and estimate the effect size
4. Using the appropriate parameters (e.g. mean, standard deviation), simulate as much data as needed to achieve a desired statistical power (usually 0.8, with a significance level of alpha = 0.05.

The a priori sample size depends on the estimated effect size. For example, with an effect size of d = 0.1 (in green in the figure below), you’d need around 1250 trials. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Sample_size.png" title="FDMC" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fitted Distribution Monte Carlo (FDMC) Simulation for A Priori Sample Size Estimation
</div>


### A new visualization tool for confusion matrices: Confusion Ellipses (CE)

So, you’ve estimated your a priori sample size, run your experiment, and gotten some classification results. Now what?

Let's start by visualizing the results. Confusion matrices (CM) are a great tool for evaluating a classifier’s performance. For a simple two-class problem, the four values in a CM don’t tell you much on their own—but the relationships between them do, revealing insights like class imbalance, accuracy, and other performance metrics.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Confusion_Ellipse.png" title="Confusion Ellipse" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Confusion Ellipse: a new representation of the Confusion Matrix
</div>

An interesting property of the CM is that it consists of two independent samples, each following a Binomial distribution: True / False (or 0 / 1). And for each distribution, we can estimate the confidence interval (like the Clopper-Pearson interval shown in the figure). 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Confusion_Ellipse_with_Confidence_Interval.png" title="Confusion Ellipse with Confidence Interval" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Displaying the confidence intervals on the Confusion Ellipse
</div>

By design, Confusion Ellipses make it easy to compare classifiers at a glance. If a CE is narrower on the horizontal axis (green in the next figure), it indicates a higher accuracy compared to a wider ellipse (blue).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Comparison_Confusion_Ellipse.png" title="Comparison Confusion Ellipses" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of two Confusion Ellipses
</div>


### How much data to prove pipeline A is better than pipeline B


When comparing the performance of two (or more) classification algorithms, the key question becomes: do you have enough data to confidently say that one algorithm performs significantly better than another? In other words, what’s the minimum number of trials needed so that, in 95% of cases (with alpha = 0.05), the confidence intervals for each result do not overlap?

This is where the Distance Separation (DS) method comes in [% cite guttmannflury2023thesis %]. DS measures the level of separation between the confidence intervals at each sample size. The ratio is negative when the required sample size isn’t reached, zero at the critical sample size, and becomes positive thereafter.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Distance_Separation.png" title="Distance Separation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Making sure that there is enough data to have a significant difference between two classifiers
</div>

For instance, a green classifier with a 94% accuracy would be statistically significantly better than a blue classifier with 79% accuracy if the results are based on at least 96 trials.

When the difference in classification accuracy between two algorithms is smaller, you’ll need much more data to reach a conclusion.

---

## 🤔 What we don't know (yet) 🤔

### What is an acceptable minimum classification accuracy?

Well of course, the higher the better.  However, the acceptable accuracy level depends on the application and the risks involved. For instance, if a BCI controls a car and has a 10% chance of causing a fatal accident, very few would be willing to take that risk.
On the other hand, if a BCI offers a 60% chance of improving rehabilitation, many patients might find it worthwhile, even if the improvement is modest.

---
