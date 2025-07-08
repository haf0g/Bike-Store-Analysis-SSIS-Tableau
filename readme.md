# BikeStores Data Warehouse & ETL Project

## 🚴 Project Overview
This BI project transforms a relational **BikeStores** database into an analytical data warehouse using SSIS, enabling sales performance analysis by store locations and product categories. Includes a Tableau dashboard for visualization.

## 🔧 Key Components

### Data Warehouse Design

- **Star Schema**:
  - **Fact Table**: `ventes` (sales quantities/amounts)
  - **Dimensions**: 
    - `Store` (store → city → state hierarchy)
    - `Product` (product → brand, product → category hierarchies)
- Created via SQL scripts (`Creation_DW_BikeStoresDW.sql`)
>
> ![image](https://github.com/user-attachments/assets/4a53e819-2673-4b27-b2c7-6f0874a3ec67)

### SSIS ETL Pipeline
1. **Data Cleaning**:
   - Auto-reset IDs with `DBCC CHECKIDENT`
   - Truncate tables before each load
2. **Dimension Loading**:
   - Store hierarchy (state → city → store)
   - Product hierarchy (brand/category → product)
3. **Fact Table Population**:
   - Calculates sales amounts (`list_price * quantity`)

### Tableau Dashboard

## 📊 Visualizations

The Tableau dashboard includes the following visualizations:

>
>![image](https://github.com/user-attachments/assets/8226ae5b-719f-4123-a654-29d49feaa20e)
>

- 📅 **Monthly Quantity Sold** – Bar chart showing product quantity sold per month to detect seasonality.
- 📈 **Annual Sales Evolution** – Line chart tracking the total sales per year, highlighting overall growth trends.
- 🚲 **Sales by Bike Category** – Horizontal bar chart comparing total sales across different bike categories.
- 🏷️ **Sales by Brand and Product** – Multi-level circular chart visualizing detailed sales per brand and product.

These visualizations provide a clear overview of sales dynamics across time, product lines, and brands.

## 🛠️ Technologies
- **ETL**: SQL Server Integration Services (SSIS)
- **Data Warehouse**: SQL Server
- **Visualization**: Tableau
- **Source Data**: BikeStores SQL Server database (`sales` + `production` schemas)

## 📊 Key Metrics
- **Sales Amount**: SUM(`montant`)
- **Units Sold**: SUM(`quantity`)
- **Brand/Category Breakdown**

##  Context
Academic project for ENSA's Business Intelligence module (CI-ISBD/S8 - May 2025), supervised by Prof. Hamid Hrimech.

---

*"From relational data to actionable sales analytics."*
