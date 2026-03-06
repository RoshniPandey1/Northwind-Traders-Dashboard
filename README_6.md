# Northwind Traders Sales Dashboard
### Power BI | Data Analytics Project

---

## Project Overview

| Detail | Info |
|--------|------|
| **Tool** | Power BI Desktop |
| **Dataset** | Northwind Traders |
| **Source** | Maven Analytics Data Playground |
| **Date** | March 2026 |
| **Level** | Beginner |
| **Topics** | Sales Analysis, Customer Analysis, Employee Performance |

---

## Dashboard Preview

> Northwind Traders Sales Dashboard showing KPI cards, Revenue Over Time, Revenue by Category, Orders by Employee and Revenue by Country

---

## Dataset Tables

| Table | Type | Description |
|-------|------|-------------|
| orders | FACT | Order transactions with dates and IDs |
| order_details | FACT | Product level detail per order |
| customers | DIMENSION | Customer company and location info |
| products | DIMENSION | Product names, prices and categories |
| categories | DIMENSION | Product category names |
| employees | DIMENSION | Employee names and titles |
| shippers | DIMENSION | Shipping company names |

---

## Data Model - Star Schema

```
customers ───────────────┐
employees ───────────────┤
shippers  ───────────────┼──> orders ──> order_details <── products <── categories
```

- FACT Tables: orders, order_details
- DIMENSION Tables: customers, employees, shippers, products, categories
- All relationships: One-to-Many | Single cross-filter direction

---

## DAX Measures Created

```dax
Total Revenue = 
SUMX(order_details, order_details[quantity] * order_details[unitPrice])

Total Orders = 
COUNTROWS(orders)

Total Customers = 
DISTINCTCOUNT(orders[customerID])

Average Order Value = 
DIVIDE([Total Revenue], [Total Orders], 0)

Total Discount = 
SUMX(order_details, 
    order_details[quantity] * 
    order_details[unitPrice] * 
    order_details[discount])
```

---

## Dashboard Features

- 4 KPI Cards: Total Revenue, Total Orders, Total Customers, Average Order Value
- Line Chart: Revenue Over Time (monthly trend)
- Bar Chart: Revenue by Category
- Bar Chart: Orders by Employee
- Column Chart: Revenue by Country
- Dropdown Slicer: Filter by Product Category
- Interactive: All visuals filter together via slicer

---

## Key Business Insights

- **Top Category**: Beverages generates highest revenue
- **Top Employee**: Margaret Peacock has highest total orders
- **Top Country**: USA is the highest revenue country
- **Revenue Trend**: Steady growth from 2013 to early 2015
- **Total Revenue**: $1.35M across 830 orders from 89 customers

---

## Verified Results

| Metric | Value |
|--------|-------|
| Total Revenue | $1.35M |
| Total Orders | 830 |
| Total Customers | 89 |
| Average Order Value | $1.63K |
| Top Category | Beverages |
| Top Employee | Margaret Peacock |
| Top Country | USA |

---

## Tools and Skills Used

- Power BI Desktop
- Power Query (ETL, data cleaning)
- DAX (SUMX, COUNTROWS, DISTINCTCOUNT, DIVIDE)
- Data Modeling (Star Schema)
- Data Visualization

---

## Connect With Me

- GitHub: [github.com/RoshniPandey1](https://github.com/RoshniPandey1)
- LinkedIn: [linkedin.com/in/roshni-pandey-827988215](https://linkedin.com/in/roshni-pandey-827988215)
