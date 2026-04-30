## Titanic Dataset - Preprocessing & EDA

This notebook performs complete data preprocessing 
and exploratory data analysis (EDA) on the 
Titanic dataset.

## Problem Statement
The Titanic dataset contains several data quality 
issues including missing values, outliers, incorrect 
data types and irrelevant columns that need to be 
cleaned before building any machine learning model.

## Issues Found & How We Fixed Them

### Missing Values
- Age      → 177 missing values 
             Fixed by filling with median
- Cabin    → 687 missing values (77%)
             Dropped entire column
- Embarked → 2 missing values
             Fixed by filling with mode (S)

### Irrelevant Columns Dropped
- PassengerId → Just an ID, not useful
- Name        → Text, not useful for analysis
- Ticket      → Random codes, not useful
- Cabin       → Too many missing values

### Data Type Issues
- Sex      → Object (male/female)
             Converted to 0/1
- Embarked → Object (S/C/Q)
             Converted to 0/1/2

### Outliers
- Fare → Had extreme values up to 512
         Fixed using IQR method
         Capped at upper limit 65.63
- Age  → Outliers between 55-80
         Left as is (realistic values)

## Feature Engineering
Created 3 new meaningful columns:
- FamilySize → SibSp + Parch + 1
               Shows travel group size
- IsAlone    → 1 if alone, 0 if with family
               60% passengers were alone!
- AgeGroup   → Child/Teen/Adult/Middle/Senior
               Age categorization

## Key Insights From EDA
- 60% of passengers travelled alone
- Female survival rate was higher than male
- First class passengers survived more
- Most passengers were Adults (18-35)
- Most passengers boarded from Southampton

## What I Learned
- Importance of inspecting data before cleaning
- Never clean blindly always explore first
- Not all outliers need to be removed
- Feature engineering adds more meaning to data

## Tools Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Dataset Source
Kaggle - Titanic Machine Learning from Disaster
