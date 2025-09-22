# 📊 Annual Product Performance Dashboard

## Project Overview

This project provides a comprehensive analysis of annual product performance, from raw data to a finished dashboard. The workflow leverages **Power Query** for robust data cleaning and transformation and a visualization tool (like Power BI, Tableau, or Excel) to create an insightful dashboard.

The goal is to identify key business trends related to revenue, sales volume, customer satisfaction, and category performance to support data-driven decision-making.

## Dashboard Preview

<img width="1486" height="807" alt="Annual_Product_Performance_Report" src="https://github.com/user-attachments/assets/a46a7459-3e43-4dbc-8d17-9d041ee8a25f" />

## Tech Stack & Tools

*   **Data Source:** `ecommerce_sales_analysis.csv`
*   **Data Transformation:** **Power Query** in Power BI 
*   **Data Visualization:** Power BI 

## Data Processing with Power Query

The raw `ecommerce_sales_analysis.csv` was processed using Power Query to prepare it for analysis. The following key transformation steps were applied:

1.  **Connect to Data Source:** The initial step was to connect to the `ecommerce_sales_analysis.csv` file.

2.  **Unpivot Monthly Sales Columns:**
    *   The dataset originally had 12 separate columns for monthly sales (`sales_month_1` to `sales_month_12`). This "wide" format is not ideal for analysis.
    *   These 12 columns were selected and **unpivoted**. This transformed them into two new columns: `Month` and `Units Sold`, creating a "long" data format that is much more flexible for creating time-based trends and aggregations.

3.  **Create Custom Columns:**
    *   **Total Revenue:** A new custom column was created to calculate the total revenue per product using the formula: `[Total Units Sold] * [price]`.
    *   **Total Units Sold:** A summary column was created by grouping by `product_id` and summing the `Units Sold` column after the unpivot.

4.  **Data Type Correction:** All columns were checked, and their data types were set correctly (e.g., `price` as Currency, `review_score` as Decimal Number, `review_count` as Whole Number).

5.  **Clean & Standardize Data:**
    *   The `Month` column was cleaned to extract only the month number (e.g., transforming "sales_month_1" into "1").
    *   Checked for and handled any potential null or error values to ensure data quality.

The resulting clean and structured table was then loaded into the data model to build the dashboard visualizations.

## Key Metrics & Insights

The dashboard highlights the following top-level metrics for the year:

*   **Total Revenue:** **$1 Billion**
*   **Total Units Sold:** **6.02 Million**
*   **Average Review Score:** **3.03 / 5**
*   **Total Number of Reviews:** **6 Million**

## How to Replicate

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/power-query-sales-dashboard.git](https://github.com/Hemaannamdevula/sales-dashboard)
    ```
2.  **Open Power BI .**
3.  Go to **Get Data** > **From Text/CSV** and select the `ecommerce_sales_analysis.csv` file.
4.  In the Power Query Editor, follow the steps outlined in the **Data Processing with Power Query** section to transform the data.
5.  Load the transformed data and use it to build the dashboard visuals.
