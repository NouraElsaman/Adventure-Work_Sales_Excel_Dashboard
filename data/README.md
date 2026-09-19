# Data Directory

This folder contains supporting documentation about the data used in the dashboard.

## Data Source

The data in this project is sourced from the **Adventure Works** sample dataset, which is a widely used Microsoft sample database originally designed for demonstrating SQL Server and Business Intelligence features.

**Note:** The underlying transactional data is embedded within the Excel workbook (`Adventure Works Sales.xlsx`) as PivotTable source data. The raw source tables are not separately exported in this repository.

## Data Scope

| Dimension | Details |
|---|---|
| Time period | 2011 – 2014 (4 years) |
| Total sales orders | 31,465 |
| Total customers | 19,119 |
| Total products | 295 |
| Salespeople | 18 |
| Order channels | Offline, Online |
| Geographies | Southwest, Canada, Northwest, Central, Northeast, Southeast, France, United Kingdom, Germany, Australia |

## Key Measures Available

- **TotalDue** — Sales amount per order (used as the primary revenue measure)
- **OrderQty** — Quantity sold per order line
- **SalesOrderID** — Unique order identifier (used for order count)
- **CustomerID** — Unique customer identifier (used for distinct customer count)
- **SalesPersonID** — Unique salesperson identifier

## Product Hierarchy

```
Category
├── Bikes
│   ├── Road Bikes
│   ├── Mountain Bikes
│   └── Touring Bikes
├── Components
│   ├── Road Frames
│   ├── Mountain Frames
│   ├── Touring Frames
│   ├── Wheels
│   ├── Handlebars
│   └── (others)
├── Clothing
│   ├── Jerseys
│   ├── Shorts
│   ├── Gloves
│   └── (others)
└── Accessories
    ├── Helmets
    ├── Tires and Tubes
    ├── Bottles and Cages
    └── (others)
```

## Order Channel Breakdown (observed in workbook)

| Channel | Orders | Sales (TotalDue) |
|---|---|---|
| Offline | 3,806 | ~$2.86 billion |
| Online | 27,659 | ~$65.4 million |
| **Total** | **31,465** | **~$2.93 billion** |

> **Note:** The high offline order value relative to order count reflects that individual offline orders have significantly higher average values (high-value Bike purchases) versus smaller-unit online accessory/clothing orders.

## Statistical Context (observed in workbook)

**Statistics - Price** and **Statistics - Quantity** are hidden analytical support sheets in the workbook containing descriptive statistics for two numeric distributions (unit price and order quantity respectively), produced using Excel's Data Analysis ToolPak.

