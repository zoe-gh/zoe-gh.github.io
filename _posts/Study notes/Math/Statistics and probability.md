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
            - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708135546.png" width="400" height="">
            - % or in counts
        - Conditional distribution
            - Probability distribution for a sub-population
            - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220708135918.png" width="500" height="">
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
                - $Bounds = [Q1 - 1.5 * IQR , Q3 + 1.5 * IQR]$
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
        - Population variance: $\sigma^2 = \dfrac {\Sigma (x - \mu)^2}{n} = \dfrac {\Sigma x^2}{n} - \mu^2$

        - Sample variance: $\sigma^2 = \dfrac {\Sigma (x - \mu)^2}{n} = \dfrac {\Sigma x^2}{n - 1} - \mu^2$
            - Why n-1: unbiased estimate
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220709191658.png" width="300" height="">
    - Standard deviation (SD): 
        - Standard deviation: $\sigma = \sqrt {\dfrac {\Sigma (x - \mu)^2}{n}}$
        - Sample standard deviation: $\sigma = \sqrt {\dfrac {\Sigma (x - \mu)^2}{n - 1}}$
        
    - Mean absolute deviation (MAD): $  MAD = \dfrac{\Sigma|x - \mu|}{n} $
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

### Bivariate numerical data

- Scatterplot
    - Present the relationship between two variables in a dataset
    - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220716154807.png" width="300" height="">
    - Description of scatterplot
        - Trend line: correlation
            - Direciton: negative, positive
            - Strength: strong, weak
            - Form: linear, nonlinear
        - Cluster
            - Low/high in x and low/high in y
        - Outlier
- Covariance
    - Measure the direction of the relationship between two variables
    - $\begin{aligned}
        cov_{x,y}   &= E [x(x-E[x])(y-E[x])] \\
                    &= \bar {xy} - \bar {x} \bar {y}
        \end{aligned}$
        - Expected value (or mean) of the product of their deviations from their individual expected values
    - $ cov(x,y) = \dfrac {\sum(x - \bar x)(y - \bar y)} {n-1}$
    - Positive & negative $\implies$ direction of regression line
- Correlation coefficient $r$
    - Measure how strong a relationship is between two variables
    - $ r \in [-1, 1] $
    - Sample correlation coefficient
        - $\begin{aligned}
            r   &= \dfrac{1}{n-1} \sum (\dfrac{x - \bar{x}}{s_x}) (\dfrac{y - \bar{y}}{s_y}) \\
                &= \dfrac{1}{n-1} \sum z_{x} \cdot z_{y} \\
                &= \frac {1}{s_x \cdot s_y} cov_{x,y}
            \end{aligned}$
                
- Linear regression
- Residual or Error
    - Residual = actual y value - predicted y value
        - $r = y - \hat {y}$
    - Squared error (SE) or Residual sum of square (RSS)
        - $ SE_{line} = \sum {r}^2 = \sum (y - \hat {y})^2$
    - Residual plot
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220716210735.png" width="500" height="">
- Least square regression
    - $\hat y = mx + b $
        - $\begin{cases} 
            m &= \dfrac {n \sum{xy} - \sum x \sum y} {n \sum (x^2) - （\sum x）^2} \\
            b &= {\dfrac{1}{n}} (\sum y - m \sum x)
            \end{cases}$

        - $ m = \dfrac {cov(x,y)} {cov(x,x)} = \dfrac {cov(x,y)} {var(x)} = r \cdot \dfrac {s_y}{s_x} $

    - $ \bar y = m \bar x + b$
    - How to get
        - $ SE_{line} = (y_1-(mx_1+b))^2 + (y_2-(mx_2+b))^2 + \cdots + (y_n-(mx_n+b))^2$
        - Find $m$ and $b$ that minimizes $SE_{line}$
            - $SE_{line} = n \bar {y^2} - 2mn \bar{xy} - 2bn \bar y + m^2n\bar{x^2} + 2mbn\bar x + nb^2 $
            - Partial derivative of m & b = 0
                - $\begin{cases}
                    -2n\bar {xy} + 2n\bar{x^2}m+2bn\bar x &= 0 \\
                    -2n\bar y + 2mn\bar x + 2nb &= 0
                    \end{cases}$
                - $\begin{cases}
                    \bar {xy}+m\bar {x^2} + b\bar x &= 0 \\
                    -\bar y + m \bar x + b &=0
                    \end{cases}$
                - $\begin{cases}
                    m \bar {x^2} + b \bar x &= \bar {xy} \\
                    m \bar x + b &= \bar y
                    \end{cases}$

                - $(\bar x, \bar y)$ & $(\frac{\bar {x^2}}{\bar x}, \frac {\bar {xy}}{\bar x})$ on least square regression line $\hat y = mx + b$

                - $\begin{cases}
                    m &= \dfrac{\bar x \bar y - \bar {xy}} {{\bar x}^2 - \bar{x^2}} \\
                    b &= \bar y - m \bar x
                    \end{cases}$
- Coefficient of determination R-squared
    - % of variation is described by the regression line
    - $\begin{aligned}
        R^2 &= 1 - \dfrac {SE_{line}}{SE_ {\bar y}} \\
            &= 1 - \dfrac {\sum {r_i}^2}{\sum (y_i - \bar y)^2} 
        \end{aligned}$

        - $SE$: squared error
        - $SE_{line}$ is small $\implies$ $R^2$ close to 1 $\implies$ good fit
    - Adjusted $R^2$
        - Corrected goodness-of-fit measure
        - Additional input varaibles will make $R^2$ stay the same or increase, even if no relationship
        - $R_{adj}^2 = 1 - \dfrac{(1-R^2)(n-1)} {n-p-1}$
            - $p$ = number of independent variables
- Standard deviation of residuals or Root-mean sqaure error RMSD
    - $S_{res} = \sqrt{\dfrac{\sum{(y_i - \hat y)^2}}{n-1}}$
- Inerpreting computer regression data
    - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220716223509.png" width="500" height="">
    - Regression line: $\hat y = mx + b$
        - y = hours studying
        - x = caffeine consumed
        - b = constant = 2.544
        - m = coefficient = 0.164
    - Measure of goodness of fit
        - S (standard deviation)
        - R-squared
        - Adjusted R-squared

### Study design

- Correlation vs causality
- Sample
    - Random sample
        - Simple random sample
            - Random digit table
        - Systematic random sample
            - Every nth
        - Stratified random sample
            - By Proportion of group
        - Clustered random sample
            - Cluster and randomly picl cluster
    - Non random sample
        - Voluntary sample -> bias
        - Convenience -> bias
- Qualitative and quantitative data
- Types of statistical study
    - Sample study
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220717122151.png" width="400" height="">
    - Obervational study
    - Experiment
        - Explanary variable
        - Response variable
        - Treatment
        - Experimental unit
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220717121958.png" width="400" height="">

### Probability

- P(A) = (# of ways A can happen) / (Total number of outcomes)
- Operation of sets
    - Empty set: $\empty$
    - Univeral set U
        - Real number: $\R$
        - Rational number: Q
        - Natural number: $\N$
        - Integer: $\Z$
    - Union (and): $X \cup Y$
    - Intersection (or): $X \cap  Y$
    - Relative complement: $X - Y = X / Y$
    - Absolute complement: $A' = U  - A$
    - Subset, strict subset, superset
        - Subset: $A \sube A$
        - Strict subset: $B \subsetneq A$
    - Conditional probability: $P(B | A)$ # B given A happens
- Theoretial and experimental probability
    - More experiments, experimental prob gets closer to theoretial prob
- Venn diagram
- Rules for probability
    - $P(A or B) = P(A) + P(B) - P(A and B)$
    - Compound probabiulity
        - Independent events: $P(A and B) = P(A) \cdot P(B)$
        - Dependent events: $P(A and B) = P(A) \cdot P(B | A)$
- Probability without eqaully likely events
