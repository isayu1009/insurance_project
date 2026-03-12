<h1>📊Healthcare Claim Analysis & High‑Risk Customer Identification </h1> </br>
This project aims to analyze healthcare claims to identify high-cost factors and high-risk members within an insurance population. It combines Python data processing, machine learning techniques, 
and Power BI visualizations to deliver actionable insights for insurance optimization and risk management. </br>

<br><h2>🚀Project Objectives</br></h2>

Identify key cost drivers in healthcare spending
Detect high-risk members based on demographic and claim patterns
Explore correlations between plan type, risk level, and claims behavior
Build visual dashboards with Power BI for clear decision-making
Provide strategic recommendations for premium alignment and plan optimization

<br>

<h2>🗂️ Data Source</h2>

The data is sourced from the project: [Healthcare Claims – Where Is the Money Going?](https://www.analystbuilder.com/projects/healthcare-claims-where-is-the-money-going-TVHLQ)

<br><h2>🛠️Methodology</br></h2>
<h3>1. Python (Data Preparation & Analysis)</h3>

Data cleaning and preprocessing
Missing data prediction using machine learning
Feature extraction to identify high-cost and high-risk patterns

<br>

<h2>🧹 Data Cleaning & Preprocessing</h2>

A significant part of this project involved transforming raw healthcare claim data into a reliable and analysis‑ready dataset. The cleaning process focused on accuracy, consistency, and preparing the data for machine learning.

### 🔍 1. Data Quality Assessment
Before cleaning, the dataset was examined for:
- Missing or incomplete values  
- Inconsistent data types (dates stored as text, numerical fields as strings)  
- Duplicate records  
- Unexpected categories or spelling variations  
- Outliers in age, claim amounts, and enrollment gaps  

This initial audit ensured that issues were identified early and addressed systematically.

### 🔧 2. Data Type Corrections
Several columns required type adjustments:
- Converted **date fields** (`claim_date`, `enrollment_start`, `enrollment_end`) to proper datetime formats  
- Fixed numerical fields that were incorrectly imported as strings  
- Standardized categorical fields (plan types, gender, claim type)

These transformations ensured that the dataset behaved correctly during EDA and modeling.

### 🔗 3. Dataset Merging
Two separate tables — member information and claim details — were merged using `member_id`.  
This enabled:
- Linking demographic information to claim behavior  
- Creating derived features such as claim frequency per member  
- Improving the machine learning model’s ability to detect patterns

### 🧩 4. Missing Value Treatment
During EDA, I identified that **missing `enrollment_end_date` values** showed meaningful patterns.  
Instead of dropping these rows, I:
- Analyzed correlations with `enrollment_start`, `claim_date`, plan type, and age  
- Built a machine learning model to predict missing end dates  
- Ensured the predicted values aligned with logical enrollment timelines

### 🧼 5. Feature Engineering
To enhance model performance and insights:
- Calculated **claim frequency** and **claim cost ratios**  
- Created **enrollment gap** duration  
- Classified members into risk categories  
- Extracted time‑based features such as year and month from claim dates

These engineered features helped uncover cost drivers and risk patterns.

### 🛡 6. Final Output
After cleaning and preprocessing:
- The dataset was consistent, well‑structured, and model‑ready  
- No critical missing values remained  
- All features used for analysis and machine learning were validated  
- The dataset was exported into the `data/processed/` directory

<br>

<h3>Power BI (Visualization & Insights)</h3>

Cost distribution
Claim frequencies
Service category analysis
High-risk member dashboards
Plan-type comparison visuals

<br><h2>📈 Key Insights</br></h2>
General Population Overview

100 members submitted 449 total claims → 4.49 claims per member
Gender split: 50% male / 50% female
Average age: 48.43 years

<br><h2>Cost Drivers</br></h2>

Inpatient services represent the largest share of both claim frequency and total spending.
This was confirmed consistently across multiple visualizations.

<br><h2>High-Risk Population</br></h2>
The top 10 highest-risk members show clear trends:

<br>* ~Around 70% are male</br>
<br>* Plan type split: 50% POS / 50% EPO</br> 
<br>* 50% are currently enrolled in low to moderate cost plans</br>

<br><h2>💡Recommendations</br></h2>

Evaluate premium structures for high‑risk members in low-cost plans.
Encourage migration toward moderate‑tier plans for better cost alignment.
Consider introducing an additional mid‑tier plan and phasing out the lowest-cost tier.
<br>
<br>
<h2> Bonus </h2>

<h2>🤖 Machine Learning Approach</h2>

During the EDA stage, I identified that it was possible to **predict missing `enrollment_end_date` values**, as the dataset contained enough patterns and supporting variables to model this attribute.

### 🔧 1. Data Preparation for Modeling

Before modeling, the dataset underwent several preprocessing steps:

- The dataset was already relatively clean; only minor corrections were required, such as **data type adjustments** and **merging two related tables**.
- **Encoding categorical features** to make them usable for machine learning algorithms.
- **Splitting the dataset** into training and testing sets to evaluate model performance.

These steps ensured that the data used for prediction was clean, consistent, and suitable for machine learning.

### 📈 2. Models Used

Multiple models were tested to determine the best approach for predicting missing values and understanding member risk patterns:

- **Random Forest Regressor / Classifier**  
  Used for missing date prediction due to its robustness and ability to capture nonlinear relationships.

- **Pipeline**  
  Implemented to streamline preprocessing and modeling steps, ensuring reproducibility and cleaner experimentation.

<br>

<h2>🎯 Machine Learning Results</h2>

The machine learning stage of the project focused on predicting missing `enrollment_end_date` values and identifying patterns associated with member risk and claim behavior.

### 📘 1. Target Variable: Enrollment End Date
The goal was to predict missing end dates using:
- Enrollment start date  
- Claim history  
- Member age  
- Plan type  
- Gaps and patterns in claims  
- Health service categories  

### 📊 2. Model Performance
The Random Forest model produced strong results due to its ability to:
- Handle nonlinear relationships  
- Capture interactions across demographic and claim variables  
- Manage categorical and numerical features together  

After evaluating several alternatives, Random Forest provided:
- Good predictive stability  
- Lower error on unseen data  
- Clear feature importance output  

### 🔍 3. Feature Importance Insights
Key predictors that influenced the end date model included:
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/19c414b6-3682-4ee2-9b52-435035ac0a42" />




### 💡 4. Final ML Output
The machine learning model enabled:
- Filling in missing enrollment data with confidence  
- Improving dataset completeness for BI reporting  
- Supporting accurate risk segmentation  
- Enhancing the quality of the visual analysis in Power BI  

All predicted values were re‑integrated into the `processed` dataset for full analytical consistency.
