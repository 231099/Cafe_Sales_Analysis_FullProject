<h1>Project Overview</h1>

<p>
The objective of this project was to transform a "dirty" dataset of 10,000 cafe sales records into a high-integrity data model.
  I focused on removing structural errors, handling missing values, and engineering new time-based features to enable detailed business intelligence reporting.
</p>

<h2>Technical Workflow</h2>
<p>
  1. Data Sanitization & Row Filtering
To ensure the mathematical accuracy of the model, I performed the following:

Targeted Cleaning: Identified the Quantity and Unit Price columns as the "Source of Truth."

Null/Blank Removal: Removed all rows where either the Quantity or Unit Price was missing, ensuring only complete transaction records remained.

Error Elimination: Purged rows containing calculation errors or non-numeric "ERROR" strings that would have skewed the dataset.

2. Feature Engineering: Revenue Calculation
Instead of relying on the provided (and inconsistent) financial data, I rebuilt the revenue metrics:

Column Removal: Deleted the original Total Spent column due to data quality issues.

Custom Calculation: Created a new Total Spent column using the formula:
[Quantity] * [Unit Price]

Data Type Optimization: Assigned "Currency" and "Decimal Number" formats to ensure correct aggregation in reports.

3. Time-Series Transformation
To allow for seasonality analysis (Year-over-Year and Month-over-Month), I transformed the temporal data:

Date Duplication: Duplicated the Transaction Date to preserve the original timestamp.

Column Splitting: Deconstructed the date into three distinct columns: Year, Month, and Day.

Benefit: This allows the end-user to drill down into sales performance by specific years or months without complex DAX.
</p>
