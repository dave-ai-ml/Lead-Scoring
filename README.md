# Lead-Scoring

This case study is for X Education company which sells online courses. Their current business problem is poor lead conversion rate. Therefore, the company wishes to identify most promising leads and increase the revenue. The provided dataset contains information of 9240 leads and 37 variables.

To begin with, the data was cleaned. A few categorical variables have a level called 'Select' which is null value. Two more variables with 70% missing values were dropped from the analysis. “Tag” variable with many categories seemed to be the interpretation of sales team that engaged with the lead. And also there are 4 variables which seems to be the output of another model Asymmetrique. Such variables were dropped. 

For some of the variables the missing value imputation did not make business sense or were highly skewed, hence were dropped. A few categorical were imputed with mode (categorical) or median (numerical). 12 variables were found to have highly skewed imbalanced data, hence were dropped. Next the outliers which had very minimal representation in some variables were dropped & variables with low frequency outliers were grouped together in new category. Outliers in numerical variables beyond 99% + 3IQR are dropped. At the end of data cleaning, the data was reduced to 12 variables.

Exploratory data analysis was performed. Bi-variate, multivariate analysis was performed. Several insights are derived from the EDA and important features contributing to leads conversion were identified. All the insights and correlations are documented in a PowerPoint presentation.

Model was prepared as follows:

•	Categorical variables with binary values were converted to 1 / 0.

•	One Hot encoding was performed & dummy variables were created for multiple values and the original categorical variables were dropped.

•	Train-test split was done with 80-20 ratio 

•	Numerical variables were scaled with MinMaxScaler to avoid physically unrealistic negative values for time spent on the website.

•	We were left with 30 variables.


Logistic regression model was built with the train dataset. 20 features were selected in RFE. The model was then refined iteratively (7 iterations) by dropping one variable at a time based on p-value (significance), VIF (multicollinearity). At each step, the model metrics were checked with threshold value of 0.5. The final model contained 13 variables.
Training model was then evaluated with a detailed metrics and ROC analysis. The optimal threshold of 0.35 was derived based on sensitivity-specificity & precision-recall trade off. 

Predictions were then made on the unseen test data and the model evaluation showed recall value of 86%, accuracy 80%, F1-score 77% & area under ROC curve 90%. Once all these were found to satisfactory, the lead scores were assigned to each lead.

Finally, the feature importance was analyzed. Since all the variables were in the scale of 0 to 1, it was interpretation of the model parameters of Sigmoid curve. In the conclusion, recommendations like top-3, middle-3 and bottom-1 features are clearly mentioned
