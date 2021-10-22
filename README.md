# Project 2: Ames Housing Data
---  

## Problem Statement:

As a consultant, I am tasked to analyse and present data to investors and home-builders who are looking to sell their construction projects to potential home-buyers.  

The current model which stakeholders are using is the general statistical metrics of annual houses, in particular the mean sales price of houses. Data in this field is rather assymetric as access to readily available factors of housing prices are not readily available.  

The objective of this model is to provide a more accurate prediction of a house's price based on the features of the house itself.  

In this analysis, we will be using Supervised Learning with Regression models.  

## Data Dictionary:

Please refer to this link for the data dictionary.
https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/data


## Additional Research Sources:
--- 
https://nycdatascience.com/blog/r/ames-iowa-real-estate-analysis/  
https://www.cityofames.org/about-ames/about-ames  

---
## Data Cleaning Process  

Generally all integer and float data are used directly.

Data columns that are ratings or gradings are set to a weight integer.

Data Columns that are string format that are classifiable but not weightable are dummied.

---
## Exploratory Data Analysis

### EDA: Check for outliers

Upon checking our saleprice with a boxplot, we find that there are quite a number of outliers. I have removed the outliers outright, as defined by the data point of saleprice being over 3 standard deviation increments away from the data mean point.

### EDA: Heatmap Features:

From the heatmap plotted, we find that the Exterior Quality, General Living Area, Garage Area, Years Built of the house contributes the most to the sale price of the house. From these we can find the relevant statistics of these relevant data in the columns to find out the general statistics of these features mentioned.

Also note that Garage variables seem to be strongly correlated to each other. Instead of getting rid of the outliers, I decided to feature them into a overall score to check for their correlation with respect to sale price. It has improved and is thus a strong factor.

### EDA: Sales Price:

We also notice that Sales Price is a normal distribution with a mean sales price of U$176420.69. 

---
## Modeling and Prediction

Our **target vector (y)** is our sales price of the house. The feature matrix is all other columns that is not part of the sales price.  

Applying train-test-split to our data, we found from cross validation that our lasso and ridge model seem to work the best with our data. We will pick a lasso model as our supervised learning model.

We have to scale our data as we are dealing with lasso regression.

We also observe the relevent data metrics of our model in the form of our R2 score, Root-Mean-Square Error (RMSE) and Mean Absolute Error (MAE) for both our training and test dataset.

Upon checking our highest absolute coefficients, we find that our top 10 factors affecting our sales price are the general living area, the overall quality of the house, the basement size, the location of the house within North Ridge and North Ridge Height, the years built, exterior quality, kitchen quality, basement exposure and the garage area.

Note that we also have removed the miscellaneous features for elevators and clay tile roofs as they are extremely rare even though they do affect the price of the house very significantly.

From our residuals vs predicted, we find our data to be relatively centered around the y=0 line, indicating that our model is quite accurate at predicting the price of a house for sale. 

Also note that our findings during the coefficients also coincides with findings found by further research done on the Ames area. (Please refer to *Additional Research Sources* for relevant article links)


## Conclusion and Recommendations
---
From our data, it is clear that there are several factors that contributes to the sales price of a house in AMES. In particular the following:

General Living Area
Exterior Quality
Overall Quality
Garage Space
Location within Northridge Area

Generally, it is recommended to maximise the house living area, and the invest in landscaping and exterior renovation to maximise the exterior of the house. It is also advisable to have a larger garage and to construct the house with generally good quality materials and furnishings/fixtures. It will also be good to attempt to bid for lots and areas within the Northridge area as they contribute to a higher sale price.

Also, it might be advisable avoid special fixtures like elevators and clay tiles, they may significantly affect the sales price of the house, although it may be rare.