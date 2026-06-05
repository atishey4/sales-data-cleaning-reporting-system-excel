# 🧹 Sales Data Cleaning & Reporting System (Excel)

An **Excel** dashboard that cleans messy raw sales data and generates automated summary reports — with
**real pivot tables, pivot charts, slicers, and a Calc sheet** for data-quality + KPI calculations.

Workbook: [`dashboard/Sales Data Cleaning & Reporting System.xlsx`](dashboard/Sales%20Data%20Cleaning%20&%20Reporting%20System.xlsx)

---

## 🎯 Objective
Turn unreliable raw sales exports into a trustworthy, report-ready dataset, and quantify the data-quality
issues that distort business reporting.

## 📦 Data
- **`data/sales_raw.csv`** — intentionally *dirty* (missing values, duplicate Order IDs, misspelled/inconsistent
  categories e.g. "Electronicss"/"fashion", mixed date formats, outliers, invalid prices). **157 records.**
- **`data/sales_clean.csv`** — the cleaned, standardised dataset. **150 records.**

Columns: Order ID, Customer ID/Name, Order Date, Region, State, Product Category, Product Name,
Quantity Sold, Unit Price, Sales Amount, Discount %, Profit Amount, Sales Representative, Payment Method,
Delivery Status.

## 🛠️ How the workbook is built (sheets)
- **RawData** — the dirty source (Excel Table `tblRaw`).
- **Data** — the cleaned source (Excel Table `tblSales`) that feeds all pivots.
- **Calc** — live formulas: reporting KPIs **and** a data-quality panel (`COUNTBLANK`, `COUNTIF`,
  `SUMPRODUCT` for duplicates/distinct, outlier/invalid counts) comparing raw vs clean.
- **PivotData** (hidden) — the PivotTables backing the charts.
- **Dashboard** — KPI cards + 6 charts + 4 slicers.

## 📊 Dashboard
KPI cards (Total Sales, Total Profit, Profit Margin, Total Orders, Avg Order Value) +
**real pivot charts**: Sales by Region, Sales by Category, Sales by Sales Rep, Monthly Sales Trend,
Orders by Delivery Status, and a **Data-Quality Issues** chart. **Slicers** (Region, Product Category,
Payment Method, Sales Representative) filter every pivot at once.

## 💡 Key Insights (sample data)
- Cleaning removed/flagged: **5 duplicate Order IDs, ~16 missing Profit values, 1 outlier, 1 invalid price**, and standardised category spellings → **157 raw → 150 clean** records.
- Post-clean reporting: **Total Sales ≈ ₹25.8 L, Profit ≈ ₹4.1 L, Margin ≈ 16%**, 150 orders, 39 customers.
- Uncleaned data would have **double-counted ~5 orders and mis-grouped categories**, distorting every KPI.

## 🚀 Open it
Open the `.xlsx` in **Excel 2016+**. Use the slicers on the Dashboard sheet; **Data → Refresh All** to
recompute pivots if you edit the data. The Calc sheet shows the underlying formulas.

## ✅ Conclusion
Demonstrates the core data-analyst workflow — profiling, cleaning, validation, and automated reporting —
entirely in Excel with maintainable, formula-driven logic.
