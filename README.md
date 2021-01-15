# Potential-Customer-Analysis
In this project, I have developed a logistic regression model that assigns a score to each lead based on their likelihood of being successfully converted. Achieved an AUC score of 87.

The below steps were involved in model building:
1. Cleaning and Preparing the Data
2. Test – train split
3. Building the Model
4. Analysing the Model

1. Cleaning and Preparing the Data:
We started the project by importing the csv file into a pandas data frame. Then we
followed the below steps for preparing the data we have built
a. Imputation of Null Values –
First we identified the percentage of null values in all the columns. If present we
either removed them or imputed them with values. So first we plotted all the variables to
find how the values were spread. For columns which had a wider spread we had
removed the null values as we cannot impute any value as it will affect the models that
are built. For all other columns which had a null value percentage less than 5% we
dropped the corresponding rows. For others who have high concentration of a particular
value we imputed the mode of the column
b. Standardization –
We scaled the columns to have maintained the same range of values for
analysis.
c. Outlier treatment –
Removed outliers by plotting boxplots for all the columns which doesnt have a
gradual graph and removed the top 5percentile values for them
d. Creation of dummy variables –
Categorical variables needed to be converted with different levels into
corresponding dummy variables using dummy encoder.
2. Test – train split:
As model building started we need to split data into test and train data. After which we
dropped the predictor and other columns as these we irrelevant. And also assigned the column
value to the predictor variable
3. Model Building:
We built the logistic regression model on the train data and checked statistics summary.
Below are the steps involved –
a. RFE - Using RFE eliminated feature and only 15 variables were considered for our
Model.
b. Checking p-values - We built the model using statsmodel and compared the p-values
of the variables . Then we dropped the ones having higher p-value as they fail to explain
sufficient variance. We kept building the model until we achieved satisfying p values for all
variables.
c. Checking VIF – After which we compared the VIF scores of the variables and dropped
columns having more than 5 VIF. (In this case all the variables had a VIF less than 3 hence we
moved forward with our model from above step)
4. Model Analysis:
After obtaining the coefficients for the model, we applied the prediction on the train data
set and chose the cut-off for calculating the Conversion probability using the ROC curve. Then
we applied the calculation on the ‘Converted’ variable.
a. Precision and Recall – The confusion matrix was calculated based on the prediction
and then we calculated the sensitivity, specificity and accuracy of the model which was more
than 85%.Finally we applied the same model to our test data to assess the model.
