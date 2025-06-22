# module11
Module 11: Practica Application 2 
# Used Car Price Prediction Project

## Project Overview

This project aims to understand the key factors that drive used car prices and build a predictive model to help used car dealerships make data-driven decisions on inventory acquisition and pricing strategies.

Using a dataset of 426K used car listings, we explore various vehicle characteristics and their impact on market value. The final outcome is a recommended pricing model that can assist in estimating the fair market value of used cars.

## Business Objective

The primary goal from a business perspective is to provide actionable insights and a tool to a used car dealership client to optimize their inventory and pricing. By understanding what makes a used car more or less expensive, the dealership can:

*   Acquire inventory at competitive prices.
*   Set profitable and attractive selling prices.
*   Focus on stocking vehicles that are in demand and likely to generate good returns.

## Data

The dataset used in this project is sourced from Kaggle, originally containing information on 3 million used cars. A subset of 426,000 cars was used for this analysis to ensure efficient processing. The dataset includes information on various car attributes such as:

*   Manufacturer (make)
*   Model
*   Year
*   Odometer reading (mileage)
*   Condition
*   Cylinders
*   Fuel type
*   Title status
*   Transmission
*   Drive type
*   Size
*   Type
*   Paint color
*   Price (the target variable)

## Methodology

The project followed a structured approach based on the CRISP-DM framework:

1.  **Business Understanding:** Defined the problem from a data perspective: a supervised regression task to predict used car prices.
2.  **Data Understanding:** Explored the dataset to understand its structure, contents, and identify initial quality issues (e.g., missing values, potential outliers).
3.  **Data Preparation:** Cleaned the data by handling missing values, removing irrelevant features, removing outliers, encoding categorical variables into numerical format, splitting the data into training and testing sets, and scaling numerical features. Outliers in price and odometer were identified and removed to improve model robustness.
4.  **Modeling:** Built and evaluated several regression models to predict car prices:
    *   Linear Regression (as a baseline)
    *   Ridge Regression (with cross-validation)
    *   Ridge Regression with GridSearchCV (to find the optimal regularization parameter)
5.  **Evaluation:** Assessed the performance of the models using metrics such as R-squared and Root Mean Squared Error (RMSE). The best performing model was selected based on its ability to generalize to unseen data.
6.  **Deployment (Reporting):** Summarized the findings, key insights, and the recommended model in a report format suitable for the dealership client.

## Key Findings on Price Drivers

Based on the analysis and the coefficients of the best performing model, the most influential factors affecting used car prices were identified. These include:

*   **Year:** Newer cars significantly influence price upwards.
*   **Odometer:** Higher mileage significantly decreases price.
*   **Manufacturer and Model:** Specific makes and models (e.g., certain Buick models, Corvette, Ford Super Duty F-550 DRW) have notable impacts on price.
*   **Condition:** The car's condition (e.g., "like new") adds value.
*   **Fuel Type:** Diesel engines tend to command higher prices compared to gas.
*   **Transmission and Type:** Certain transmission types and vehicle body types (like sedans) can influence price.

A detailed visualization of the top influential features and their impact direction (positive or negative coefficient) is included in the notebook.

## Recommended Pricing Model

The **Ridge Regression model, optimized using GridSearchCV**, is recommended for predicting used car prices.

*   **Performance:** This model achieved a Root Mean Squared Error (RMSE) of approximately **$7441.82** on the test set.
*   **Interpretation of RMSE:** This means that, on average, the model's price predictions are within approximately \$7441.82 of the actual selling price of a used car.
*   **Benefits:** The Ridge model's regularization helps prevent overfitting, making it more reliable for predicting prices on new inventory.

This model provides a data-backed estimate for pricing decisions, aiding in inventory acquisition and setting competitive asking prices.

## How to Use the Findings

The insights and the recommended model can be used by the dealership to:

*   **Inform Pricing:** Use the model's price estimates as a starting point for setting asking prices.
*   **Optimize Inventory:** Focus on acquiring vehicle types and features that the model predicts will have higher market value.
*   **Understand Market Value:** Gain a deeper understanding of how different car attributes influence consumer value.
*   **Enhance Negotiation:** Have a data-driven basis during price negotiations.

## Limitations and Future Steps

*   **Data Timeliness:** The dataset represents a historical snapshot. Incorporating more recent data is crucial for maintaining model accuracy as market conditions change.
*   **Model Accuracy:** While the RMSE is reasonable, it's important to acknowledge that no model can perfectly predict price due to uncaptured factors.
*   **Further Model Exploration:** Exploring other regression techniques could potentially yield marginal improvements in accuracy.
*   **Regional Analysis:** Investigating regional price differences could provide more localized insights.

## Getting Started

To replicate this analysis or use the code:

1.  Ensure you have a Python environment with the necessary libraries installed (pandas, numpy, matplotlib, seaborn, scikit-learn).
2.  The data file `vehicles.csv` is expected to be in a `data` subdirectory relative to the notebook.
3.  Run the code cells in the provided Google Colab notebook sequentially.

## Conclusion

This project successfully identified key drivers of used car prices and delivered a well-performing Ridge Regression model. By leveraging these data-driven insights and the predictive model, used car dealerships can make more informed decisions to optimize their operations and profitability in the competitive used car market.
