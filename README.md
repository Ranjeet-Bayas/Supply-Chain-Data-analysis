# # Supply Chain Analysis – Power BI Dashboard

An end-to-end interactive Power BI report for monitoring and analysing supply chain performance across four key domains: **Supplier**, **Inventory**, **Shipment**, and **Customer**. The dashboard enables stakeholders to track operational KPIs, identify bottlenecks, and make data-driven decisions across the supply chain lifecycle.

---

## 📊 Report Overview

| Property | Detail |
|---|---|
| File | `supply_chain.pbix` |
| Tool | Microsoft Power BI Desktop |
| Pages | 1 (with navigation sections) |
| Data Model | Star schema – Fact + Dimension tables |
| Sections | Overview · Supplier · Inventory · Shipment · Customer |

---

## 🧭 Dashboard Sections

The report uses navigation buttons to switch between the following views on a single canvas:

### 🔵 Overview
A high-level snapshot of the entire supply chain.

| KPI Card | Metric |
|---|---|
| Total Revenue | Overall revenue generated |
| Profit | Net profit value |
| Profit Margin % | Profitability ratio |
| Total Shipments | Count of all shipments |
| Gross Revenue | Sum of gross revenue from sales |
| Total Sales Cost | Overall cost of sales |

---

### 🏭 Supplier
Focus on supplier performance and lead times.

| KPI Card | Metric |
|---|---|
| Order Quantity | Total units ordered from suppliers |

| Chart | Type | Description |
|---|---|---|
| Avg Lead Time of Supplier | Clustered Bar Chart | Average lead time (days) per supplier name |

---

### 📦 Inventory
Track stock levels and product value.

| KPI Card | Metric |
|---|---|
| Inventory Value | Total monetary value of current stock |

| Chart | Type | Description |
|---|---|---|
| Inventory Stock | Clustered Bar Chart | Inventory value broken down by product name |

---

### 🚚 Shipment
Monitor shipment volumes, delays, and carrier performance.

| KPI Card | Metric |
|---|---|
| Total Shipment Quantity | Total units shipped |
| Delivered Quantity | Units successfully delivered |
| Total Shipments | Overall shipment count |

| Chart | Type | Description |
|---|---|---|
| Total Delay in Shipment | Clustered Bar Chart | Total delay duration per carrier |

---

### 👤 Customer
Understand revenue contribution per customer.

| Chart | Type | Description |
|---|---|---|
| Revenue by Customer | Clustered Bar Chart | Total revenue attributed to each customer |

---

## 🗂️ Data Model

The report follows a **star schema** structure with the following tables:

### Fact Tables

| Table | Description |
|---|---|
| `fact_sales` | Sales transactions including gross revenue and sales cost |
| `fact_shipment` | Shipment records including carrier, quantity, and delay data |

### Dimension Tables

| Table | Key Fields | Description |
|---|---|---|
| `dim_supplier` | `supplier_name` | Supplier master data including lead times |
| `dim_product` | `product_name` | Product catalogue |
| `dim_customer` | `customer_name` | Customer master data |

### Measures Table (`TableMeasures`)

| Measure | Description |
|---|---|
| `Total Revenue` | Total revenue across all sales |
| `Profit` | Revenue minus costs |
| `Profit Margin %` | Profit as a percentage of revenue |
| `Gross Revenue` | Sum of gross revenue from fact_sales |
| `Total Sales Cost` | Sum of all sales costs |
| `Order Quantity` | Total units ordered |
| `Inventory Value` | Current total stock value |
| `Total Shipment Quantity` | Total units dispatched |
| `Delivered Quantity` | Units confirmed delivered |
| `Total Shipments` | Count of shipment records |
| `Total Delay` | Cumulative shipment delay |
| `Avg Lead Time` | Average supplier lead time in days |

---

## 🚀 Getting Started

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (latest version recommended)

### Opening the Report

1. Clone or download this repository.
2. Open **Power BI Desktop**.
3. Go to **File → Open report** and select `supply_chain.pbix`.
4. The report loads with the embedded data model — no additional data connection setup required.

---

## 🔄 Refreshing / Updating Data

If you connect this report to a live data source:

1. Open **Home → Transform data** to launch Power Query Editor.
2. Update connection strings under **Home → Data source settings**.
3. Ensure your live tables match the schema of `fact_sales`, `fact_shipment`, `dim_supplier`, `dim_product`, and `dim_customer`.
4. Click **Refresh** to reload the latest data.

---

## 📐 Navigation

The report uses **action buttons** for section-based navigation:
- Click **Supplier**, **Inventory**, **Shipment**, or **Customer** buttons to jump to the relevant view.
- Click **Overview** to return to the summary page.

> Hold `Ctrl` and click buttons in Edit mode to trigger navigation inside Power BI Desktop.

---

## 📌 Notes

- The data model is fully embedded in the `.pbix` file.
- A custom theme is applied for consistent branding and colour palette.
- Images and background shapes are used for visual layout and section structuring.
- All KPI cards and charts are connected to the `TableMeasures` table for centralised metric management.

---

## 📄 License

This project is intended for internal supply chain analytics and reporting. Please review your organisation's data governance policy before publishing or distributing this report.
