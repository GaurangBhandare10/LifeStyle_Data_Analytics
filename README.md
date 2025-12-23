# Lifestyle Data Analytics – DWBI Project

## Project Overview
This project presents an end-to-end data warehousing and business intelligence solution designed to analyze lifestyle, fitness, and nutrition data. The objective is to understand how workout habits, dietary choices, and daily behaviors influence overall health outcomes. The solution follows a **Medallion Architecture (Bronze–Silver–Gold)** implemented in **Databricks**, with interactive dashboards built in **Power BI** for analytical consumption.

---

## Architecture & Technology Stack
- **Data Storage & Processing:** Azure Databricks (Delta Lake)
- **Architecture Pattern:** Medallion Architecture (Bronze → Silver → Gold)
- **Data Source:** CSV-based lifestyle and fitness dataset
- **Visualization Tool:** Microsoft Power BI
- **Workflow Orchestration:** Databricks Workflows
- **Query Engine:** Spark SQL & PySpark

---

## ETL Pipeline Design

### Bronze Layer (Raw Ingestion)
The Bronze layer stores raw lifestyle data ingested directly from CSV files into Databricks tables. This layer preserves the original structure and values without transformations, ensuring data traceability and reproducibility. A dedicated schema was created in Databricks to organize the dataset at the ingestion stage.

### Silver Layer (Data Cleansing & Enrichment)
The Silver layer focuses on data quality improvement and feature engineering. Key transformations include:
- BMI-based weight categorization
- Workout-based activity level classification
- Experience level grouping
- Fitness goal derivation (Gain vs Cut)
- Age range segmentation
- Standardized column naming conventions

These transformations convert raw attributes into meaningful analytical dimensions suitable for reporting and downstream analytics.

### Gold Layer (Analytics-Ready Data)
The Gold layer contains curated, analytics-ready tables optimized for visualization. Numeric fields are rounded for consistency, derived columns are finalized, and irrelevant records are filtered. This layer serves as the single source of truth for Power BI dashboards and KPI calculations.

---

## Automated Databricks Workflow
The entire ETL process is orchestrated using **Databricks Workflows**, which automatically execute the Bronze-to-Silver and Silver-to-Gold notebooks in sequence. This ensures data freshness, minimizes manual intervention, and maintains pipeline reliability. The workflow design supports scalability and aligns with enterprise-grade data engineering practices.
<p align="center"> <img width="250" height="250" alt="Databricks Workflow" src="https://github.com/user-attachments/assets/f0f6ef5a-2fb3-4c51-b37b-a6040ed66b1a" /> </p> <p align="center"> <img width="300" height="300" alt="Medallion Architecture" src="https://github.com/user-attachments/assets/c706423b-5754-4412-975d-3cc3ef47059e" /> </p>
---

## Power BI Integration
Databricks is directly connected to Power BI using optimized connectors, allowing real-time access to Gold-layer views. Measures and KPIs were created within Power BI using DAX to enhance analytical depth without modifying backend tables.
<p align="center"> <img width="435" height="233" alt="Power BI Connection" src="https://github.com/user-attachments/assets/3e17f99f-21ef-4884-be3d-62feb514b7b6" /> </p>
---

## Dashboards Overview

### 1. Fitness Performance Dashboard
<p align="center"> <img width="455" height="291" alt="Fitness Dashboard" src="https://github.com/user-attachments/assets/738f164c-5f17-49bf-8e58-e9da0c069990" /> </p>
This dashboard answers questions such as:
- Which workout types burn the most calories?
- How does workout intensity vary across age groups?
- How does activity level influence calorie burn?

### 2. Nutrition Insights Dashboard
<p align="center"> <img width="534" height="286" alt="Nutrition Dashboard" src="https://github.com/user-attachments/assets/01f8bb10-5b3f-4b9c-9ac8-395296161587" /> </p>
This dashboard focuses on dietary analysis and answers:
- How do different diet types affect calorie intake?
- What is the balance between macronutrients?
- How efficient is calorie consumption relative to calorie burn?
  

### 3. Lifestyle Drill-Down Dashboard
<p align="center"> <img width="516" height="294" alt="Drill Down Dashboard" src="https://github.com/user-attachments/assets/3a4957c0-babb-4351-896f-f13a0ec4905f" /> </p
This interactive dashboard enables deeper exploration by:
- Diet type
- Age group
- Fitness goal
- Activity level

Users can drill down into specific segments to identify patterns and personalize insights.

---

## Key Metrics & KPIs
- **Calorie Efficiency Ratio:** Calories Burned ÷ Calories Consumed
- **Diet Efficiency Index (DEI):** Weighted macronutrient contribution per calorie
- **Muscle Engagement Count:** Exercise diversity indicator
- **Nutrient Averages:** Sugar, proteins, fats, sodium, and cholesterol
- **Health Score:** Composite metric based on sugar and cholesterol intake

---

## Key Features
- Fully automated ETL pipeline using Databricks Workflows
- Scalable Medallion Architecture implementation
- Clean separation between raw, refined, and analytics-ready data
- Interactive Power BI dashboards with drill-down capabilities
- Business-ready KPIs aligned with fitness and nutrition analytics

---

## Target Users
- Fitness enthusiasts seeking data-driven insights
- Nutrition and wellness platforms
- Fitness trainers and nutrition coaches
- Students and professionals studying DWBI concepts

---

## Conclusion
This project demonstrates the practical application of data warehousing and business intelligence concepts using modern cloud-based tools. By combining Databricks, Delta Lake, and Power BI, the solution delivers scalable data processing, reliable analytics, and meaningful visual insights aligned with real-world health and fitness use cases.

---

## Author
**Gaurang Bhandare**  
DWBI Project – Lifestyle Data Analytics
