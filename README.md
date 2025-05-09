# Absenteeism Prediction Project

An end-to-end machine learning solution to predict excessive employee absenteeism during work hours.

## Project Overview

This project addresses the growing challenge of workplace absenteeism, which can significantly impact company productivity and goals. Using machine learning techniques, I've developed a model that predicts whether an employee is likely to be excessively absent from work based on various personal and professional factors.

### Business Problem

Many companies face challenges with employee absenteeism due to:
- Unachievable business goals leading to increased stress levels
- Higher risk of unemployment creating anxiety
- Increased workplace competitiveness and pressure

### Project Objectives

- Create a metric to effectively measure absenteeism
- Identify key predictors that indicate whether an employee will be absent
- Determine if employees with certain characteristics are more likely to be absent
- Predict absenteeism patterns based on factors like commute distance, family responsibilities, and education level

## Dataset

The project uses the Absenteeism at Work dataset containing 700+ records with information about:
- Reason for absence (categorized into 28 different reasons)
- Transportation expense
- Distance to work
- Age
- Daily workload
- BMI (Body Mass Index)
- Education level
- Number of children and pets
- Absenteeism time in hours

## Methodology

### Data Preprocessing

1. Dropped unnecessary columns like `ID`
2. Converted categorical reasons for absence into grouped dummy variables:
   - Group 1: Reasons 1–14 (mostly disease-related)
   - Group 2: Reasons 15–17
   - Group 3: Reasons 18–21
   - Group 4: Reasons 22–28 (non-medical reasons)
3. Extracted month and day of week from date information
4. Converted education data to binary format
5. Created target variable by classifying absenteeism as:
   - Moderately absent (≤ 3 hours): `0`
   - Excessively absent (≥ 4 hours): `1`

### Feature Engineering & Model Development

1. Implemented two scaling approaches:
   - Standard scaling using `sklearn`'s `StandardScaler`
   - Custom scaling with a specialized `CustomScaler` class
2. Split data into training (80%) and testing (20%) sets
3. Built logistic regression models with both scaling methods
4. Applied backward elimination to simplify the model by removing features with minimal contribution
5. Calculated and analyzed coefficients and odds ratios for model interpretation

### Model Deployment

Created a reusable module for making predictions on new data, with functionality to:
- Load and preprocess new data consistently
- Generate probability scores for excessive absenteeism
- Provide binary predictions (excessive/moderate absenteeism)

## Results & Insights

The final model achieved **75% accuracy** in predicting excessive absenteeism. Key findings include:
- Identification of the most significant predictors of excessive absenteeism
- Understanding of the relationship between personal factors and absence patterns
- Insights into how transportation and workplace factors impact attendance

## Technologies Used

- Python
- pandas for data manipulation
- scikit-learn for machine learning algorithms
- NumPy for numerical operations
- Pickle for model serialization

## What I Learned

This project enhanced my skills in:
- End-to-end machine learning project development
- Feature engineering and selection
- Model interpretation through coefficients and odds ratios
- Creating custom transformer classes for data preprocessing
- Building reusable prediction modules


