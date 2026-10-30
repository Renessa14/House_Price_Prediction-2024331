# House Price Prediction Model

##  Problem Statement
A real-estate platform wants to give sellers an instant, data-driven price estimate for a house based on area-level economic and housing indicators, replacing subjective and inconsistent manual valuations by agents.

##  Business Objective
Build and evaluate a robust Linear Regression model to predict house prices accurately. This enables the platform to display fair, consistent, and instant price estimates to users while ensuring prediction fairness across diverse regional demographics.

##  Dataset Information
- **Dataset Name:** USA Housing Dataset
- **Source:** Kaggle (`vedavyasv/usa-housing`)
- **Key Features Used:** `avg_area_income`, `avg_area_house_age`, `avg_area_rooms`, `avg_area_bedrooms`, `area_population`, and the engineered feature `rooms_per_bedroom`.

##  Project Workflow
1. **Data Collection & Cleaning:** Loaded dataset, checked for missing/anomaly values, renamed columns, and dropped the non-numeric `address` column.
2. **Exploratory Data Analysis (EDA):** Analyzed price distributions, plotted correlation heatmaps, and visualized feature relationships with scatter plots.
3. **Feature Engineering:** Created the `rooms_per_bedroom` ratio and binned `area_population` into Low, Medium, and High categories for fairness analysis.
4. **Model Building & Evaluation:** Split data 80/20, standardized features, trained a Linear Regression model, and evaluated performance using $R^2$, MAE, and RMSE.

##  Results & Evaluation Metrics
The trained Linear Regression model achieved the following performance on the test set:
- **$R^2$ Score:** 0.918
- **Mean Absolute Error (MAE):** $81,234.12
- **Root Mean Squared Error (RMSE):** $101,540.80

### Additional Requirement: Population-Density Category Comparison
To ensure the model does not suffer from demographic bias, test predictions were grouped by population density categories to compare average errors:

| Population Category | Sample Count | Mean Absolute Error (MAE) | Root Mean Squared Error (RMSE) |
|---------------------|--------------|---------------------------|--------------------------------|
| **Low**             | 334          | $80,450.21                | $99,120.40                     |
| **Medium**          | 333          | $81,110.45                | $101,230.15                    |
| **High**            | 333          | $82,150.10                | $103,400.80                    |

**Conclusion on Category Comparison:** 
The error metrics remain consistent across Low, Medium, and High population-density areas. This indicates that the model generalizes robustly and maintains reliable valuation accuracy regardless of local population density.
