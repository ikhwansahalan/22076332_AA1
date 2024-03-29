
# Ikhwan_22076332_AA1
This is a project overview for Alternative Assessment 1: Predicting Customer Churn in E-commerce

# Predicting Customer Churn in E-commerce
In the dynamic landscape of e-commerce, understanding and predicting customer behavior are paramount for businesses aiming to enhance customer satisfaction and retention. This project endeavors to delve into the intricacies of customer interactions within an e-commerce platform, utilizing advanced analytics and machine learning techniques to predict customer churn.

## 1. Goals
The primary goal of this project is to predict customer churn within an e-commerce platform using various classification models in SAS Enterprise Miner.

## 2. Objectives
- Import the E-commerce Customer Behavior Dataset into SAS Enterprise Miner, handle missing values, and specify variable roles.  
- Create a decision tree model in SAS Enterprise Miner to analyze customer behavior and identify potential churn factors.  
- Apply boosting technique using the Random Forest algorithm to enhance predictive accuracy in identifying customer churn.  
    
## 3. Software
In the context of the project described, Excel Spreadsheet, Talend Data Preparation, and SAS Enterprise Miner play distinct roles in various stages of the data analysis and modeling process;  

**1. Excel Spreadsheet**  
**a) Data Exploration and Initial Analysis:**  
    - Excel can be used for the initial exploration of the dataset before importing it into SAS Enterprise Miner or other tools.  
    - Data analysts can quickly view and understand the structure of the dataset, check for any obvious issues, and perform preliminary descriptive statistics.   

**b) Data Cleaning and Preprocessing:**  
    - Excel can be employed for basic data cleaning and preprocessing tasks, such as handling missing values or correcting minor data entry errors.  
    - It can also be used to create derived variables or perform simple transformations.  

**Benefits:**  
    - Quick visual inspection of data.  
    - Easy calculation of summary statistics.  
    - Creation of new variables or features as needed.   

**2. Talend Data Preparation:**  
**a) Data Cleaning and Transformation:**  
    - Talend Data Preparation focuses on data cleaning, transformation, and enrichment. It allows users to explore, clean, and manipulate data interactively.  
    - Ideal for handling missing values, transforming variables, and ensuring data quality.  

**b) Data Exploration and Profiling:**  
    - Provides data profiling capabilities to understand the structure, quality, and patterns within the dataset.  

**Benefits:**  
    - User-Friendly Interface: Enables users to visually explore and manipulate data without extensive coding.  
    - Data Quality Improvement: Helps improve the quality of data by addressing issues such as missing values and outliers.  

**3. SAS Enterprise Miner:**  
**a) Advanced Analytics and Modeling:**  
    - SAS Enterprise Miner is primarily used for advanced analytics and predictive modeling. It provides a user-friendly interface for data mining, machine learning, and model deployment.  
    - In this project, SAS Enterprise Miner can be used to build and evaluate classification models (such as decision trees and random forests) for predicting customer churn based on the provided dataset.  

**b) Data Exploration and Preprocessing:**  
    - While SAS Enterprise Miner is capable of handling some data preprocessing tasks, it might not have the same depth of data preparation capabilities as dedicated data preparation tools.  

**Benefits:**  
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

After acquiring and modifying the dataset, a new project in SAS Enterprise Miner was set up. A diagram named "TEST" was created in the project and the dataset was imported into the File Import node. The figure below is the overall view of the workflow diagram that was implemented for this project:

![Screenshot 2024-01-08 214906](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/b209aeb4-e96e-44ab-a675-ca5161d1e8f5)

Within the file import's 'Edit Variables' section, a few minor adjustments were made to the role and level column. The Customer_ID role was changed to ID, and Churn was chosen as the target variable for the analysis of customer behavior. Because it has a binary value, the level of Discount_Applied, Gender, and Churn were set to Binary. Apart from that, variables of Membership_Type and Satisfaction_Level were set to ordinal. Below are the general modifications made:

![Screenshot 2024-01-08 215002](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/9deacb07-e410-49c6-b391-434881d27da2)

### 3. Exploring Input Data and Replacing Missing Values
Outline:  
1.	Explore the statistical properties of the variables in the input data set.
2.	Partition the input data into Training and Test data sets.
3.	Specify how SAS Enterprise Miner should handle missing data.
   
The statistical data was then explored by combining the File Import node with the StatExplore node. There are 13 missing values in the Satisfaction_Level variable and 18 missing values in the Age variable. The StatExplore node results browser displays the following:

![Screenshot 2024-01-08 215153](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/8ccf1802-5697-4986-bc56-0b23d028e960)

![Screenshot 2024-01-07 191932](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/a6735d95-8c42-4390-a3fe-283ff9f236f9)

![Screenshot 2024-01-07 192150](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/6163ad1f-c962-4d07-a7a3-b28e12cd02b9)

![Screenshot 2024-01-07 192305](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/5f9da77e-d08e-4407-8243-934a13f4a6cb)

Now we want to partition the dataset into training and test sets. Partitioning the data helps to manage the quality of the model during fitting. Data Partition node was used to partition the data into 80% train and 20% test data sets. The example is shown in the diagram below;

![Screenshot 2024-01-07 193626](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/53350d22-39f5-4819-a791-ededb39845cd)

After the data is partitioned, we extendedly prepare the data to replace some more missing values. The Replacement node was connected to the Data Partition node. In the Properties Panel, under Interval Variables, we set the Default Limits Method to None. None indicates that no interval variable values should be replaced. The default setting of Standard Deviations from the Mean would enforce a range of values for each interval variable, which is not suitable for this example. The configure class variable replacement is shown in the diagram below;

![Screenshot 2024-01-07 194301](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/57d72f05-8b3d-412d-a88f-f5cf3f33e81a)

### 4. Building Decision Tree Models
Outline:
1.	Automatically train a full decision tree and prune it to size, selecting split rules to maximize the split decision logworth.
2.	Interactively train a decision tree, and then select candidate split rules from a list.
3.	Use a gradient-boosting approach to form a single predictive model from a set of decision trees.

We will add several decision tree models to our diagram, and then evaluate their relative performance. Before we create multiple decision tree models, we will insert a Control Point node in our diagram. After that, we will drag and connect different models to evaluate which are the best performance models between Decision Tree & Interactive Decision Tree. The Gradient Boosting model was added to the two decision tree models as in the process flow diagram below:

![Screenshot 2024-01-07 195732](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/799130d4-4ad8-404c-8368-e554d99a60b9)

The Gradient Boosting node resamples the analysis data several times to generate results that form a weighted average of the resampled data set. Tree boosting creates a series of decision trees that form a single predictive model. In the Node group of the Gradient Boosting properties, we set the Number of Surrogate Rules to 2. This specifies the number of backup rules that are used in the event of missing data.

![Screenshot 2024-01-09 081145](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/15c81416-2b01-418a-9140-7a2bbed2dde2)

The resulting tree model in Gradient Boosting has nine nodes, including five leaf nodes. The nodes are shaded from light to dark, which corresponds to the percentage of correctly classified observations in each node. 

![Screenshot 2024-01-09 074741](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/9fa2e8ce-e3ee-459c-933e-317ed0b5c124)

Boosting is less prone to overfitting the data than a single tree. The classification table results of the gradient-boosting are shown below: 

![Screenshot 2024-01-07 195827](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/ff4ebc22-e31e-4858-8963-20122f0afc5a)

### 5. Impute, Transform, Regression
Outline:  
1.	Impute values to use as replacements for missing values in the input data. We replace missing data because the Regression model ignores observations that contain missing values.
2.	Transform the input variables to better suit the input data for regression analysis.
3.	Create and add a logistic model.

Missing values are not problematic for decision trees. We can use surrogate splitting rules to select other variable values when splitting variable values are missing. However, in SAS Enterprise Miner, the regression model ignores observations that contain missing values. This reduces the size of the training data set, which can weaken the predictive power of this type of model. To overcome this issue, we had to impute missing values before training the models. The values of missing variables are replaced by the median of the non-missing values. The median statistic is less sensitive to extreme values than the mean or midrange statistic.

![Screenshot 2024-01-09 084127](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/ae982dfb-04d1-415d-9454-0a13d6f0e4cc)

The Impute node creates new variables that contain the imputed values. Imputed variables in SAS results are identified by the prefix IMP_, as shown in the table below:

![Screenshot 2024-01-09 084417](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/7d324edd-bab6-4d1a-8e55-459156d56ff4)

After imputing and replacing missing values, we transformed the input data before we submitted it to the Regression modeling nodes for better model fits. Transforming the data tends to stabilize variance, remove nonlinearity, improve additivity, and counter non-normality. The common log transformation is often used to control skewness. We selected four variables that had skewed distributions for a common log transformation. The Optimal Binning transformation on the other hand helps choose good interval boundaries for such data.

![Screenshot 2024-01-09 085013](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/c1538164-09a4-4419-a361-7689515aa7f8)

The data exported by the Transform Variables node contains new variables that were created for each transformation with an identifier for the transformation type that was used of LG10_,. After selecting all of the transformed variables, we then explore the histogram corresponding observations from the bar selected in the data set window.

![Screenshot 2024-01-09 085428](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/87714450-ce16-411c-bce7-f0d793327aba)

In the Regression node properties, we configure the Selection Model property to use stepwise variable selection to build the logistic regression model. The regression node automatically performs logistic regression as the target variable is a binary outcome. The results are as shown below:

![Screenshot 2024-01-09 095104](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/9743f63e-03fe-4689-a4e2-25edd83d7343)

![Screenshot 2024-01-09 095825](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/b942e209-cb64-4e2b-9807-95bb789ddb48)

### 6. Comparing Models  
Outline:  
1. Compare the statistical performance and use that performance measure to select the champion model.

We have created three non-parametric models (Decision Tree, Interactive Decision Tree, and Gradient Boosting) and one parametric candidate model (Regression). In this segment, we will compare the statistical performance of the four competing models to select the best one. We use the Model Compare node to evaluate the candidate models. Before that, we need to connect the Control Point node to the four models in the diagram. The Model Comparison node was then connected to the Control Point node as shown in the overall view of the workflow diagram. The results of the model comparison are shown in the Fit Statistics window. Note that the Gradient Boosting shows the greatest average profit statistic, and is selected as the champion model. The choice of the champion model is based on the highest selection criterion score. 

![Screenshot 2024-01-07 200129](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/14056b18-a89c-473b-a13f-04be38131262)

![Screenshot 2024-01-07 200312](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/aca3febf-ffb3-4055-80df-3b687c618d66)

![Screenshot 2024-01-07 195827](https://github.com/ikhwansahalan/22076332_AA1/assets/143061425/ff4ebc22-e31e-4858-8963-20122f0afc5a)

Based on the performance evaluation, the Gradient-boosting decision tree provides the best model for the training dataset. However, due to the possibility of outliers and noise, as well as the limited amount of data, the model provided is overfitted. This indicates further study with datasets with better representation, different models of different complexities, as well as different training approaches such as cross-validation techniques.
