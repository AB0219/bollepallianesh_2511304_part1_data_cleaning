# Data Cleaning Log

## Project

Business Data Cleaning, Validation & Excel Reporting



## Objective

The objective of this project was to clean, validate, and standardize the retail order dataset to produce an analysis-ready version for business reporting. The cleaned dataset was created without modifying the original raw dataset.



# Issues Identified

The following data quality issues were identified during the assessment:

* Leading and trailing spaces in text fields.
* Multiple spaces between words.
* Inconsistent capitalization of text values.
* Inconsistent category, sub-category, and ship mode names.
* Missing values in business-critical fields.
* Mixed date formats across order and shipment dates.
* Invalid or unrecognized date values.
* Ship dates occurring before order dates.
* Exact duplicate records.
* Duplicate Order IDs with conflicting information.
* Missing discount values.
* Negative discount values.
* Discounts exceeding the acceptable business threshold.
* Cancelled, refunded, and failed payment orders requiring separate treatment.
* Sales and profit calculation inconsistencies.



# Cleaning Actions Performed

## Text Standardization

* Removed leading and trailing spaces using TRIM.
* Removed unnecessary extra spaces.
* Standardized capitalization using PROPER formatting where appropriate.
* Standardized category, sub-category, region, segment, state, city, ship mode, payment status, and order status values.
* Corrected inconsistent spellings and formatting.



## Date Cleaning

* Converted all valid dates into a consistent date format.
* Identified missing dates.
* Flagged invalid date values.
* Flagged records where Ship Date occurred before Order Date.
* Created the Shipping Delay Days calculated column.



## Missing Value Handling

Business rules applied:

| Field             | Action                                                                     |
| ----------------- | -------------------------------------------------------------------------- |
| Region            | Missing values replaced with **Unknown**                                   |
| Ship Mode         | Missing values replaced with **Unknown**                                   |
| Discount          | Missing values replaced with **0** only when other sales fields were valid |
| Other text fields | Standardized where appropriate                                             |



## Duplicate Handling

The dataset was checked for:

* Exact duplicate rows.
* Duplicate Order IDs.
* Conflicting duplicate records.

Actions performed:

* Exact duplicate records were removed.
* Duplicate Order IDs containing conflicting information were retained and flagged for manual review.
* Duplicate handling statistics were recorded in the Data Quality Report.



## Business Rule Validation

The following business rules were applied:

* Negative discounts were flagged as invalid.
* Discounts above the accepted business threshold were flagged.
* Cancelled orders were excluded from completed sales reporting.
* Failed payment records were excluded from completed sales reporting.
* Refunded orders were summarized separately.
* Ship dates occurring before order dates were flagged as invalid shipping records.



## Calculated Columns Added

The cleaned dataset includes the following calculated columns:

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag



## Data Quality Flags

Records were classified into one of the following categories:

* Clean
* Warning
* Invalid

The flag was assigned based on missing values, invalid discounts, date validation, duplicate checks, and business rule violations.



# Assumptions

* Missing Region values were assumed to be **Unknown**.
* Missing Ship Mode values were assumed to be **Unknown**.
* Missing Discount values were treated as zero only when all other sales information was valid.
* Cancelled and Failed Payment orders do not contribute to completed sales analysis.
* Refunded orders were analyzed separately.



# Records Removed

* Exact duplicate records were removed.
* Conflicting duplicate Order IDs were retained and flagged instead of being deleted.



# Records Flagged

Records were flagged for review when they contained:

* Invalid discounts.
* Missing mandatory values.
* Invalid dates.
* Ship Date earlier than Order Date.
* Conflicting duplicate Order IDs.
* Sales or profit calculation mismatches.



# Limitations

* Business rules were applied based on the requirements provided in the assignment.
* Product master data and customer master data were not available for cross-validation.
* Some conflicting duplicate records require manual business review.
* Calculated values depend on the correctness of the source data provided.



# Outcome

The cleaned dataset is standardized, validated, and ready for business reporting and dashboard development. Supporting reports include a Data Quality Report and Pivot Summary Report for business analysis.
