
# Ikhwan_22076332_AA1
This is a project overview for Alternative Assessment 1: Predicting Customer Churn in E-commerce

# Predicting Customer Churn in E-commerce

## 1. Goals
The primary goal of this project is to predict customer churn within an e-commerce platform using various classification models in SAS Enterprise Miner.

## 2. Objectives
- Import the E-commerce Customer Behavior Dataset into SAS Enterprise Miner, handle missing values, and specify variable roles.
- Create a decision tree model in SAS Enterprise Miner to analyze customer behavior and identify potential churn factors.
- Apply boosting technique using the Random Forest algorithm to enhance predictive accuracy in identifying customer churn.
    
## 3. Software
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


## 4. Methodology 

### 1. Data Acquisition and Cleaning
This exercise uses open-source data collected from Kaggle as in the following details: 

**1)	Name:** E-commerce Customer Behavior Dataset

**2)	Source:** https://www.kaggle.com/datasets/shriyashjagtap/e-commerce-customer-for-behavior-analysis

**3)	Description:** This dataset provides a comprehensive view of customer behavior within an e-commerce platform. Each entry in the dataset corresponds to a unique customer, offering a detailed breakdown of their interactions and transactions. The information is crafted to facilitate a nuanced analysis of customer preferences, engagement patterns, and satisfaction levels, aiding businesses in making data-driven decisions to enhance the customer experience. The target variable for this project will be the Churn variable. Its data type is Binomial and it indicates whether the customer has stopped purchasing (1 for churned, 0 for active). The rest of the independent variables consist of numeric, categorical, and Boolean as shown in the list below;

**4)	Columns:**

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

The selected dataset consists of 11 variables as shown in the list above. There were some modifications made to the existing dataset to implement the tools and functions for feature engineering and data cleaning for this study case. To complete the dataset for the analysis, 2 variables which are "Favourite Category" and "Churn" (Target Variable) were then appended to the dataset using random sampling inside an Excel Spreadsheet as shown in the figure below:

![Screenshot 2024-01-08 191747](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/d115ea9e-30e5-4c21-b91b-cedd9d34f4f0)

After the dataset had been appended using Excel Spreadsheet, Talend Data Preparation was then utilized to visually explore and address issues such as missing and invalid values from the variables. The figures below show the process done using Talend Data Preparation.

![WhatsApp Image 2024-01-08 at 17 54 20](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/dbe7e247-9e31-4b05-82ed-f402cb71d34e)

![WhatsApp Image 2024-01-08 at 17 54 21](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/8c8688ec-cb23-417e-b15d-bbd21aeab76f)

### 2. Setting Up an Enterprise Miner Project
Outline:
1.	Create a new SAS Enterprise Miner Project
2.	Create a new SAS Enterprise Miner process flow diagram
3.	Place the input data source on the process flow diagram

After acquiring and modifying the dataset, a new project in SAS Enterprise Miner was set up. A diagram named "TEST" was created in the project and the dataset was imported into the File Import node as in the figure below;

![Screenshot 2024-01-07 190656](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/7352a2a2-4667-4348-a4f2-e83b90da20d9)

### 3. Exploring Input Data and Replacing Missing Values
1.	Explore the statistical properties of the variables in the input data set.
2.	Partition the input data into Training and Test data sets.
3.	Specify how SAS Enterprise Miner should handle missing data.
   
The statistical data was then explored by combining the File Import node with the StatExplore node. There are 13 missing values in the Satisfaction_Level variable and 18 missing values in the Age variable. The StatExplore node results browser displays the following:

![Screenshot 2024-01-07 191932](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/a6735d95-8c42-4390-a3fe-283ff9f236f9)

![Screenshot 2024-01-07 192150](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/6163ad1f-c962-4d07-a7a3-b28e12cd02b9)

![Screenshot 2024-01-07 192305](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/5f9da77e-d08e-4407-8243-934a13f4a6cb)

Now we want to partition the dataset into training and test sets. Partitioning the data helps to manage the quality of the model during fitting. Data Partition node was used to partition the data into 80% train and 20% test data sets. The example is shown in the diagram below;

![Screenshot 2024-01-07 193626](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/53350d22-39f5-4819-a791-ededb39845cd)

After the data is partitioned, we extendedly prepare the data to replace some more missing values. The Replacement node was connected to the Data Partition node. In the Properties Panel, under Interval Variables, we set the Default Limits Method to None. None indicates that no interval variable values should be replaced. The default setting of Standard Deviations from the Mean would enforce a range of values for each interval variable, which is not suitable for this example. The configure class variable replacement is shown in the diagram below;

![Screenshot 2024-01-07 194301](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/57d72f05-8b3d-412d-a88f-f5cf3f33e81a)

### 4. Building Decision Trees
Outline:
1.	Automatically train a full decision tree and prune it to size, selecting split rules to maximize the split decision logworth.
2.	Interactively train a decision tree, and then select candidate split rules from a list.
3.	Use a gradient-boosting approach to form a single predictive model from a set of decision trees.

We will add several decision tree models to our diagram, and then evaluate their relative performance. Before we create multiple decision tree models, we will insert a Control Point node in our diagram. After that, we will drag and connect different models to evaluate which are the Decision Tree, Interactive Decision Tree, Gradient Boosting, and Regression. After configuring the properties and running the model, we will get the output result for each model. The examples are in the following diagram;
![Screenshot 2024-01-07 195732](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/799130d4-4ad8-404c-8368-e554d99a60b9)

1
![Screenshot 2024-01-07 190656](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/7352a2a2-4667-4348-a4f2-e83b90da20d9)
2
![Screenshot 2024-01-07 191932](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/a6735d95-8c42-4390-a3fe-283ff9f236f9)
3
![Screenshot 2024-01-07 192150](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/6163ad1f-c962-4d07-a7a3-b28e12cd02b9)
4
![Screenshot 2024-01-07 192211](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/1de3fe8a-11db-4ff6-af73-effaeaf9bf96)
5
![Screenshot 2024-01-07 192305](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/5f9da77e-d08e-4407-8243-934a13f4a6cb)
6
![Screenshot 2024-01-07 193626](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/53350d22-39f5-4819-a791-ededb39845cd)
7
![Screenshot 2024-01-07 194301](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/57d72f05-8b3d-412d-a88f-f5cf3f33e81a)
8
![Screenshot 2024-01-07 195721](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/5f135bed-0cfe-418b-8dae-adee47f1578d)
9
![Screenshot 2024-01-07 195732](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/799130d4-4ad8-404c-8368-e554d99a60b9)
10
![Screenshot 2024-01-07 195827](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/0ac855a2-1c83-4bb6-ad5d-6ef6339f0ff8)
11
![Screenshot 2024-01-07 200129](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/ddffbc5c-9cf4-472b-a7e3-e392e8906ce6)
12
![Screenshot 2024-01-07 200312](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/9716e515-9176-4121-b7bc-bab2990261fd)
### 5. Impute, Transform, Regression
1.	Impute values to use as replacements for missing values in the input data. We replace missing data because the Regression model ignores observations that contain missing values.
2.	Transform the input variables to better suit the input data for regression analysis.
3.	Create and add a logistic model.
### 6. Comparing Models
1. Compare the statistical performance and use that performance measure to select the champion model.
