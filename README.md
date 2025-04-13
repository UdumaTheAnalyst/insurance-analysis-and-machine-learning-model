# insurance-analysis-and-machine-learning-model  
This project uses python to analyze and create a machine learning model for prediction.    
Report on Insurance Cost Analysis and Prediction  

1. Objective  
The goal of this analysis is to explore the insurance dataset, preprocess the data, and build a linear regression model to predict medical charges based on factors like age, BMI, smoking status, and region.  
2. Dataset Overview  
Source: insurance.csv  
Variables:  
age: Age of the insured  
sex: Gender (male/female)  
bmi: Body Mass Index  
children: Number of dependents  
smoker: Smoking status (yes/no)  
region: Residential region   
charges: Medical costs billed by insurance  
3. Key Steps & Findings  
3.1 Data Loading & Initial Exploration  
Loaded the dataset using pandas.    
First 5 rows:    
   age     sex     bmi  children smoker     region      charges  
0   19  female  27.900         0    yes  southwest  16884.92400  
1   18    male  33.770         1     no  southeast   1725.55230  
...
   Descriptive statistics (e.g., mean age: ~39, mean charges: ~$13,270).  
No missing values after cleaning (clean_insurance has 1198 entries).  
3.2 Data Cleaning  
Handling duplicates and missing values:  
Dropped duplicates and null values.  
Outlier removal using IQR for the charges column:  
Lower bound: Q1 - 1.5*IQR  
Upper bound: Q3 + 1.5*IQR  
Result: Dataset reduced from 1338 to 1198 entries.   
3.3 Data Visualization  
Distribution of Charges:  
Histogram shows a right-skewed distribution, indicating higher medical costs for a subset of individuals.  
Most charges are below   
20  
3.4 Model Building  
Features & Target:  
Features: age, bmi, children, smoker, sex, region  
Target: charges  
Train-Test Split: 80% training, 20% testing.  
Algorithm: Linear Regression (sklearn.linear_model.LinearRegression).  
3.5 Model Evaluation  
Metrics:  
R² Score: ~0.73 (73% of variance explained).  
RMSE: ~$5,900 (indicates average prediction error).
 
Sample Prediction:  

Input: [19, 27.9, 0, 1, 1, 0]  
Predicted Charges: $18,763.92  

4. Insights  
Key Drivers of High Charges:  
Smoking status (e.g., smokers pay significantly more).  
Age and BMI are positively correlated with charges.  

Model Performance:  
The linear regression model performs reasonably well (R² = 0.73) but could be improved with feature engineering or non-linear algorithms.  
5. Recommendations  
Feature Engineering: Encode categorical variables (e.g., smoker, region) more effectively.  
Try Advanced Models: Explore decision trees, random forests, or gradient boosting for better accuracy.    
Outlier Analysis: Investigate why certain individuals have extremely high charges (e.g., pre-existing conditions).  

6. Conclusion  
The analysis provides a foundational understanding of factors influencing insurance costs. The linear regression model offers a baseline prediction, but further refinement could enhance predictive accuracy.  

