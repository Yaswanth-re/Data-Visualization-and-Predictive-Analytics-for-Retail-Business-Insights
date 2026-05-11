# Data Visualization and Predictive Analytics for Retail Business Insights

A professional Streamlit dashboard that helps retail teams understand sales, profit, customers, products, forecasting, and business actions from one interactive application.

The project turns raw retail CSV data into clear charts, customer segments, predictive forecasts, anomaly detection, what-if analysis, and downloadable reports. It is designed so both technical and non-technical users can understand the business story quickly.

## Dashboard Preview

### Overview Dashboard

![Overview Dashboard](assets/screenshots/dashboard-overview.png)

### Customer Intelligence

![Customer Intelligence](assets/screenshots/dashboard-customers.png)

### Business Actions

![Business Actions](assets/screenshots/dashboard-business-actions.png)

### Smart Insights

![Smart Insights](assets/screenshots/dashboard-smart-insights.png)

## What This Project Solves

Retail businesses often have many records but limited clarity. This dashboard helps answer questions such as:

- Which categories and regions are performing best?
- Which customers are high value, regular, or at risk?
- How do discounts affect sales and profit?
- Which products are commonly purchased together?
- What could happen to revenue if demand, price, or discount changes?
- Which forecasting model gives the best prediction for the selected data?

## Key Features

- Secure sidebar login for controlled dashboard access
- CSV upload support plus a built-in demo retail dataset
- Sales and profit KPI summary cards
- Region, category, segment, store, and sub-category analysis
- Customer segmentation using monetary value, frequency, and recency
- Churn-risk view for customers who may need retention actions
- Review sentiment analysis using simple positive and negative keyword scoring
- Product-pair discovery for cross-selling and bundle ideas
- Discount impact analysis across discount bands
- Time-series forecasting with Prophet, Linear Regression, and ARIMA
- Forecast model comparison using MAE, RMSE, and MAPE
- Anomaly detection for unusual monthly performance
- What-if revenue simulation for price, demand, and discount changes
- Exportable Excel and PDF reports for presentation or documentation

## How The Dashboard Works

1. The user logs in and uploads a CSV file, or the app loads the demo dataset.
2. The app cleans the dataset and adds missing supporting columns when possible.
3. Sidebar filters let the user choose date range, category, region, segment, target variable, and forecast months.
4. The app calculates KPIs, customer segments, forecasts, anomalies, product pairs, discount effects, and business insights.
5. The results appear in six dashboard tabs: Overview, Customers, Products, Category & Segment, Business Actions, and Smart Insights.

## Tech Stack

- Python
- Streamlit
- Pandas
- NumPy
- Plotly
- Prophet
- Scikit-learn
- Statsmodels
- ReportLab
- python-docx

## Project Structure

```text
.
|-- app.py
|-- demo_retail_dataset_full.csv
|-- requirements.txt
|-- README.md
|-- docs/
|   `-- FUNCTION_REFERENCE.md
|-- assets/
|   `-- screenshots/
|       |-- dashboard-overview.png
|       |-- dashboard-customers.png
|       |-- dashboard-business-actions.png
|       |-- dashboard-smart-insights.png
|       `-- dashboard-insights.png
|-- build_ieee_paper.py
|-- build_ieee_paper_low_similarity.py
`-- Data_Visualization_and_Predictive_Analytics_Retail_Insights_Enhanced_16_Slides.pptx
```

## Main Files

- `app.py`: main Streamlit dashboard application
- `demo_retail_dataset_full.csv`: demo dataset used when no CSV is uploaded
- `requirements.txt`: Python packages required to run the project
- `assets/screenshots/`: screenshots used in this README
- `docs/FUNCTION_REFERENCE.md`: simple explanation of every main function in `app.py`
- `build_ieee_paper.py`: script used to generate the project paper
- `build_ieee_paper_low_similarity.py`: alternate paper-generation script
- `Data_Visualization_and_Predictive_Analytics_Retail_Insights_Enhanced_16_Slides.pptx`: final presentation deck

## How To Run Locally

1. Open PowerShell or Command Prompt in this project folder.

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Start the Streamlit dashboard:

```bash
python -m streamlit run app.py
```

4. Login with these demo credentials:

```text
Username: admin
Password: 1234
```

## Dataset Requirements

The dashboard works best when the CSV file contains these columns:

- `Order Date`
- `Category`
- `Region`
- `Sales`
- `Profit`

The app can automatically create default values for several optional columns, including `Segment`, `Quantity`, `Discount`, `Customer ID`, `Order ID`, `Store`, `Review`, and `Sub-Category`.

## Business Value

This project is useful for retail decision support because it combines descriptive analytics, customer intelligence, forecasting, and action recommendations in one place. It can help with performance monitoring, category planning, customer retention, discount strategy, stock planning, and presentation-ready reporting.

## Future Improvements

- Add live database connectivity
- Add user roles and stronger authentication
- Add holiday, weather, and campaign effects to forecasting
- Add customer lifetime value and loyalty scoring
- Deploy the dashboard publicly with Streamlit Community Cloud or another hosting platform

## Author
 academic project on retail business analytics and decision support.
