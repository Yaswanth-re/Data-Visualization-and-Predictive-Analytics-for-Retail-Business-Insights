# Function Reference

This document explains the main functions in `app.py` in simple language. It is written for reviewers, teachers, and new developers who want to understand the project quickly.

## `login()`

Shows a login form in the Streamlit sidebar. It checks the entered username and password against the demo credentials and stops the dashboard if the login fails.

## `build_demo_dataset()`

Creates a realistic demo retail dataset when no external CSV file is available. It generates daily orders from 2020 to 2025 with categories, regions, customers, sales, profit, discounts, quantities, and reviews.

## `load_data(uploaded_file)`

Loads the dataset used by the dashboard. If the user uploads a CSV file, it reads that file. If not, it tries to load `Sample - Superstore.csv`. If that file is missing, it falls back to the generated demo dataset.

## `safe_mape(actual, predicted)`

Calculates Mean Absolute Percentage Error while avoiding division by zero. This is used to compare forecasting models safely.

## `score_sentiment(text)`

Reads a customer review and classifies it as `Positive`, `Negative`, or `Neutral` using simple keyword matching.

## `ensure_supporting_columns(df)`

Adds default columns when the uploaded dataset is missing optional fields. This keeps the dashboard working even when a CSV file only has the required core columns.

## `build_customer_segments(filtered)`

Groups customers using spending value, order frequency, and recency. It uses KMeans clustering to label customers as `At Risk`, `Regular`, or `High Value`.

## `build_basket_pairs(filtered)`

Finds product pairs that appear together in the same order. This supports cross-selling and bundle recommendations.

## `build_export_package(performance_df, best_forecast, anomalies, customer_segments)`

Creates an Excel file in memory with multiple sheets, including model performance, forecast results, anomaly records, and customer segments.

## `generate_business_insights(monthly, region_ranking, anomalies, target, growth, volatility, projected_change)`

Turns calculated metrics into plain-language business insights. It explains growth, forecast direction, top region, volatility, and anomaly findings.

## `build_pdf_report(title, target, kpis, monthly, region_ranking, performance_df, insights)`

Builds a PDF report in memory using ReportLab. The report includes KPIs, charts, model performance, and automated insights.

## `compute_regional_growth(filtered, target)`

Compares the most recent two months for each region and calculates regional growth percentage.

## `prophet_model(train_df, forecast_period)`

Trains a Prophet time-series model and returns future forecast values with upper and lower estimate ranges.

## `linear_model(train_df, forecast_period)`

Trains a simple Linear Regression model using time as the input feature, then predicts future monthly values.

## `arima_model(train_df, forecast_period)`

Trains an ARIMA forecasting model and predicts the next selected number of months.

## `train_and_score_models(monthly, forecast_period)`

Splits the monthly dataset into training and test data, runs Prophet, Linear Regression, and ARIMA, scores each model, and returns the best comparison table.

## Dashboard Flow After Functions

After the functions are defined, `app.py` runs the Streamlit dashboard flow:

1. Load uploaded or demo data.
2. Validate required columns.
3. Apply sidebar filters.
4. Build monthly target data.
5. Train and compare forecasting models.
6. Calculate KPIs, customer segments, anomalies, sentiment, product pairs, and what-if scenarios.
7. Render the dashboard tabs and export options.
