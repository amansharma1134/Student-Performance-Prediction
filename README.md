# Student Performance Prediction

This repository contains a data science project aimed at predicting whether a student will pass or fail based on various academic and extracurricular factors. The project utilizes **Python**, **Pandas**, **NumPy**, and **Scikit-Learn** to perform data cleaning, exploratory data analysis, and machine learning classification.

---

## ## Project Objective
The goal is to analyze student data (study hours, attendance, previous grades, etc.) to build a predictive model that determines student success (Pass/Fail).

## ## Dataset Overview
The project uses a dataset consisting of **40,000 student records**. Key features include:
* **Study Hours per Week**: Numerical value indicating time spent studying.
* **Attendance Rate**: Percentage of classes attended.
* **Previous Grades**: Historical academic performance.
* **Extracurricular Activities**: Binary participation (Yes/No).
* **Parent Education Level**: Categorical data ranging from High School to Doctorate.
* **Passed**: The target variable (Yes/No).

## ## Key Findings from Data Analysis
* **Missing Values**: Approximately **5%** of data was missing across most columns, which was handled using median imputation for numerical features.
* **Data Anomalies**: Initial descriptive statistics revealed outliers, such as a maximum grade of **200.0** and a maximum attendance rate of **150.2%**.
* **Correlations**: Interestingly, "Attendance Rate" and "Doctorate-level Parent Education" showed the highest (though still low) positive correlation with passing, while "Study Hours" showed a slight negative correlation in this specific dataset.

## ## Machine Learning Workflow

### ### 1. Data Preprocessing
* Converted categorical variables (`Passed`, `Extracurricular`) into numerical formats.
* Applied **One-Hot Encoding** to `Parent Education Level` to prepare it for the model.
* Handled missing values using median filling to ensure a complete dataset for training.

### ### 2. Model Implementation
Two primary models were tested:
* **Logistic Regression**: Served as the baseline model.
* **Random Forest Classifier**: Used to determine feature importance.

### ### 3. Performance Metrics
The baseline Logistic Regression model achieved:
* **Accuracy**: ~52.61%.
* **Observations**: The model showed high recall for passing students but struggled significantly with identifying failing students (precision for '0.0' was high, but recall was near zero), indicating a need for further feature engineering or class balancing.

### ### 4. Feature Importance
According to the Random Forest model, the top three predictors of student performance are:
1.  **Attendance Rate** (34.3%)
2.  **Previous Grades** (33.8%)
3.  **Study Hours per Week** (29.9%)

---

## ## Technologies Used
* **Python 3.11**
* **Pandas & NumPy**: Data manipulation
* **Scikit-Learn**: Machine learning and evaluation
* **SciPy**: Statistical testing

## ## How to Use
1.  Ensure you have the `student_performance_prediction.csv` file in the project directory.
2.  Install requirements: `pip install pandas numpy scikit-learn scipy`.
3.  Run the `Student Performance Prediction.ipynb` notebook to see the full analysis and model results.
