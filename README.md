# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Project Overview

This project demonstrates the complete business data cleaning, validation, and reporting process for a retail order dataset. The objective was to transform a raw, inconsistent dataset into a clean, analysis-ready dataset by applying data cleaning techniques, business validation rules, calculated fields, and Excel-based reporting.

The final deliverables include a cleaned dataset, data quality report, pivot summary report, cleaning log, and supporting screenshots.

---

# Repository Structure

```
part1_data_cleaning/
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
└── README.md
```



# Problem Statement

The retail company exported order-level sales data from multiple internal systems. The raw dataset contained numerous data quality issues, including inconsistent text formatting, mixed date formats, duplicate records, missing values, invalid discounts, calculation mismatches, and inconsistent order statuses.

The goal of this project was to clean, validate, standardize, and prepare the dataset for business reporting and analysis.



# Dataset Description

The dataset contains order-level information including:

- Order ID
- Order Date
- Ship Date
- Customer Name
- Customer Segment
- Region
- State
- City
- Category
- Sub Category
- Ship Mode
- Quantity
- Unit Price
- Cost
- Discount
- Sales
- Profit
- Payment Status
- Order Status



# Tools Used

- Microsoft Excel
- Excel Functions
  - TRIM
  - PROPER
  - SUBSTITUTE
  - IF
  - IFERROR
  - TEXT
  - YEAR
  - MONTH
  - DATEDIF
  - COUNTIF
  - SUMIFS
- Excel Pivot Tables
- Conditional Formatting
- Filters and Sorting



# Data Cleaning Steps

The following cleaning activities were performed:

### Text Cleaning

- Removed leading and trailing spaces
- Removed extra spaces
- Standardized capitalization
- Corrected inconsistent text values
- Standardized category names
- Standardized sub-category names
- Standardized region names
- Standardized customer segment names
- Standardized ship mode values
- Standardized payment status values
- Standardized order status values



### Date Cleaning

- Converted all valid dates into a consistent format (dd-mm-yyyy)
- Identified invalid dates
- Flagged missing dates
- Flagged Ship Date earlier than Order Date
- Calculated Shipping Delay Days



### Missing Value Handling

Applied the following business rules:

- Missing Region → Filled as **Unknown**
- Missing Ship Mode → Filled as **Unknown**
- Missing Discount → Treated as **0** only when all other sales fields were valid
- Missing mandatory values were flagged for review



### Duplicate Handling

The dataset was checked for:

- Exact duplicate records
- Duplicate Order IDs
- Conflicting duplicate Order IDs

Actions taken:

- Removed exact duplicate rows
- Retained conflicting duplicate Order IDs
- Flagged conflicting records for manual review



# Business Rules Applied

The following business validation rules were implemented:

- Missing Region filled with "Unknown"
- Missing Ship Mode filled with "Unknown"
- Negative discounts flagged as invalid
- Discounts above the acceptable business range flagged as invalid
- Cancelled orders excluded from completed sales summaries
- Failed payment orders excluded from completed sales summaries
- Refunded orders summarized separately
- Ship Date before Order Date flagged as invalid
- Data quality flags assigned to every record



# Calculated Columns

The cleaned dataset includes the following calculated fields:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag



# Data Quality Report

The Data Quality Report includes:

- Missing Value Summary
- Duplicate Summary
- Invalid Discount Summary
- Date Issue Summary
- Order Status Summary
- Sales and Profit Calculation Mismatch Summary
- Final Clean vs Flagged Record Summary



# Pivot Summary Report

The Pivot Summary workbook contains the following reports:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

Sorting and filtering have been applied to selected pivot tables as required.



# Key Business Insights

- Regional sales and profit performance can be compared effectively.
- Product categories contributing the highest revenue are easily identified.
- Customer segment profitability can be evaluated.
- Monthly sales trends provide insights into seasonal performance.
- Refunded, cancelled, and failed orders are summarized separately for operational review.
- Data quality issues were identified and documented for future process improvements.



# Assumptions

- Missing Region values were replaced with **Unknown**.
- Missing Ship Mode values were replaced with **Unknown**.
- Missing Discount values were considered as zero only when other sales fields were valid.
- Cancelled and Failed Payment orders do not contribute to completed sales analysis.
- Conflicting duplicate records require manual review.



# Limitations

- Business rules were implemented based on the assignment requirements.
- Some conflicting duplicate records require manual verification.
- External master data was not available for validation.
- Data accuracy depends on the correctness of the source dataset.



# Screenshots Included

The repository contains the following screenshots:

- Raw dataset preview
- Cleaned dataset preview
- Pivot Summary 1
- Pivot Summary 2



# Conclusion

The raw retail sales dataset was successfully cleaned, validated, standardized, and transformed into an analysis-ready dataset. Business rules were consistently applied, data quality issues were documented, and comprehensive reports were created using Microsoft Excel. The final outputs support business decision-making through clean data, quality reporting, and meaningful pivot-based summaries.
