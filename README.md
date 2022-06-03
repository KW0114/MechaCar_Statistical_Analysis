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

## Summary Statistics on Suspension Coils

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch.

![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/4751a5905fb8fb79d63e0082a14e6cfe803300f8/Resources/total_summary_table.png)

If we were just looking at the entire dataset together (the table above), then we could say that, as a whole, this condition is met because the variance
is 62.3, which is less than 100.

![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/4751a5905fb8fb79d63e0082a14e6cfe803300f8/Resources/lot_summary_table.png)

However, when we separate each lot and look at the summary stats individually, lot 3 does not satisfy this condition, with its variance in PSI coming in at
170.3. As you can also see, the other two lots have extremely low variance values in comparision to this, which is most likely why the overall dataset 
passed the condition.

## T-Tests on Suspension Coils

For our t-tests, let us assume the null hypothesis states that our sample mean(s) match the population mean of 1500. Of course, which means the alternative
states that at least one of our means differ from the population mean.

**Overall T-Test**
![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/4751a5905fb8fb79d63e0082a14e6cfe803300f8/Resources/overall_t_test.png)

When testing the overall dataset against the population, we get a p-value of 0.06, which is much above than the normal 0.05 significance level.
So there is sufficient evidence supporting our null hypothesis, so we will fail to reject it. The confidence interval is also extremely small in range,
which makes this claim even more valid. 

**Lot 1 T-Test**
![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/4751a5905fb8fb79d63e0082a14e6cfe803300f8/Resources/lot1_t_test.png)

When testing lot 1, our p-value is exactly 1. This is the highest possible value we could get. This is because when you look at our summary stats for
lot 1, the mean is indeed exactly 1500, so we will fail to reject the null hypothesis.

**Lot 2 T-Test**
![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/d98007127f95a3c263df233c0cf95857ea1ea47b/Resources/lot2_t_test.png)

When testing lot 2, the p-value is 0.6, which is much higher than 0.05. We will again fail to reject the null hypothesis, there is sufficient evidence supporting
the fact that there is no statistical difference between the mean of lot 2 and the mean of our population.

**Lot 3 T-Test**
![screenshot](https://github.com/KW0114/MechaCar_Statistical_Analysis/blob/d98007127f95a3c263df233c0cf95857ea1ea47b/Resources/lot3_t_test.png)

When testing lot 3, the p-value is 0.04, which is below our threshold of significance. For this lot, we will reject the null hypothesis and favor the alternative,
that there is a statistical difference between the mean of lot 3 and our population mean of 1500.

## Study Design: MechaCar vs Competition

The metric that I decided to focus on for this study is city and highway fuel efficiency, so I would be performing two tests.

The null hypotheses: City and highway fuel efficiency for MechaCar prototypes exceed that of the competitor brand.
Alternative: City and highway fuel efficiency for MechaCar prototypes is less than or equal to its competitor brand.

For this study I would perform a two-way T-test comparing the mean city fuel efficiency (then another one for highway) to the mean
efficiency of the competitor brand. This is the best test of the ones covered in this module because it is dichotomous, and includes
numerical data (as is used in the hypotheses).

We would need a sample of cars from MechaCar to test their fuel efficiency. I am guessing we would not readily be able to access a similar
sample from the sompetitor, so we may simply need to use the efficiency rate advertised by that company.
