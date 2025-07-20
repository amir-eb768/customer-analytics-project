# Online Retail Customer Analytics

## Project Overview

This project provides a comprehensive analysis of a transactional dataset from a UK-based online retail company. The primary goal is to derive actionable insights into customer behavior to support strategic business decisions. The analysis covers data cleaning, exploratory analysis, customer segmentation using the RFM model, churn analysis, retention analysis using cohorts, and market basket analysis to uncover product associations.

The analysis is performed in the `UCI analysis.ipynb` Jupyter Notebook.

## Dataset

The project utilizes the **Online Retail Dataset** from the UCI Machine Learning Repository.

- **Source:** [UCI Machine Learning Repository: Online Retail Data Set](https://archive.ics.uci.edu/ml/datasets/online+retail)
- **Description:** This dataset contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

## Tools and Libraries

- **Python 3.x**
- **Jupyter Notebook**
- **Libraries:**
  - `pandas`: For data manipulation and analysis.
  - `pandasql`: For running SQL queries on DataFrames.
  - `matplotlib` & `seaborn`: For data visualization.
  - `plotly`: For creating interactive charts.

## Analysis Workflow

The notebook is structured into several key stages of analysis:

### 1. Data Cleaning and Preprocessing
- **Handling Missing Data:** Orders without a `CustomerID` were removed to ensure the integrity of customer-level analysis.
- **Processing Canceled Orders:** Invoices starting with 'C' were identified as canceled. A sophisticated cleaning step was performed to remove the original positive-quantity transactions that correspond to these cancellations, preventing them from being counted as sales.

### 2. Customer Behavior Analysis
- **Order Frequency:** Analyzed the distribution of orders per customer, revealing that a vast majority of customers made only a single purchase.
- **Sales Performance by Country:** Calculated key metrics for each country:
  - **AOV (Average Order Value)**
  - **OPC (Orders Per Customer)**
  - **SPC (Sales Per Customer)**

### 3. Churn Analysis
- **Churn Definition:** A customer is defined as 'churned' if they have not made a purchase within a 6-month (180-day) window from the last transaction date in the dataset.
- **Churn Rate Calculation:** The churn rate was calculated and visualized for each country to identify regions with higher customer attrition.

### 4. RFM Customer Segmentation
- Customers were segmented based on their purchasing behavior using the **RFM (Recency, Frequency, Monetary)** model.
- Each customer was scored on these three dimensions, and then grouped into meaningful segments like 'Best Customers', 'At Risk', 'Loyal Customers', and 'Lost'.

### 5. Cohort Analysis for Retention
- Customer cohorts were created based on the month of their first purchase.
- A retention heatmap was generated to visualize the percentage of customers from each cohort who returned for subsequent purchases, providing clear insights into long-term customer loyalty.

### 6. Market Basket Analysis
- The **Apriori algorithm** was used to discover associations between products that are frequently purchased together.
- Key metrics such as **Support**, **Confidence**, and **Lift** were calculated to identify strong cross-selling opportunities.

### 7. Canceled Order Trend Analysis
- The final analysis examines the monthly trend of order cancellations.
- A monthly cancellation rate (Canceled Orders / Total Orders) was calculated and plotted to identify any seasonal patterns or periods with unusually high cancellations.

## How to Run

1. Clone this repository:
   ```bash
   git clone (https://github.com/amir-eb768/customer-analytics-project/)
   ```
2. Install the required libraries:
   ```bash
   pip install pandas pandasql matplotlib seaborn plotly
   ```
3. Open and run the `UCI analysis.ipynb` notebook in a Jupyter environment.
