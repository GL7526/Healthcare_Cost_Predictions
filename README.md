# Healthcare Cost Predictions
This repository is dedicated to a project between myself and George Lin (gl7526 on github) which attempts to predict the annual cost of healthcare for people who have employee-sponsored insurance between 2013 and 2017 depending on their class of treatment (inpatient, outpatient, etc.). We applied multiple linear regression models to capture the data and chose the optimal one. 


The data are totals for specific treatments between 2013 and 2017 as given by the Heath Care Cost Institute. The data can be found under "Public Data" and in the link "Annual Report Dataset" in the following webpage: https://healthcostinstitute.org/data

- [Project Goal](#ProjGoal)
- [Preview Data](#LookAtDep)
- [Scatterplot With An Independent Variable](#EDA)
- [Distribution of Residuals](#DistRes)
- [Big Takeaways](#Takeaway)
<br>

## Project Goal <a name = 'ProjGoal'></a>
The purpose of this project is to predict an accurate cost for the price of a medical treatment. These treatments include things such as prescriptions, vitamins, office visits, surgeries, etc.
<br>
<br>

## Preview Distribution of Dependent Variable <a name = 'LookAtDep'></a>

<center><img src='graphs%20of%20data/distribution_of_annual_cost.png' width = 400></center>
The first thing we did was look at the distribution of the dependent variable. This gives us a quick estimate of where the lowest and highest values lie and which values occur the most. This can help us determine whether or not there are extreme outliers that we may want to remove, but since we have a small sample size, we decided against removing too many.


## Annual Cost of Treatment vs. Number of Uses of Treatment <a name = 'EDA'></a>

<center><img src='graphs%20of%20data/cost%20vs%20utilization.png' width = 400></center> <!-- center isn't working, probably deprecated; might be able to fix by referencing this tag in CSS?  // Annual Cost of Treatment vs. Use of Treatment-->

From this, we can vaguely see that generally, as the number of times the treatment is used, the more it will cost.

## Distribution of Residuals <a name = 'DistRes'></a>

<center><img src='graphs%20of%20data/dist%20of%20resids.png' width = 400></center>

One of the assumptions of linear regression is that the residuals of the dependent variable should be homoscedastic and should therefore follow a normal distribution when plotted by frequency, which is graphed in the image above.
<br>
<center><img src='graphs%20of%20data/qqplot.png' width = 400></center>

Another way to view the distribution of the residuals of the dependent variable is by a qqplot. From this, we see that the values of the residuals aren't "well distributed" and clusters right below 0. This tells us that the residuals probably do not follow a normal distribution.
<p>However, these graphs are mostly eye tests. For a more quantitative test for the normality of the residuals, we used the Jarque Bera Test, which told us that the probability of the distribution of our residuals following a normal distribution is "2.551202e-128," or nearly impossible.</p>
<br>
<p>Despite lacking normality in the distribution of the residuals, this model is just a tool for prediction. Most models don't start with perfectly clean data and ours can still give very accurate results.</p>

## Big Takeaways <a name = 'Takeaway'></a>

After creating various models and testing them against each other by using the mean absolute error as a metric of comparison, we find that our Ridge Regression Model does the best by a small margin.
