# Supermart Sales Analysis
## Project Overview
This project analyzes Supermart grocery sales data to uncover business insights, trends, and patterns. The goal is to identify top-selling products, understand regional and seasonal sales trends, and predict sales using machine learning.

## This project showcases skills in:

- Data Cleaning & Preprocessing
- Feature Engineering
- Exploratory Data Analysis (EDA)
- Visualization
- Regression Modeling with Random Forest
  
## Dataset
Source: Supermart Grocery Sales - Retail Analytics Dataset
- Key Columns:
- Category, Sub Category, Region
- Order Date, Sales, Quantity, Discount, Profit

##  Workflow
1. Data Cleaning & Feature Engineering
- Handled missing values, duplicates, and inconsistent date formats.
- Converted Sales and Profit to numeric types.
- Extracted Year, Month, and Day from Order Date.
- Dropped unnecessary columns: Order ID, Customer Name, City, State.
- Created new features: Profit_Margin, Discount_Level (Low, Medium, High, Very High), Is_Weekend, Season (Winter, Spring, Summer, Fall),High_Profit (1 if Profit > median, else 0),Profit_per_Discount
  
2. Exploratory Data Analysis (EDA)

- Compared sales by category before and after cleaning.
- Visualized distributions and checked for outliers using boxplots.
- Calculated skewness for numerical columns.
- Analyzed Profit Margin by Region.
- Handled rare categorical labels (less than 2% frequency) by grouping them as Other.

3. Modeling

- Encoded categorical variables with one-hot encoding.
- Selected features for modeling (Discount, Order_Year, Order_Month, Order_Day, Is_Weekend, Profit_per_Discount, High_Profit, Quarter, and encoded categorical columns).
- Target variable: Sales.
- Split data into train (80%) and test (20%) sets.
- Trained a Random Forest Regressor with 300 trees, max depth 15, and min samples per leaf 5.
- Evaluated model using: R², RMSE, MAE, MAPE (%)
- Visualized Actual vs Predicted Sales for the test set.

4. Results
   
| Metric   | Train  | Test   | Cross-Validation |
| -------- | ------ | ------ | ---------------- |
| R²       | 0.6232 | 0.3392 | -0.0515          |
| RMSE     | 354.99 | 466.86 | 592.21           |
| MAE      | 286.13 | 383.31 | 507.67           |
| MAPE (%) | 24.14  | 32.04  | 44.88            |


## How to Run
1. Clone this repository:
````
git clone https://zaralrubaie/super-mart-grocery-sales-/edit/main/README.md
````
2. Install required packages:
````
pip install -r requirements.txt
````
## Future Work
- Extend the model to forecast monthly sales.
- Perform market basket analysis for product recommendations.
  
## Requirements
- Python 3.x
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
