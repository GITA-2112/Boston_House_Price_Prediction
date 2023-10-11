# Boston_House_Price_Prediction
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/331ac9b0-03e7-4017-88fc-63054d97065f)

## Background Story 
Purchasing a house,  one of the most significant decisions of your life. It's a decision that will shape your family's future, influence your daily life, and have financial implications for years to come. But in the ever-evolving real estate market, how do you determine the right price for a property? This is where the science and art of predicting house prices become crucial. 

Let's delve into why this prediction is so crucial and explore the compelling reasons behind its urgency :
1. Financial Security, between homeowners and real-estate ensuring purchasing not oversale or undersale
2. Investment Decision, accurate predictions enable them to identify properties that will appreciate in value over time, allowing them to grow their wealth.
3. Affordability, this knowledge empowers them to explore options that align with their financial capabilities.
4. Fair Transactions, predicting house prices ensures that buyers and sellers are on an equal footing, facilitating transparent, ethical, and mutually beneficial deals.

## Objective : Best Models for House Price Prediction
   
## Dataset Overview
The data is about predicting housing price MEDV (Median value of owner-occupied homes) in Boston city
Other colums :
*   Criminal rate (crim)
*   Residential land zoned proportion (zn)
*   Non-retail business acres proportion (indus)
*   Is bounds with river (chas)
*   Nitrogen oxides concentration (nox)
*   Number rooms average (rm)
*   Owner age proportion (age)
*   Weighted distance to cities (dis)
*   Accessibility index (rad)
*   Tax rate (tax)
*   Pupil-teacher ratio (ptratio)
*   Black proportion (black)
*   Percent lower status (lstat)

## Exploratory Data Analysis

### Positive & Negative Correlation
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/d0399d1d-9128-409e-9391-c35b4c00b90b)
- The positive correlation (Except : MEDV) is RM which is average number of rooms per house. This is saying that as the average number of rooms increase, the MEDV value of the house tends to increase.
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/2e7c2146-f1d2-4c4e-97c0-bfd5a53d6e36)
- The negative correlation is LSTAT which is -0.74, LSTAT (% lower status of the population), so this is saying is as the % of lower status of the population increases for a house, the MEDV value of the house tends to decrease.
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/d713e0d9-6b54-4db5-a982-78d6f2957ac9)

### Descriptive statistics
Here the summary :
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/456fd3bf-6797-47a2-acd3-3c2cf7aface8)

#### One and only a categorical variable is bounds with river (chas), which is is apparently also binary (0,1)
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/0ebeed27-b8f6-482c-b891-18408e9cab63)

#### There are some outliers in data
Implementing "StandardScaler" for data transformation technique used to scale or normalize the features.
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/6b1c1362-a512-4506-a8bd-9a2f4641570d)

### Data Pre-processing
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/1a617a6a-3bda-4040-9e5f-4ff24d4db7d7)

### Feature Selection
A high VIF (Variance Inflation Factor), it indicates that the feature has a strong correlation with other features in the dataset. This can be an indication that the feature may not be necessary in the model or that there is redundancy of information among these features. In some cases, removing features with high VIF can improve the model's performance or make it easier to interpret.

![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/e959768d-ed4e-4f3d-8f73-fabe50a40207)

- Heatmap Correlation to determine, which column should be drop.

![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/64a0fe27-2690-48ce-9952-6538b5640999)

- After drop 'RAD' column, the VIF score shows :

![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/1c7f9002-cdf5-4a81-abee-82edb1cc850c)

## Machine Learning Models
- Ridge Regression
  
- Lasso
  
## Metrics Evaluation
- A lower RMSE indicates that the model's predictions are closer to the actual prices, which reflects the model's predictive accuracy.
  
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/e400e3c2-cffc-4dfe-ba49-8c0b9d3e19c8)

"Best Model - Ridge Regression, RMSE of Ridge regression model with alpha = 10 is 4.871717983886228"

## Diagnostic Study
1. Validating Assumptions: Diagnostic studies help validate. Researchers often have initial hypotheses about what might be causing a problem, and a diagnostic study helps test these hypotheses.

2. Monitoring and Evaluation: Diagnostic studies can serve as a baseline for ongoing monitoring and evaluation.

### R2_Score : 
Insight : A high R2 indicates that the model explains a large portion of the variability in house prices, which is desirable. It provides insight into the goodness of fit of the model.

![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/e2d22c1f-0d4a-4d16-846e-03b63c0a2260)

### Residual
Insight : The smaller the residual distribution, the model shown has good performance. Ideally, the residual should be close to zero line, meaning the model is almost perfect at predicting the data.

#### Residual - Ridge Regression
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/2dc0175c-2d93-430b-9370-3361bb1ed16b)

#### Residual - Lasso
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/1229861d-e192-4bbb-95c8-1b0c7932b0cb)

#### Metrics Evaluation - Ridge Regression 
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/099858c3-488e-46bd-baeb-bb0a79ce6966)

#### Metrics Evaluation - Lasso
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/0e87edfd-8cf1-4231-9d54-d95b91ef8514)

MAE and MAPE provide valuable insights into the accuracy of your model's predictions.

In summary, A lower MAE and a lower MAPE indicate better model performance, as they suggest that the model's predictions are closer to the actual values.


## Result
### MEDV & Predicted Value 
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/1f67eff8-ac64-4b9c-9efa-48688578c5c4)

### Table Comparison 
![image](https://github.com/GITA-2112/Boston_House_Price_Prediction/assets/135007275/9ab185cc-8343-41a0-95d1-f0a2ab26e4ad)

## Conclusion
Based on the observation of RMSE, MAPE, and MAE values, the machine learning model that performs better is Ridge Regression compared to Lasso. While the scatter plot of actual vs. predicted values may appear somewhat similar, it is evident that the data points are closer to the y = x line in Ridge Regression. For a non-technical perspective, the comparison table is easy to interpret. The distribution of predicted prices between Ridge Regression and Lasso is notably different in sample number 385, when Ridge Regression produces predictions that closely align with the actual values, while predictions made using Lasso tend to under sale. On the other hand, some samples also exhibit overselling and underselling trends, usually within a range of approximately $2,000. It's important to consider these discrepancies in predictions, as they can significantly impact real-world decisions. However, these deviations can serve as a valuable benchmark for decision-making.

