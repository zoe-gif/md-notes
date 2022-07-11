---
title: Statistics and Probability
date: 2022-07-08
update: 2022-07-08
categories:
- Study notes
- Math
tags: Statistics
description: 
---

### Categorical and quantitative data

- Dataset elements
    - Individual
    - Variable
        - Catagorical variable
        - Quantitative variable
- Common statistical graph
    - Bar graph
    - Pie graph
    - Venn diagram
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708133745.png" width="200" height="">
    - Two-way frequency table
        - Relative frequency: compared to total 100%
        - Marginal distribution
            - Probability distribution of the variables contained in the subset
            - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708135546.png" width="300" height="">
            - % or in counts
        - Conditional distribution
            - Probability distribution for a sub-population
            - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708135918.png" width="300" height="">
            - % only
    - Frequency table
    - Dot pot
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708211512.png" width="200" height="">
    - Stem and leaf plot
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708212055.png" width="300" height="">
    - Histogram
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708212818.png" width="200" height="">
    - Box/whisker plot
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708215525.png" width="500" height="">
        - Q1: 25th percentile
        - Q3: 75th percentile
        - Interquartile range IQR = Q3 - Q1
        - Interquartile range rule to detect outliers
            - If 1.5 IQR rule: 
                - Bounds = [Q1 - 1.5 * IQR , Q3 + 1.5 * IQR]
    - Line graph
    - Exponetial graph
    - Logarithmic graph
    - Trigonometric graph
- Distribution
    - Shape
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708211646.png" width="500" height="">
    - Cluster: data gathering arount one value
    - Gap: zero frequency but with non-zero frequency classes on both sides
    - Peak: high point
    - Outlier: data much smaller or larger than most
    - Median: center of distribution
    - Variability: how spread out a group of data is

### Descriptive and inferential statistics

- Descriptive statistics: to descript
    - Mean: average
    - Median: middle, balancing point
        - Total distance below the mean = total distance above the mean
    - Mode: value that occurs most often
    - Range: distance between the lowest and highest
    - Mid-range = Range / 2
    - Variance: 
        - Population variance: $\sigma^2 = \frac {\Sigma (x - \mu)^2}{n} = \frac {\Sigma x^2}{n} - \mu^2$
        - Sample variance: $\sigma^2 = \frac {\Sigma (x - \mu)^2}{n} = \frac {\Sigma x^2}{n - 1} - \mu^2$
            - Why n-1: unbiased estimate
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220709191658.png" width="300" height="">
    - Standard deviation (SD): 
        - Standard deviation: $\sigma = \sqrt {\frac {\Sigma (x - \mu)^2}{n}}$
        - Sample standard deviation: $\sigma = \sqrt {\frac {\Sigma (x - \mu)^2}{n - 1}}$
    - Mean absolute deviation (MAD): $  MAD = \frac{\Sigma|x - \mu|}{n} $
- Inferential statistics: to make inference and prediction

### Modeling data distribution

- Percentile: percentage of data that is below certain amount
- Z-score: how many standard deviation away from mean
    - $z = \frac{x - \mu}{\sigma}$
    - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220711211404.png" width="500" height="">
    - Empirical rule 68-95-99.7
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220711215930.png" width="300" height="">
    - Standard normal table for proportion
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220711214359.png" width="500" height="">
- Effect of linear transformation
    - Add a constant to data set
        - Mean, median add
        - Standard deviation. IQR same
    - Scale data set
        - Mean, median, standard, IQR deviation scale
- Density curve: distribution and probability of value
    - Total area under cure: 100%
    - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220711213442.png" width="250" height="">
- Normal and binomial distribution
    - Normla distribution
        - $\begin{aligned} 
                f(x)    &= \frac{1}{\sigma \sqrt{2\pi}} e^{-{\frac{1}{2}} (\frac{x-\mu}{\sigma})^2}\\
                        &= \frac{1}{\sqrt{2\pi \sigma^2}} e^{-{\frac{1}{2}} z}\\
                        &= \frac{1}{\sqrt{2\pi\sigma^2 e^{z^2}}}
            \end{aligned}$
        - Continuous
    - Binomial distribution
        - Summarize the number of trails with the same probability of attaining one particular value
        - Discrete
        - More trails, getting closer to normal distribution