# Inventory & Stock Management Dashboard

**Inventory Position, Stock Movement & Supplier Overview**

An Excel portfolio project demonstrating a complete inventory-analysis workflow from raw transaction data and product master data through cleaning, validation, calculations, PivotTables, KPIs, dashboard reporting, and business insights.

## Project Objective

The project analyzes inventory transactions to provide a clear management view of:

- Current stock position
- Inventory value
- Purchasing and sales activity
- Returns
- Warehouse distribution
- Supplier inventory value
- Product-level stock concentration
- Stock status and reorder priority

## Project Workflow

**Raw Inventory Data → Data Cleaning → Data Validation → Product Master Mapping → Calculated Metrics → Inventory Summary → PivotTables → KPI Summary → Dashboard → Business Insights**

## Key KPIs

| KPI | Result |
|---|---:|
| Total Products | 30 |
| Total Current Stock | 34,571 units |
| Total Inventory Value | $1,156,389.50 |
| Total Units Purchased | 42,631 |
| Total Units Sold | 8,228 |
| Total Units Returned | 206 |
| Low Stock Items | 0 |
| Reorder Required Items | 0 |

## Dashboard Preview

![Inventory & Stock Management Dashboard](Inventory_Dashboard.png)


## View the Dashboard Online

Anyone can view the main dashboard workbook in Excel for the web: [Inventory_Stock_Management_Dashboard.xlsx](https://1drv.ms/x/c/af2c5b27416c24d1/IQBJz6Kds3odTJW-g_bih0B0AWZuHaAQafHr8eusl4pAzJs)

## Repository Files

### `Inventory_Stock_Management_Dashboard.xlsx`

The main analysis workbook containing:

- `Cleaned Inventory Data`
- `Dashboard`
- `PivotTables`
- `Inventory Summary`
- `KPI Summary`
- `Data Quality Log`

This is the primary workbook for reviewing the completed analysis.

### `Product_Master_Data.xlsx`

The separate product reference file containing 30 products and:

- Product ID
- Product Name
- Category
- Supplier
- Supplier Country
- Unit Cost
- Unit Price
- Reorder Level
- Safety Stock
- Lead Time Days

### `Raw_Inventory_Data.xlsx`

The original transaction-level inventory dataset used as the starting point for the cleaning workflow.

It contains **1,825 transaction records** and intentionally includes data-quality issues for demonstration purposes.

## Data Cleaning

The main workbook contains the cleaned transaction data. The Data Quality Log documents the cleaning decisions.

| Issue | Count | Action | Reason |
|---|---:|---|---|
| Exact duplicates | 23 | Removed | Duplicate transaction records |
| Missing Quantity | 4 | Removed | Required for inventory movement |
| Zero Quantity | 4 | Removed | No inventory movement |
| Missing Warehouse | 15 | Set to `Unknown` | Cannot reliably infer warehouse |
| Missing Supplier | 13 | Recovered | Matched using Product Master |
| Missing Unit Cost | 10 | Recovered | Matched using Product Master |
| Missing Unit Price | 8 | Recovered | Matched using Product Master |
| Blank Purchase Order | 1,202 | Kept | Expected for non-purchase transactions |

After removing the 23 duplicate records and 8 invalid quantity records, the cleaned dataset contains **1,794 transaction records**.

## Data Validation

The cleaning process included:

- Duplicate detection and removal
- Missing-value investigation
- Quantity validation
- Text and category standardization
- Supplier recovery using the Product Master
- Unit Cost and Unit Price recovery
- Date validation
- Warehouse validation
- Purchase Order completeness checks
- Formula and calculation validation

Sales quantities remain negative because they represent inventory leaving stock.

## Calculated Metrics

### Stock Movement

Stock Movement preserves the direction of inventory movement:

- Purchase → positive
- Sale → negative
- Return → positive
- Adjustment → positive or negative

### Inventory Value

`ABS(Quantity) × Unit Cost`

### Sale Value

For Sale transactions:

`ABS(Quantity) × Unit Price`

Otherwise:

`0`

### Purchase Value

For Purchase transactions:

`Quantity × Unit Cost`

Otherwise:

`0`

## Inventory Summary

The product-level Inventory Summary combines transaction data with Product Master information and calculates:

- Total Purchased
- Total Sold
- Total Returned
- Net Stock Movement
- Inventory Value
- Sales Value
- Stock Status
- Reorder Priority
- Current Stock

## Stock Status Logic

Stock thresholds are based on Reorder Level and Safety Stock from the Product Master.

- **Healthy Stock:** Current Stock > Reorder Level
- **Low Stock:** Current Stock ≤ Reorder Level and > Safety Stock
- **Reorder Required:** Current Stock ≤ Safety Stock

Current project result:

- 30 Healthy Stock
- 0 Low Stock
- 0 Reorder Required

## PivotTable Analysis

The dashboard is supported by PivotTables covering:

1. Current Stock by Category
2. Inventory Value by Supplier
3. Units Purchased vs Sold by Category
4. Current Stock by Warehouse
5. Stock Status
6. Top Products by Current Stock

## Key Inventory Insights

### Inventory Concentration
Electronics holds the largest share of current stock, with **14,858 units**, representing approximately **43%** of the total **34,571 units**.

### Warehouse Distribution
Central Warehouse contains the largest stock position at **17,372 units**, representing approximately **50%** of total recorded stock.

### Inventory Value Concentration
PrintTech represents the largest inventory value among suppliers at **$190,002**, accounting for approximately **16.4%** of the **$1.156M** total inventory value.

### Stock Position
All **30 products** are currently classified as **Healthy Stock**, with **0 Low Stock** and **0 Reorder Required** items based on the calculated stock thresholds.

### Top 10 Concentration
The top 10 products account for **18,658 units**, approximately **54%** of the total current stock.

## Excel Skills Demonstrated

- Data cleaning and validation
- Duplicate detection
- Missing-value handling
- Data standardization
- XLOOKUP
- SUMIFS
- IF and ABS functions
- Calculated columns
- Product Master mapping
- Inventory aggregation
- Stock-status logic
- PivotTables
- PivotCharts
- KPI reporting
- Dashboard design
- Business insight generation

## How to Use

1. Open `Raw_Inventory_Data.xlsx` to review the starting transaction data.
2. Open `Product_Master_Data.xlsx` to review the product reference data.
3. Open `Inventory_Stock_Management_Dashboard.xlsx` to review the completed analysis.
4. Start with `Cleaned Inventory Data`.
5. Review the `Inventory Summary` and `KPI Summary`.
6. Explore the `PivotTables`.
7. Open `Dashboard` for the management overview.
8. Review `Data Quality Log` for documented cleaning decisions.

## Portfolio Context

This project was created as an Excel portfolio project to demonstrate practical data-entry, data-cleaning, spreadsheet-analysis, reporting, and dashboard skills.

All business entities, transactions, products, suppliers, and values in the dataset are fictional and intended for demonstration and portfolio purposes only.

## Suggested GitHub Repository Description

> Excel inventory dashboard built from raw transaction data, featuring data cleaning, product master mapping, KPI analysis, PivotTables, stock monitoring, supplier analysis, and business insights.

## Suggested Repository Topics

`excel` `excel-dashboard` `data-analysis` `data-cleaning` `inventory-management` `pivot-table` `business-intelligence` `dashboard` `portfolio-project`

## License

This project is available under the MIT License.



