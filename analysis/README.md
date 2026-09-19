# Analysis Notes

This folder documents the analytical decisions and findings from the Adventure Works Sales dashboard project.

## Analytical Approach

The analysis was conducted entirely within Microsoft Excel using PivotTables, PivotCharts, slicers, and calculated fields. The workbook contains multiple hidden data sheets that feed the visible dashboard sheets.

## Workbook Structure

| Sheet | Type | Visibility | Purpose |
|---|---|---|---|
| Dashboard - Category | Dashboard | Visible | Products per category, sales category mix, top subcategory bar chart, quantity treemap |
| Dashboard - Region & Monthly | Dashboard | Visible | Sales per region, sales per month, month analysis combo chart, top 5 products |
| Dashboard - Subcategory | Dashboard | Visible | Top 3 subcategories per category by sales value and quantity |
| Dashboard - Top Products | Dashboard | Visible | Top 5 products by quantity, sales, and monthly trend |
| Dashboard - Additional | Dashboard | Visible | Additional analytical view |
| Dashboard - Overview | Dashboard | Hidden | Secondary dashboard view — 7 charts, not visible by default (originally Sheet2) |
| Pivot Data | PivotTable data | Hidden | All 28 PivotTables and chart source aggregations (originally Sheet1) |
| Statistics - Price | Statistics | Hidden | Descriptive statistics for price distribution (mean, median, SD, skewness, kurtosis) |
| Statistics - Quantity | Statistics | Hidden | Descriptive statistics for quantity distribution |

> **Note:** One genuinely empty sheet (Sheet5: 0 charts, 0 shapes) was removed during workbook professionalization. Sheet2 was retained and renamed to **Dashboard - Overview** after Excel confirmed it contained 7 ChartObjects and 12 Shapes.

## Key Business Dimensions

The dashboard enables analysis across the following dimensions:

1. **Product Category** — Bikes, Components, Clothing, Accessories
2. **Product Subcategory** — Road Bikes, Mountain Bikes, Road Frames, Jerseys, Helmets, etc.
3. **Territory/Region** — Southwest, Canada, Northwest, Central, Northeast, Southeast, France, United Kingdom, Germany, Australia
4. **Time** — Monthly patterns across 2011–2014; annual slicer (2011, 2012, 2013, 2014)
5. **Order Channel** — Offline vs. Online
6. **Individual Product** — 295 distinct products

## Confirmed Dashboard KPIs

These values are directly visible on the dashboard (screenshot verified):

| KPI | Value | Notes |
|---|---|---|
| Total Sales | $2,926,970,124 | TotalDue sum across all orders |
| Bikes Sales % | 40.65% | Bikes share of total sales |
| Road Bikes % | 21.3% | Road Bikes share of total sales |
| Products | 295 | Distinct product count |
| Customers | 19,119 | Distinct customer count |
| Sellers | 18 | Distinct salesperson count |

## Confirmed Sales by Region (from PivotTable data)

| Region | Sales (TotalDue) |
|---|---|
| Southwest | $696,896,626 |
| Canada | $526,969,463 |
| Northwest | $411,207,275 |
| Central | $263,099,146 |
| Northeast | $253,771,294 |
| Southeast | $226,427,460 |
| France | $198,158,288 |
| United Kingdom | $187,208,422 |
| Germany | $92,658,226 |
| Australia | $70,573,924 |
| **Total** | **$2,926,970,124** |

## Confirmed Monthly Sales (from PivotTable data)

| Month | Sales |
|---|---|
| Jan | $183,378,293 |
| Feb | $103,403,614 |
| Mar | $382,618,986 |
| Apr | $113,514,051 |
| May | $390,954,185 |
| Jun | $365,654,295 |
| Jul | $360,088,403 |
| Aug | $207,215,346 |
| Sep | $256,880,446 |
| Oct | $311,820,065 |
| Nov | $94,933,254 |
| Dec | $156,509,185 |

## Confirmed Top Sub-Products by Sales (from PivotTable data)

| Rank | Subcategory | Category | Sales |
|---|---|---|---|
| 1 | Road Bikes | Bikes | $624,874,729 |
| 2 | Mountain Bikes | Bikes | $357,041,833 |
| 3 | Road Frames | Components | $240,926,877 |
| 4 | Mountain Frames | Components | $222,743,775 |
| 5 | Touring Bikes | Bikes | $207,928,847 |
| 6 | Jerseys | Clothing | $175,677,570 |
| 7 | Helmets | Accessories | $134,483,767 |
| 8 | Gloves | Clothing | $97,203,913 |
| 9 | Wheels | Components | $94,291,498 |
| 10 | Touring Frames | Components | $84,171,558 |

## Confirmed Sales Category Distribution (from PivotTable data)

| Category | Sales Share |
|---|---|
| Bikes | 40.65% |
| Components | 31.79% |
| Clothing | 18.53% |
| Accessories | 9.02% |

## Dashboard Features Verified

- ✅ PivotTables (hidden **Pivot Data** sheet contains all 28 PivotTables)
- ✅ PivotCharts (18 charts confirmed in **Pivot Data** sheet)
- ✅ Slicers (Category, Order Type, Year — visible in screenshots)
- ✅ Doughnut charts (Bikes %, Road Bikes % KPIs, Online % KPI)
- ✅ Bar charts (multiple orientations)
- ✅ Pie chart (Sales per Category)
- ✅ Line chart (Sales per month)
- ✅ Multi-series bar chart (Month Analysis)
- ✅ Stacked bar chart (Sales Top Products per month)
- ✅ Treemap-style layout (Quantity Top 3 sub-categories per category)
- ✅ Descriptive statistics (**Statistics - Price**, **Statistics - Quantity**)

## Analytical Integrity Notes

- All KPI values are extracted directly from PivotTable output cells or dashboard screenshots.
- No values have been fabricated or estimated.
- The "Offline" channel dominates by sales value ($2.86B vs $65.4M online) because offline orders include the high-value Bike category purchases. The online channel has more orders (27,659 vs 3,806) but lower average order value.
- The descriptive statistics sheets (**Statistics - Price**, **Statistics - Quantity**) indicate the analyst examined price and quantity distributions to understand data spread (mean, median, standard deviation, skewness).
- Sheet names were professionally updated using Excel COM automation (win32com): all generic Sheet names replaced with descriptive names. One genuinely empty sheet (Sheet5) was removed. Sheet2 was retained as **Dashboard - Overview** after Excel confirmed it contained 7 ChartObjects. Excel handled all internal reference updates natively.
