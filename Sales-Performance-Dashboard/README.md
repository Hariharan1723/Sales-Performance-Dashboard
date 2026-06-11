# 📊 Sales Performance Dashboard — Power BI

A two-page interactive Power BI dashboard built for monthly business reviews, covering sales KPIs, target achievement, delivery delays, and return rate diagnostics.

---

## 🖼️ Dashboard Preview

### Page 1 — Business Performance Overview
![Page 1 Overview](screenshots/page1_overview.png)

### Page 2 — Sales Diagnostic: Target, Returns & Delays
![Page 2 Diagnostic](screenshots/page2_diagnostic.png)

---

## 📁 Repository Structure

```
Sales-Performance-Dashboard/
│
├── data/
│   └── sales_data.csv             # Source data used in the dashboard
│
├── dashboard/
│   └── Sales_Dashboard.pbix       # Power BI report file
│
├── screenshots/
│   └── page1_overview.png         # Dashboard Page 1 screenshot
│   └── page2_diagnostic.png       # Dashboard Page 2 screenshot
│
└── README.md
```

---

## 📌 Project Overview

| Detail | Info |
|---|---|
| **Tool** | Microsoft Power BI Desktop |
| **Data Source** | Excel / CSV (Sales transactions 2015–2018) |
| **Pages** | 2 |
| **Domain** | Retail Sales Analytics |
| **Use Case** | Monthly Business Review for Sales Manager |

---

## 📄 Page 1 — Business Performance Dashboard

Provides a high-level view of overall business health for the selected year.

**KPI Cards (with YoY comparison)**
- Total Orders — with % change vs Last Year
- Total Sales — with % change vs Last Year
- Total Profit — with % change vs Last Year
- Profit Margin % — with % point change vs Last Year

**Charts**
- 📅 Orders Month-Wise (Bar Chart) — identifies seasonal peaks
- 📈 YoY Sales Trend 2015–2018 (Line Chart) — tracks long-term growth
- 🗂️ Sales by Category (Bar Chart) — Technology, Office Supplies, Furniture
- 🗺️ Sales by Region (Bar Chart) — Central, North, South
- 👥 Sales by Segment (Donut Chart) — Consumer, Corporate, Home Office

---

## 📄 Page 2 — Sales Diagnostic

Drills into performance gaps, delivery issues, and return patterns.

**Headline KPIs**
- 🎯 Target Achievement %
- ⏱️ Delivery Delay Rate %
- 🔁 Return Rate %

**Visuals**
- Target Achievement Matrix (Year × Category) — with conditional formatting (Green/Red)
- Manager × Category Achievement Table — regional accountability view
- Sales vs Target Bar Chart (by Category)
- Return Rate % by Year (trend)
- Delivery Delay % by Ship Mode

---

## 💡 Key Business Insights (2018)

- ✅ **Orders grew 26.7% YoY** — business momentum is strong
- ✅ **Sales crossed ₹1.04M** — up 36.2% vs last year
- ✅ **Profit Margin improved to 12.37%** — up 3.8 percentage points
- ✅ **Target Achievement at 125%** — all categories beating targets in 2018
- ⚠️ **Delay Rate at 35.7%** — 1 in 3 orders arriving late; Second Class shipping worst at 41.1%
- ⚠️ **Furniture missed targets in 2015–2017** — 2018 recovery needs monitoring
- ⚠️ **Return Rate at 6.5%** — peaked in 2017, improving but not back to 2015 levels

---

## 🛠️ DAX Highlights

Key measures used in this dashboard:

```DAX
-- YoY Sales Growth %
YoY Sales % = 
DIVIDE(
    [Total Sales] - [LY Sales],
    [LY Sales]
)

-- Target Achievement %
Target Achievement % = 
DIVIDE([Total Sales], [Total Target])

-- Delivery Delay Rate %
Delay Rate % = 
DIVIDE(
    COUNTROWS(FILTER('Orders', 'Orders'[Delivery Status] = "Delayed")),
    COUNTROWS('Orders')
)
```

---

## 🚀 How to Use

1. Download or clone this repository
2. Open `dashboard/Sales_Dashboard.pbix` in **Power BI Desktop**
3. If prompted, update the data source path to point to `data/sales_data.csv`
4. Refresh the data — all visuals will populate automatically
5. Use the **Year slicer** on Page 1 to filter by year (2015–2018)

---

## 👤 Author

**Hariharan B**
- GitHub: (https://github.com/hariharan1723)
- LinkedIn:(https://www.linkedin.com/in/hariharanbalamurugan)
---

## 📃 License

This project is for portfolio and demonstration purposes.
