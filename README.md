# Marketing Insights for an E-Commerce Company

## Project Overview

This project analyzes e-commerce transaction and marketing data to understand sales performance, customer behavior, marketing spend, and opportunities to improve customer retention and targeting. The analysis uses transaction records from **1 January 2019 to 31 December 2019** and combines sales, customer, discount coupon, marketing spend, and tax data.

The project was completed in Python using Jupyter Notebook, with exploratory analysis, customer segmentation, predictive modeling, product-pair analysis, and cohort analysis.

## Business Objectives 

- Calculate transaction-level invoice value using quantity, unit price, discount, GST, and delivery charges.
- Analyze customer acquisition, repeat purchases, retention, and revenue from new versus existing customers.
- Track sales KPIs by time period, product category, and customer location.
- Explore discount usage and the relationship between marketing spend and revenue.
- Segment customers using value-based/RFM approaches and K-Means clustering.
- Classify customers into low-, medium-, and high-value groups.
- Analyze products that are purchased together to identify potential cross-selling opportunities.
- Predict the next-purchase interval for repeat customers.
- Perform monthly customer cohort analysis to study retention behavior.

## Dataset

The project uses the following five datasets:

| Dataset | Description |
|---|---|
| `Online_Sales.csv` | Transaction-level sales, products, quantity, unit price, delivery charges, and coupon status |
| `CustomersData.xlsx` | Customer demographics, location, gender, and tenure |
| `Discount_Coupon.csv` | Monthly category-level coupon codes and discount percentages |
| `Marketing_Spend.csv` | Daily offline and online marketing spend |
| `Tax_amount.xlsx` | GST rates by product category |

The data covers calendar year 2019.

## Tools and Libraries

- **Python:** pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Statistics and Machine Learning:** SciPy, scikit-learn, XGBoost
- **Environment:** Jupyter Notebook

## Workflow

### 1. Data Preparation and Integration
- Loaded and inspected the five datasets.
- Checked data types, missing values, and duplicate records.
- Standardized column names and corrected data types, including transaction dates.
- Joined the datasets to create an analysis-ready dataset.
- Prepared fields required for revenue calculations and customer-level analysis.

### 2. Revenue Calculation and Exploratory Data Analysis
Calculated invoice value using the project definition:

`Invoice Value = ((Quantity × Avg_Price) × (1 − Discount_pct) × (1 + GST)) + Delivery_Charges`

Explored customer acquisition, monthly retention, new-versus-existing customer revenue, discount usage, sales trends, product/category performance, geographic patterns, and marketing spend. Analyzed revenue, orders, average order value, customer counts, quantity, tax, and delivery charges across relevant time periods.

### 3. Customer Segmentation
- Created value-based customer segments (Premium, Gold, Silver, and Standard).
- Built RFM-style segments using recency, frequency, and monetary behavior.
- Applied K-Means clustering to identify customer groups and inspect their profiles.

### 4. Customer Lifetime Value (CLV) Classification
- Defined low-, medium-, and high-value customer classes using customer revenue.
- Prepared model features and addressed class imbalance through resampling.
- Trained classification models, including Logistic Regression and XGBoost, and reviewed classification metrics.

### 5. Cross-Selling Analysis
Explored transaction-level product combinations to identify products that may be suitable for joint promotions or bundles.

### 6. Next-Purchase Interval Prediction
Created customer-level target groups for the expected purchase interval: 0–30, 30–60, 60–90, and 90+ days. Evaluated classification approaches for predicting these intervals.

### 7. Cohort Analysis
Grouped customers by acquisition month and examined subsequent monthly purchasing behavior to understand retention patterns.

## Key Outcomes

- Built a repeatable analytical workflow spanning data preparation, EDA, customer segmentation, and predictive modeling.
- Developed customer groups that can support differentiated retention, activation, and promotional strategies.
- Explored customer-value classification and next-purchase interval prediction as potential inputs to targeted marketing.
- Identified cross-selling and cohort-analysis approaches for examining product affinity and customer retention.

> **Note:** Model performance should be reported using held-out test-set metrics. The notebook contains very high training scores for the CLV classification experiment, so training scores alone should not be presented as evidence of generalization. Add validated test metrics and quantified business findings here if you have them available.

## Repository Structure

```text
Marketing-Insights-for-E-Commerce/
├── Marketing_Insights_For_E_Commerce_Company.ipynb
├── Online_Sales.csv
├── CustomersData.xlsx
├── Discount_Coupon.csv
├── Marketing_Spend.csv
├── Tax_amount.xlsx
└── README.md
```

*Update the filenames in this example to match the files committed to your repository.*

## How to Run

1. Clone or download this repository.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scipy scikit-learn xgboost openpyxl mlxtend
   ```

3. Update the dataset paths in the notebook to point to the local dataset files.
4. Open the notebook in Jupyter and run the cells in order.

## Potential Business Applications

- Target high-value customers with loyalty and retention campaigns.
- Design reactivation campaigns for customers who have not purchased recently.
- Use customer segments to tailor offers rather than applying the same discount to everyone.
- Explore product bundles based on products that appear together in transactions.
- Use next-purchase predictions to inform the timing of customer communications.
- Monitor cohort retention and marketing spend alongside revenue.

## Limitations

- The dataset covers one calendar year, which limits analysis of longer-term customer lifetime behavior.
- Predictive results need to be assessed on held-out data before operational use.
- Associations between marketing spend and revenue do not, by themselves, prove that marketing spend caused revenue changes.
- Recommendations should be validated with business stakeholders or controlled experiments before implementation.
#
