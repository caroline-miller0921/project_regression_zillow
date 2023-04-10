Regression Project - Zillow_2017

Goal: Identify key drivers of home value for Single Family properties within Orange, Colusa, and Los Angeles Counties, and to create a model which can predict the home value better than the baseline predictions. Home values represent a great and costly investment for home owners, banks, and real eastate companies. The flucuation in the real esatte market directly affects our business and our customers. It is important to track trends and drivers of home values in order to maintain a continous understanding of a market which has proven to be volatile.

Project Description: This project analyzes historical data from our company to find correlation between variables which we track and the tax value. The data specifically looks at homes in three California counties which sold in 2017. The variables assessed include the age of the property, the sqaurefeet, the number of bedrooms and bathrooms, and the county in which the property is located. Through this data analysis, I identify key drivers. I then use those key drivers make a predictive model.

Business Goals

1. Construct an ML Regression model that predict propery tax assessed values ('taxvaluedollarcnt') of Single Family Properties using attributes of the properties.
2. Find the key drivers of property value for single family properties. Some questions that come to mind are: Why do some properties have a much higher value than others when they are located so close to each other? Why are some properties valued so differently from others when they have nearly the same physical attributes but only differ in location? Is having 1 bathroom worse than having 2 bedrooms?
3. Deliver a report that the data science team can read through and replicate, understand what steps were taken, why and what the outcome was.
4. Make recommendations on what works or doesn't work in prediction these homes' values.

Initial Questions and Hypotheses:
I hypothesize that the home value increases as the property size increases. The tax value will correlate with the number of bedrooms and bathrooms and the squarefeet of the property. The average home value will vary between the houses loacted in each county. I question what the distributions of home values looks like for each of the counties and which county contains the highest hmoe values. I hypothesize that the age of the properties will not be key driver behind the home value as the housing market in these counties is fairly competitive and properties are in demand (assuming the properties listed on Zillow are quality constructions). 

Plan:  Acquire and prepare a dataframe which contains three datasets from the MySQL dataframe 'zillow'. Explore the features against the target variable using visulaiztions, statistical testing, and data wrangling to identify and confirm correlation between drivers and thr target variable. Answer the businiess questions listed above through data exploration. With the correlative features, construct models fit on a scaled train dataframe using Linear Regression to generate predictions. Evaluate the predictions of the models on the train and validate datasets. Determine the best performing model, and test the model on unseen data. draw conclusions. determine the nest steps to be taken, and identify any recommendations. 

Data Dictionary
Object Returned	Description	Purpose
1. bedrooms	Feature and dependent variable, number of bedrooms within the property	float64 datatype
2. bathrooms	Feature and dependent variable, number of bathrooms within the property	float64 datatype
3. squarefeet	Feature and dependent variable, area of the property	float64 datatype
4. tax_value	Target and independent variable, Unscaled, measured in USD	Feature selection, evaluate model predictions, float64 datatype
5. yearbuilt	Feature and dependent variable, year the property was constructed	int64 datatype
6. taxamount	Feature and dependent variable, percentage of tax_value, relative to tax_va;ue, measured in USD	float64 datatype
7. fips	Feature and dependent variable, number representing a State and county in which the property is located	int64 datatype
8. propertytypeid	Feature and dependent variable, number representing the type of construction accoring to Zillow standard procedures	int64 datatype
9. transactiondate	Feature and dependent variable, year in which the property was purchased by a customer (within 2017)	datetime64 datatype
10. fips_location	Feature and dependent variable, State and county in which the property is located	object datatype
11. property_age	Feature and dependent variable, difference between year the property was constructed and year in which the transaction was made (2017)	int64 datatype

Steps to Reproduce:
1. Ensure you have an env.py file containing your MySQL username, password, and host information and that you have saved the wrangle.py file into the same local repository
2. Acquire the dataframe from MySQL using the wrangle.py function 'get_zillow_2017()'
3. Split the dataframe into train, validate, and test datasets using the wrangle.py function 'prepare_zillow()'
4. Conduct univariate, bivariate, and multivariate exploration based on your hypotheses and initial questions or business questions (please see functions within wrangle.py)
5. Use feature engineering if necessary
6. Determine the features you'd like to use in training and fitting your model
7. Scale the features using the wrangle.py function 'scale_data()'
8. Determine your baseline model using the median or mean of your target variable or a preexiting model; determine the evaluation metrics of baseline model
9. Construct models which predict continuous values (i.e. Regression models), using parameters which lead to best performance
10. Evaluate each model's performance 
11. Determine the best model
12. Test the model on the unseen test dataset
13. Make conclusions, confirm or reject hypotheses, and answer initial questions
