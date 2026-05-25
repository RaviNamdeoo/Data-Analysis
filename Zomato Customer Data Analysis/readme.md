# Zomato Restaurant Data Analysis
 
Exploratory Data Analysis and Rating Prediction on the Zomato dataset using Python and Machine Learning.
 
---
 
## About the Project
 
This project performs end-to-end data analysis on Zomato restaurant data merged with country codes. The goal is to explore restaurant patterns across countries and build a model to predict aggregate restaurant ratings.
 
---
 
## Dataset
 
- `zomato.csv` — Main restaurant dataset
- `Country-Code.xlsx` — Country code mapping file (merged with main data)
  
---

## What's Covered
 
**Data Cleaning**
- Merged country code data
- Dropped redundant columns (`Address`, `Locality Verbose`, `Switch to order menu`, etc.)
- Filled 9 missing cuisine values with `Fast Food` (no dominant pattern found per city)
  
**EDA**
- Geo-distribution using Longitude & Latitude
- Correlation heatmap of numerical features
- Univariate analysis: Price range, Aggregate rating, Votes
- Multivariate analysis: Rating vs Country, Online Delivery vs Table Booking
  
**Feature Engineering**
- Created `Average Individual Cost` from `Average Cost for two`
- Dropped high cardinality columns (Cuisines, Restaurant Name, Currency, etc.)
  
**Model Building**
- Train/Test split (80/20)
- Preprocessing pipeline using `ColumnTransformer`:
  - PowerTransformer + StandardScaler for skewed numerical columns
  - StandardScaler for remaining numerical columns
  - OneHotEncoder for nominal categorical columns
  - OrdinalEncoder for `Rating text` (mapped to meaningful order)
- Models trained: Linear Regression, Random Forest Regressor

## Results
 
| Model | R² Score |
|---|---|
| Linear Regression | ~92.34% |
| Random Forest Regressor | ~98.75% |
 
> Ordinal encoding of `Rating text` alone improved R² from 79.72% to 91.87%.

## Author
 
Made by Ravi with curiosity and lots of `df.head()` calls.  
Feel free to connect on [LinkedIn](#https://www.linkedin.com/in/ravinamdeo/)
