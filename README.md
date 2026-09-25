# FUTURE_ML_01

## Machine Learning Internship – Sales & Demand Forecasting

This project was completed as part of the Future Interns Machine Learning Internship.

### Project Objective

The objective of this project is to analyze historical retail sales data and build a machine learning model to forecast daily sales revenue.

### Dataset

The project uses the Online Retail dataset containing transaction-level sales information.

Dataset columns include:

- InvoiceNo
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- CustomerID
- Country

### Data Preparation

The following preprocessing steps were performed:

1. Removed records with missing product descriptions.
2. Converted `InvoiceDate` to datetime format.
3. Removed cancelled invoices.
4. Removed invalid quantities and prices.
5. Calculated transaction-level revenue using:

`Revenue = Quantity × UnitPrice`

6. Aggregated transaction revenue into daily sales.
7. Created time-based and lag features.

### Feature Engineering

The forecasting model uses:

- Year
- Month
- Day
- Day of Week
- Week of Year
- 1-Day Lag
- 7-Day Lag
- 7-Day Rolling Average

### Model

A Random Forest Regressor was used for sales forecasting.

The data was divided chronologically into:

- 80% Training data
- 20% Testing data

This preserves the time-series order and avoids using future observations to predict the past.

### Model Evaluation

The model was evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

### Final Model Performance

**Improved Random Forest**

- MAE: 16,170.46
- RMSE: 26,871.50
- R²: 0.0130

The improved model was also compared with the original Random Forest model and a 7-day lag baseline.

### Visualizations

The project includes visualizations for:

- Historical daily sales
- Actual vs predicted sales
- Forecast error over time
- Monthly sales revenue
- Feature importance

Visualization files are available in the `visualizations` folder.

### Project Structure

```text
FUTURE_ML_01/
│
├── data/
│   └── Online Retail.xlsx
│
├── notebooks/
│   └── task1_sales_forecasting.ipynb
│
├── src/
│
├── visualizations/
│   ├── feature_importance.png
│   ├── forecast_error.png
│   ├── monthly_revenue.png
│   └── final_sales_forecast.png
│
├── README.md
└── .gitignore