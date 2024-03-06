# Used_Car_Prices
Regression Model to predict used car prices

1.1 Background of the Study

The prices of new cars in the industry is fixed by the manufacturer with some additional 
costs incurred by the government as taxes. So buying a new car can be considered as a money 
investment. But due to the increased price of new cars some customers are not able to buy a new 
car with their budgets. But nowadays people like to spend more comfortable lives with their busy 
schedules. So almost every person tends to buy a car for their ease. So because of that, they tend 
to buy used cars according to their needs and funds.
But the used-car market is also booming and making it a good time for sellers, but not so 
much for buyers. With the economy reviving and also a shortage of new cars because of a global 
chip shortage, demand and price of new cars are surging. So it is important to know the actual 
market value of used cars for both buying and selling. Because these used cars’ market value 
depends on many factors such as miles on the car, age of the car, conditions of the car and many 
more. When buying a used car, consideration ofsome facts is important because some cars actually 
appear to be brand new but they could probably have some problems. Therefore identifying the 
facts that should be considered when buying a used car and according to those factors determining 
the car price is very useful. In addition, nowadays most used cars are sold through third party 
people. So because of that also car prices have increased more than its actual value. But if buyers 
have a proper way to predict the car prices, they will be able to limit the increasing prices due to 
third party persons. And also there are lots of individuals who are interested in the used car market 
to sell their car or buy a used car. Therefore, because of the above discussed factors there is a need 
for a used car price prediction system to effectively determine the worthiness of the car using a 
variety of features

1.2	Significance of the Study

As the used car market is globally increasing, it is important to have a proper way to predict the used car prices according to the features of the car for both buyers and sellers. Then they will be able to know the actual demand value of the cars and avoid the unnecessary money expenses. And also used car owners will be able to directly sell their cars to buyers without help from third party persons.

2	Methodology

2.1	Descriptive Analysis

Visually represent the information and data by using graphs. This is important because it allows trends and patterns to be more easily seen and make data easier for the human brain to understand. Data visualization provides a quick and effective way to communicate information in a universal manner with complicated and massive amounts of data. In this study there are both quantitative and categorical variables, and for the univariate analysis boxplots and histograms were used to represent quantitative data and pie charts were used to represent categorical data as the number of categories are small in every categorical variable. Under the bivariate analysis considered the relationships between dependent variable and independent variables and boxplots and scatterplots were used

2.2	Advanced Analysis

Multiple linear regression (MLR), known simply as multiple regression, is a statistical technique that uses several explanatory variables to predict the outcome of a response variable. The goal of multiple linear regression (MLR) is to model the linear relationship between the explanatory (independent) variables and response (dependent) variable.
In essence, multiple regression is the extension of ordinary least-squares (OLS) regression because it involves more than one explanatory variable and the model is based on the following assumptions:
•	There is a linear relationship between the dependent variables and the independent variables
•	The independent variables are not too highly correlated with each other
•	yi observations are selected independently and randomly from the population
•	Residuals should be normally distributed with a mean of 0 and variance σ
The equation for this model is as follows with p independent variables X1, X2, …,Xp. 
        where, for i=n observations
Multiple linear regression model was used to fit the model for the dataset by considering used car price as the dependent variable and all the other variables as explanatory variables. Backward elimination was used as the feature selection. Residual analysis was done to check the assumptions of the model and VIF values used to check the multicolinearoty. R square and RMSE value used to check the accuracy of the model. 


3	DATA

In this study collected dataset of used cars is being used and it contains 1436 cases of data and 10 variables. Variable description is as below and variable ‘Price’ is used as the response variable.
3.1	Variable Description
Table 3 1 Variable Description
|Variable	|Description	|Variable type|
|-----------|---------------|-------------|
|Price	|The price of the car in dollars	|quantitative variable|
|Age	|The age of the car in months	|quantitative variable|
|KM	|How many kilometers did the car was used	|quantitative variable|
|FuelType	|Type of Fuel	|categorical variable|
|HP	|Horse power of the car	|quantitative variable|
|MetColo	|Whether car has metallic color or not	|categorical variable|
|Automatic	|Whether car has automatic transmission or not	|categorical variable|
|CC	|The engine size of the car	|quantitative variable|
|Doors	|The number of doors in the car	|quantitative variable|
|Weight	|The weight of the car in kilograms	|quantitative variable|
	
3.2	Data Preparation

Here in the dataset there were 1 duplicate observation. So it was removed from the dataset. And also there were 10 missing values as below. 
Price        0
Age          2
KM           0
FuelType     4
HP           0
MetColor     0
Automatic    0
CC           2
Doors        0
Weight       2

Since variables ‘Age’, ‘CC’ and ‘Weight’ are quantitative and have skewed distributions, there were imputed by the median imputation. The categorical variable which is ‘FuelType’ was imputed by using the mode imputation. So after preprocessing the dataset there were 1435 observations and 10 attributes.


