
# Ikhwan_22076332_AA1
This is a project overview for Alternative Assessment 1: Predicting Customer Churn in E-commerce

# Predicting Customer Churn in E-commerce

## 1. Goals
The primary goal of this project is to predict customer churn within an e-commerce platform using various classification models in SAS Enterprise Miner.

## 2. Objectives
- Import the E-commerce Customer Behavior Dataset into SAS Enterprise Miner, handle missing values, and specify variable roles.
- Create a decision tree model in SAS Enterprise Miner to analyze customer behavior and identify potential churn factors.
- Apply boosting technique using the Random Forest algorithm to enhance predictive accuracy in identifying customer churn.

## 3. Datasets

Title: E-commerce Customer Behavior Dataset

Source: Kaggle - E-commerce Customer for Behavior Analysis

Description: The dataset offers a comprehensive view of customer behavior within an e-commerce platform, providing insights into interactions and transactions. This detailed breakdown allows for a nuanced analysis of customer preferences, engagement patterns, and satisfaction levels, facilitating data-driven decisions to enhance the overall customer experience.

Columns:

1. Customer ID:
  - Type: Numeric
  - Description: A unique identifier assigned to each customer.
2. Gender:
  - Type: Categorical (Male, Female)
  - Description: Specifies the gender of the customer.
3. Age:
  - Type: Numeric
  - Description: Represents the age of the customer, enabling age-group-specific insights.
4. City:
  - Type: Categorical (City names)
  - Description: Indicates the city of residence for each customer, providing geographic insights.
5. Membership Type:
  - Type: Categorical (Gold, Silver, Bronze)
  - Description: Identifies the type of membership held by the customer, influencing perks and benefits.
6. Total Spend:
  - Type: Numeric
  - Description: Records the total monetary expenditure by the customer on the e-commerce platform.
7. Items Purchased:
  - Type: Numeric
  - Description: Quantifies the total number of items purchased by the customer.
8. Average Rating:
  - Type: Numeric (0 to 5, with decimals)
  - Description: Represents the average rating given by the customer for purchased items, gauging satisfaction.
9. Discount Applied:
  - Type: Boolean (True, False)
  - Description: Indicates whether a discount was applied to the customer's purchase, influencing buying behavior.
10. Days Since Last Purchase:
  - Type: Numeric
  - Description: Reflects the number of days elapsed since the customer's most recent purchase, aiding in retention analysis.
11. Satisfaction Level:
  - Type: Categorical (Satisfied, Neutral, Unsatisfied)
  - Description: Captures the overall satisfaction level of the customer, providing a subjective measure of their experience.
12. Favorite Category:
  - Type: Categorical (‘Toys, Kids, & Babies’, 'Beauty & Personal Care', ‘Home & Living’, ‘Fashion’, ‘Games & Hobbies’, ‘Mobile & Gadgets’)
  - Description: The category in which the customer most frequently shops.
13. Churn:
  - Type: Binomial
  - Description: Indicates whether the customer has stopped purchasing (1 for churned, 0 for active).
    
## 4. Software
In the context of the project described, SAS Enterprise Miner can play distinct roles in various stages of the data analysis and modeling process;

Advanced Analytics and Modeling:
  - SAS Enterprise Miner is primarily used for advanced analytics and predictive modeling. It provides a user-friendly interface for data mining, machine learning, and model deployment.
  - In this project, SAS Enterprise Miner can be used to build and evaluate classification models (such as decision trees and random forests) for predicting customer churn based on the provided dataset.

Data Exploration and Preprocessing:
  - While SAS Enterprise Miner is capable of handling some data preprocessing tasks, it might not have the same depth of data preparation capabilities as dedicated data preparation tools.

Benefits:
  - Integration with SAS Analytics: Seamless integration with other SAS tools for end-to-end analytics.
  - Model Interpretability: Provides insights into model interpretations, variable importance, and performance metrics.


_Further details on the methodology and results are described in the report (Ikhwan_22076332_AA1)._


## 5. Methodology 

### Setting Up an Enterprise Miner Project
1.	Create a new SAS Enterprise Miner Project
2.	Create a new SAS Enterprise Miner process flow diagram
3.	Place the input data source on the process flow diagram
### Exploring Input Data and Replacing Missing Values
1.	Explore the statistical properties of the variables in the input data set.
2.	Partition the input data into Training and Test data sets.
3.	Specify how SAS Enterprise Miner should handle missing data.
### Building Decision Trees
1.	Automatically train a full decision tree and prune it to size, selecting split rules to maximize the split decision logworth.
2.	Interactively train a decision tree, and then select candidate split rules from a list.
3.	Use a gradient-boosting approach to form a single predictive model from a set of decision trees.
### Impute, Transform, Regression
1.	Impute values to use as replacements for missing values in the input data. We replace missing data because the Regression model ignores observations that contain missing values.
2.	Transform the input variables to better suit the input data for regression analysis.
3.	Create and add a logistic model.
### Comparing Models
1. Compare the statistical performance and use that performance measure to select the champion model.
