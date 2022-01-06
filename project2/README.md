# Project 2 - Ames Housing Data and Kaggle Challenge


## Problem Statement 
Following the record breaking sale of houses during the summer, it looks like the housing market in Iowa seems to be slowing down. [(source)](https://www.weareiowa.com/article/news/local/after-another-record-breaking-month-iowa-realtor-describes-perfect-storm-housing-market-jen-burkamper/524-b0d79923-32d4-4c82-a6a5-de3c10afbc02)

According to a Ted Weaver, a realtor based in Iowa, ["if you're priced appropriately, you can sell within the first week."](https://www.weareiowa.com/article/money/iowa-real-estate-updates-homeowner-buying-selling-process-realty-tips-september-2021-homes-for-sale/524-c348c4bd-838b-4d27-8b6a-f4fb3a9ab2f9) How then should potential home owners price their houses without going through the long process of getting a realtor to valuate their homes? 

This project aims to solve that problem, by trying to automate pricing of houses based on statistically important features. Through machine learning, we hope to be able to help expedite the sale of houses, while ensuring that home owners looking to sell their homes get the best value for their property.

---

## Contents

* [Training data - cleaning](#link1)
* [Training data - EDA](#link2)
* [Test data - cleaning](#link3)
* [Modelling](02_modelling.ipynb)
* [Recommendations](02_modelling.ipynb#link4)

---

## Data Sets

* [`train.csv`](datasets/train.csv) -- original training data for model
* [`test.csv`](datasets/test.csv) -- test data for model. These will be used to predict housing prices.

#### Data Dictionary
* [`source from Kaggle`](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/data)

--- 

## Model Summaries

Model Name | Training Score | Testing Score | RMSE
-|-|-|-
Baseline/Null Model|0%|0%|80,473
Linear Regression (Overfit)|90.5%|89.8%|25,746
Ridge (with intera tion)|89.8%|89.2%|26,476
Lasso (with interation)|89.7%|89.1%|26,562
Lasso Regression (Dropping collinear features)|89.4%|88.4%|27,000

--- 

## Model Analysis

We have chosen the 3rd iteration of Lasso although RMSE score is slightly higher, as we do not want the data to be overfit with multi-collinear variables. Looking at the regression plot, we can see that the line passes through most data points. 

At higher prices, namely those above 300,000USD we can see that there are a couple of data points that lie outside the confidence interval, suggesting that our model might not be accurate when predicting houses of very high values. This is mirrored by the residual plots - at house prices below 300,000USD there is an equal number of residuals on both sides of the line.

However, these high value houses only represent 8% of the entire dataset. They are quite rare, and for the general population wanting to sell their house, the model would still work relatively well.

The regression models are far from perfect, but is able to account for about 88.7% of the variation in sale price, and able to predict the prices within approximately 27,000USD.

--- 

## Recommendations

Looking at the features for the predictive models, the top few features seems plausible. For example, living area and overall quantity are features that are commonly known to affect sales price. Similarly, new houses tend to be postiviely correlated with sales prices as well. 

With respect to prospective sellers, they should take the valuations from this model with a pinch of salt as it only explains 88.7% of the variation with relation to price. To err on the side of caution, they could add 27,000 USD to the price generated, to account for negotiations from prospective buyers as well. If the prices generated are above 350,000 USD, they probably should get a realtor for a physical valuation instead.

In addition, if people are looking for property investments, here are some things they could look out for (assuming living area and quality cannot be controlled): 

- Properties in Northridge Heights
- Stone masonry veneer type houses
- Ensure garages are not attached 
- Houses with a porch
- Newer houses
- Foundation made from poured concrete 
- Central air conditioning

--- 
## Model Limitations and Future Improvements

### Limitations
- There were many null values that were imputed based on highest value counts, which might not be an accurate reflection of the true data
- Model would be more accurate with more features/interaction terms, however this would make it less interpretable to the target audience

### Improvements
- To consider a separate model that drops the house price of above 300,000. We could also examine what are the factors important to houses above 300,000
- Taking into account inflation of house prices, as our data set was collected over a few years
