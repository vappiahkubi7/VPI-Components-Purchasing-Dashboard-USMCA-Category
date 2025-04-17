# 📦 VPI Components Purchasing Dashboard – USMCA Category

**This **Purchasing dashboard** provides real-time visibility into the purchasing performance of VPI components within the USMCA region. It tracks key procurement KPIs such as on-time delivery, lead times, and category spend, enabling procurement teams to identify supplier issues, optimize sourcing decisions, and improve supply chain efficiency for 7.2L engine manufacturing.

![IMG_6484WEB](https://github.com/user-attachments/assets/ea5cc2cd-8972-4e4d-a379-e54f65279b32)

---

## 🧾 INTRODUCTION

This project delivers a **data-driven purchasing dashboard** designed to support strategic sourcing decisions for **VPI (Value Package Introduction)** components in the USMCA region. Built using **Power BI** and **Excel**, the dashboard consolidates key purchasing data across suppliers, focusing on **delivery reliability**, **lead time consistency**, and **spend performance**.

The project simulates a real-world procurement scenario where stakeholders require timely and insightful analysis of **supplier performance KPIs** to ensure components are sourced efficiently, on time, and within budget for **7.2L engine production lines**.

---

## 🚨 Problem Statement

In today’s fast-paced global supply chains, supplier delays and procurement inefficiencies continue to disrupt production and impact cost. To support the sourcing of 7.2L engine components across the USMCA region, the VPI Purchasing Team developed an interactive Power BI dashboard to monitor supplier performance, track delivery timelines, and provide real-time visibility into key purchasing KPIs.

Given the complexity and time sensitivity of VPI (Value Package Introduction) programs where hundreds of components are sourced across borders, the need for a centralized, data-driven solution was critical. This dashboard enables the team to move from reactive issue management to proactive procurement planning by visualizing on-time delivery, lead time trends, category spend, and PO fulfillment metrics.

Built using Power BI, Excel, and DAX, the solution delivers actionable insights for both operational teams and senior stakeholders, helping to mitigate risk, benchmark supplier performance, and ensure procurement alignment with production schedules.

---

## 🎯 Aim of the Project

- To create a **dynamic procurement dashboard** that offers stakeholders real-time insights into **supplier performance**, **delivery timelines**, **purchase orders**, and **spend trends**.  
- To improve visibility into **vendor reliability** and **category spend**, enabling smarter negotiation, risk mitigation, and forecasting strategies.

---

## 🛠 Skills and Concepts Demonstrated

- Procurement analytics and supply chain visualization  
- DAX (Data Analysis Expressions) for KPI modeling  
- Dashboard storytelling and UX  
- Vendor performance tracking  
- Excel data wrangling and transformation  
- Lead time analysis and exception reporting  

---

## 🧰 SQL & Power BI Tools and Features Used

- **Excel** for initial data transformation and formatting  
- **Power BI Desktop** for dashboard design  
- **DAX measures** to calculate:
  - On-Time Delivery %  
  - Average Lead Time  
  - PO Cycle Time  
  - Supplier Count per Category  
- **Slicers and drill-downs** for interactivity  
- **Conditional formatting** to highlight delayed shipments  
- **Custom tooltips** for additional KPI descriptions  
- **Power Query** to clean and join datasets  

---

## 📦 Modelling

The data model was structured around **three core tables**:  
- `PurchaseOrders`: Contains order lines, delivery dates, and quantities  
- `Suppliers`: Master data including category and region (US, Mexico, Canada)  
- `DeliveryLogs`: Actual delivery timestamps and exceptions

**Key Measures Developed:**
- `OnTimeDeliveryRate = CALCULATE(...)`  
- `AverageLeadTime = AVERAGEX(...)`  
- `LateDeliveriesCount = COUNTROWS(FILTER(...))`

Relationships were created between `SupplierID` and `OrderID` fields to ensure accurate filtering and aggregation across the visuals.

---

## 📊 Data Analysis and Visualization

**Main Dashboard Panels Include:**

  OnTimeDeliveryRate = 
  CALCULATE(
      DIVIDE(COUNTROWS(FILTER(DeliveryLogs, DeliveryLogs[DeliveredOnTime] = TRUE())), COUNTROWS(DeliveryLogs))
  )

  AverageLeadTime = 
  AVERAGEX(
      DeliveryLogs,
      DATEDIFF(PurchaseOrders[OrderDate], DeliveryLogs[DeliveryDate], DAY)
  )

  LateDeliveriesCount = 
  COUNTROWS(
      FILTER(DeliveryLogs, DeliveryLogs[DeliveredOnTime] = FALSE())
  )

- 🔹 **Supplier Performance Overview**  
  - Bar chart comparing On-Time Delivery % by supplier  
  - Highlighted suppliers with <80% reliability  

- 🔹 **Delivery Timeline Tracker**  
  - Line chart of average delivery days per vendor over time  
  - Trend line showing improvements or deterioration  

- 🔹 **PO Fulfillment Matrix**  
  - Matrix view for POs issued vs delivered by region  
  - Filters for country, month, and category  

- 🔹 **Spend by Category**  
  - Treemap and stacked bar charts showing spend distribution by part category  
  - Breakdown by USMCA region  

- 🔹 **Late Delivery Alert Table**  
  - Conditional formatting used to flag suppliers with late deliveries  
  - Custom tooltip to display delivery deviation in days  

---

## ✅ Recommendation

- **Initiate strategic supplier reviews** for the 3 vendors with <75% on-time performance  
- Adjust **safety stock and lead time buffers** based on historic delay trends  
- Expand dashboard integration to include **cost variance**, **return rates**, and **vendor quality metrics**  
- Utilize Power BI **alerts and subscriptions** for weekly performance monitoring  

---

## 📁 Project Files

- `PowerBI_Report.pbix` – Complete Power BI file  
- `data/` – Contains sanitized sample Excel datasets  
- `analysis-notes.md` – Summary of key takeaways  
- `screenshots/` – Visuals for README preview

---

## 📚 Learning Outcomes

- Gained experience designing a procurement-focused dashboard using **real-world KPIs**  
- Applied **DAX logic** to build dynamic performance metrics  
- Practiced **dashboard storytelling** and **data modeling best practices**  
- Strengthened skills in **root cause analysis** and actionable recommendation building

---

## 🖼️ Preview

![Dashboard Screenshot](screenshots/dashboard-overview.png)

---

> _“Procurement dashboards aren't just about visuals — they’re decision-making tools that drive cost efficiency, performance visibility, and supplier accountability.”_
