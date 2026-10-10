# Executive Supply Chain & Inventory Intelligence System

An operational reporting platform built in Power BI to monitor logistics performance, regional fulfillment rates, inventory distribution, and shipping lead times using a Star Schema data model.

![Dashboard Preview](dashboard_preview.png)

---

## 🛠️ Data Pipeline & Architecture
1. **ETL & Data Transformation:** Processed raw supply chain datasets using Python (Pandas, NumPy) on Google Colab to clean and partition flat data into a Star Schema.
2. **Data Modeling:** Established 1-to-Many ($1:*$) relationships between dimension tables (`Dim_Product`, `Dim_Customer`, `Dim_Warehouse`) and `Fact_Sales`.
3. **DAX Measures:** Calculated key operational performance indicators (KPIs) in Power BI Desktop.

---

## 📊 Core DAX Calculations
- **Total Revenue:** 
  `Total Sales = SUM(Fact_Sales[SalesAmount])`
- **On-Time Delivery Rate (OTD %):** 
  `OTD % = DIVIDE([OnTime Deliveries], COUNTROWS(Fact_Sales), 0)`
- **Average Lead Time:** 
  `Avg Shipping Lead Time = AVERAGE(Fact_Sales[ActualShippingDays])`

---

## 💡 Key Operational Takeaways
- **Fulfillment Health:** Visualized delivery status splits (Advance shipping vs. Late delivery trends).
- **Category Leaders:** Mapped sales performance across product lines against yearly demand shifts.
- **Regional Breakdown:** Highlighted geographical lead times and fulfillment efficiency metrics across global markets.
