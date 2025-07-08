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
*(See attached .twb file)*  
**Visualizations**:
- Sales by state/city (map)
- Revenue by brand/category (treemap)
- Quarterly sales trends (line chart)
- Top-performing stores (bar chart)


## 🛠️ Technologies
- **ETL**: SQL Server Integration Services (SSIS)
- **Data Warehouse**: SQL Server
- **Visualization**: Tableau
- **Source Data**: BikeStores SQL database (`sales` + `production` schemas)

## 📊 Key Metrics
- **Sales Amount**: SUM(`montant`)
- **Units Sold**: SUM(`quantity`)
- **Brand/Category Breakdown**

##  Context
Academic project for ENSA's Business Intelligence module (CI-ISBD/S8 - May 2025), supervised by Prof. Hamid Hrimech.

---

*"From relational data to actionable sales analytics."*