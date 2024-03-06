# Used_Car_Prices
Regression Model to predict used car prices

## Introduction
### 1.1 Background of the Study

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

### 1.2	Significance of the Study

As the used car market is globally increasing, it is important to have a proper way to predict the used car prices according to the features of the car for both buyers and sellers. Then they will be able to know the actual demand value of the cars and avoid the unnecessary money expenses. And also used car owners will be able to directly sell their cars to buyers without help from third party persons.

## 2	Methodology

### 2.1	Exploratory Data Analysis

Visually represent the information and data by using graphs. This is important because it allows trends and patterns to be more easily seen and make data easier for the human brain to understand. Data visualization provides a quick and effective way to communicate information in a universal manner with complicated and massive amounts of data. In this study there are both quantitative and categorical variables, and for the univariate analysis boxplots and histograms were used to represent quantitative data and pie charts were used to represent categorical data as the number of categories are small in every categorical variable. Under the bivariate analysis considered the relationships between dependent variable and independent variables and boxplots and scatterplots were used

### 2.2	Advanced Analysis

Multiple linear regression (MLR), known simply as multiple regression, is a statistical technique that uses several explanatory variables to predict the outcome of a response variable. The goal of multiple linear regression (MLR) is to model the linear relationship between the explanatory (independent) variables and response (dependent) variable.
In essence, multiple regression is the extension of ordinary least-squares (OLS) regression because it involves more than one explanatory variable and the model is based on the following assumptions:
•	There is a linear relationship between the dependent variables and the independent variables
•	The independent variables are not too highly correlated with each other
•	yi observations are selected independently and randomly from the population
•	Residuals should be normally distributed with a mean of 0 and variance σ
The equation for this model is as follows with p independent variables X1, X2, …,Xp. 
        where, for i=n observations
Multiple linear regression model was used to fit the model for the dataset by considering used car price as the dependent variable and all the other variables as explanatory variables. Backward elimination was used as the feature selection. Residual analysis was done to check the assumptions of the model and VIF values used to check the multicolinearoty. R square and RMSE value used to check the accuracy of the model. 


## 3	DATA

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
	
### 3.2	Data Preparation

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

## 4 Exploratory Data Analysis
The detailed Exploratory Data analysis of the study can be found on the folder 'EDA'.

### 4.1	Price
  
Figure 4 1 Boxplot of Price and summary statistics of price

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Bixplot_Price.png)

Figure 4 2 Histogram of price

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Picture1.png)

Price is the response variable of the study and it represents the car price of used cars. According to the histogram, it can be seen that price is unimodal positively skewed. Range of the car prices are spread between 4k and 32k and 9900 is the median value. According to the Boxplot it can be clearly seen that there are many outliers and among them 3 are highly deviated outliers. But there is not enough evidence to remove those outliers. And also it can be seen that 50% of the prices are between 8k and 12k.

### 4.2 Correlation Matrix
 
Figure 4 2 Correlation Matrix (Heat Map)

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/correlation%20matrix.png)

By considering the correlation matrix, relationships among quantitative variables can be clearly seen. Pearson correlations among them have been calculated. According to this also it can be observed that variables Age has a strong relationship and KM and weight has moderately strong relationships with the Price. Doors and CC have weak positive relationships with Price and there is a moderately strong relationship between CC and Weight according to the correlation matrix. 
Correlations between Price and categorical variables “Automatic” and “MetColor” were calculated by using the Point- biserial Correlation and there were respectively 0.0339 and 0.1076 correlations. Thus there are weak positive relationships between Price and the Automatic and, Price and the metColor. 

## 5	Advanced Analysis

To predict the Price of used cars Multiple Linear Regression Model is used. Variable “Price” is considered as the response variable and all the other variables are considered as independent variables. Among them “MetColor”, “Automatic” and “FuelType” were categorical variables and dummy variables were created for them. For the variable “FuelType” category “CNG” was considered as the base level and  for variables “Automatic” and “Metcolor”, categories “Not Automatic” and “Not Metallic Color” were used as base levels respectively. 

An important part of predictive modelling is the careful partitioning of available data. When separating the data set into a training set and test set, 80% of the data used for training and 20% of the data is used for testing. 

Table 5 1 Data Sets
|Name of the dataset	|Number of Observations|
|-----------------------|----------------------|
|Train set	|1148|
|Test set	|287|

After the model has been processed by using the training set, the model is tested by making predictions against the test set. 

### 5.1	Model 1 

 fit the model for the train set, backward elimination was used as the feature selection method by considering the 0.05 as the significant level. Then following variables were obtained. 
'Age', 'KM', 'HP', 'Auto_Automatic', 'CC', 'Weight', 'FT_CNG', 'FT_Diesel'

Then the model was fitted using the above selected variables as independent variables and the variable “Price” as the dependent variable. 

Table 5 2 Regression Results Model 1
 
![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/RegressionResultsModel1.png)

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Regression%20Results%20Model1.1.png)


Model was fitted with a high R square value (0.879). Thus 87.9% of the variability of response variable is explained by the model. And the overall model also significant at 5% level with 0.00 F- statistic. When considering the significance of variables all the variables are significant at the 5% level as all the p values are less than 0.05. 

![pp plot](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/PP%20Plot%20M1.png) <img src="https://github.com/Sehaniw0802/Used_Car_Prices/assets/66731646/3c7e57c1-b413-4098-9baa-0bb0a65f2cc9" width="50%" height="50%"> Standerdised residuals vs standerdised predicted value plot model2

When considering the model assumptions it can be seen that residuals are normally distributed (figure 5-1) according to the normal probability plot. But when considering the standardized residuals vs. fitted values (Figure 5-2), it can be seen that residuals are not randomly distributed and there is a curve shape. Thus the model is not adequate. And also there are few points which can be identified as outliers since they lie beyond the -2 and +2 levels. 
					 
![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/VIF%20M1.png) VIF value model 1

When considering the VIF values. It can be seen that there are 3 variables called “HP”, “CC” and “FT_Diesel” which have VIF values greater than 5. Therefore it can be said that there is multicolinearity between the independent variables. 

So because of the model assumption errors and the existence of the multicollinearity, to predict the used car prices in a more accurate way modifications for the obtained model is needed.

### 5.2	Model 2

Due to the skewness of the response variable and with need of model modifications, the response variable is transformed into log transformation and refits the model for the train set using backward elimination with 5% level of significance and by using log_price as the dependent variable and all the other variables as independent variables. Then the following variables were obtained as independent variables of the model.

'Age', 'KM', 'HP', 'Auto_Automatic', 'Weight', 'FT_CNG'

As the variable “FT_CNG” is a dummy variable, consider the dummy variable “FT_Diesel” also as an independent variable and refit the model by using all the above variables as independent variables and the variable “log_price” as the dependent variable.

Table 5 4 Regression Results Model 2
  
 ![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Regression%20Results%20Model2.png)

 ![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Regression%20Results%20Model2.2.png)

According to the model results (Table 5-4), Model has a high R square value (0.857) Thus 85.7% of the variability is explained by the fitted model. And the overall model is significant at 5% level with 0.00 F-statistic value. Except for the dummy variable “FT_Diesel” all the other variables are significant at 5% level. 

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/PP%20Plot%20M2.png)

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Std%20resuiduals%20vs%20fitted%20value%20M2.png)
 
When considering the model assumptions, it can be seen that residuals are normally distributed according to the probability plot and it has a perfect normal distribution than the model 1 residuals. Plots of the standardized residuals vs. standardized predicted values graph are randomly scattered and the presented curve shape of the first model also has been removed. In both models outliers are present. Therefore, according to the results of residual analysis model 2 is better than model 1.

     Table 5 5 VIF values of model 2
 
![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/VIF%20M2.png)

When considering the VIF values, all the variables VIF values are less than 5 for all variables. Thus multicollinearity does not exist in the second model. Therefore when shifting from model 1 to model 2, problems that occurred due to multicollinearity have been removed.

### 5.3	Comparison Between two models

Table 5 6 Model summaries

|Model	|Dependent Variable	|Adj. R Square value	|No. of variables	|Multicolinearity|
|-------|-------------------|-----------------------|-------------------|----------------|
|Model 1 	|Price	|0.879	|8	|Exist |
|Model 2	|Log_price	|0.857	|7	|Doesn’t exist|

When comparing the above 2 derived models, Model 1 has a higher adjusted R square value than the model 2. But both the adjusted R square values are high. When considering the no. of observations of two models, Model 1 has 7 variables and Model 2 has 8 variables. Thus model 2 is simpler than model 1. 

Table 5 7 Correlation between Price and quantitative variables

![Alt text](https://github.com/Sehaniw0802/Used_Car_Prices/blob/main/Images/Correlations%20comparison.png)

When looking at the model variables Model 1 consists variable “CC” other than the model 2 variables. So investigation of the relationship between the variable “CC” and the dependent variable “Price” is important. The correlation between variable “Price” and the “CC” is 0.18125. So there is a weak positive relationship. Thus according to this data set, variable “CC” which is engine capacity does not make a huge impact on the car price. So not containing the variable “CC” by model 2 will not make a huge impact on the price of the cars. 

When considering two models’ assumptions both models’ residuals are normally distributed. But model 2 residuals have a perfect normal distribution than model 1. As model 1 standardized residuals vs. standardized fitted value plot shows curve pattern model 1 is not adequate while model 2 plots are randomly scattered. Thus model assumptions are satisfied by model 2 rather than model 1.
When considering the VIF values also, model 1 there exist multicollinearity and in model 2 multicollinearity does not exist as all VIF values are less than 5. 
So by considering all these things model 2 can be considered as the best fitted model for the prediction of used car prices compared to model 1. 
The calculated RMSE value by using the test set for the model 2 is 0.136. So as there is a very small RMSE value, it can be also said that model 2 is appropriate. 
As in model 2 coefficient of variable “KM” is very small, divide the variable by 1000 and re-fit the model by using backward elimination. Then the same results were obtained as model 2. Same residuals plots and VIF values obtained. Only change was the variable “KM” coefficient multiplied by 1000. 
So according to this dataset best fitted model to predict the used car price is,

log(price) = 8.587 – 0.0105(Age) – 0.0017(KM) + 0.0025(HP) + 0.0393(Auto_Automatic) +                   0.0010(Weight) – 0.0741(FT_CNG) + 0.0120(FT_Diesel)

Here values for variable “KM” should substitute as km per 1000 and, after computing the value for response variable “log_price” by substituting the values for independent variables, to get the used car price antilog of variable “log_price” must be calculated.        





