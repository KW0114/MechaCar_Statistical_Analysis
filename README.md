# MechaCar Statistical Analysis with R

## Overview 

The purpose of this module was to learn the basics of R in order to perform statistical tests on data sets
for analysis. R makes statistical testing extremely easy, as it was written by mathematicians specifically
for these jobs in mind. 

In this project includes:
* Multiple Linear Regression using the lm() function
* Created summary statistic tables for PSI, including a grouped version by lot number
* T-tests to determine if our sample populations differ statistically from the population
* A design for a statisical study that would quantify a relationship with the data that customers would be interested in

## Linear Regression to Predict MPG

Here is the result of the lm() call with every variable included in the table vs. mpg:

![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/8c176185bad5aa228d6fdaf3ef771c75cf45f4ac/Resources/linear_regression_screenshot.png)

Our main points of interest from this output will be the p-value column, and the r-squared value. 

1. For p-values, we are interested in numbers **less than** the normal significance level of 0.05.
As you can see above, the vehicle length and ground_clearance variables both have p-values within this range,
which means that these two variables have a statistically significant impact on the miles per gallon.

2. Looking at the bottom right, we can see the p-value for this model is 5.35e-11, which is smaller than our
0.05 significance level. This means that we have sufficient evidence supporting that there is correlation
happening in this linear model, and the slope will not be zero.

3. The r-squared value is 0.7149, meaning approximately 71.49% of mpg predictions not represented in our dataset
could be determined by this model, so it is fairly effective at predicting mpg og MechaCar prototypes. 
