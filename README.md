# Healthcare Provider Performance Dashboard

## 📌 Business Context

Healthcare providers and administrators need data-driven insights to evaluate cost efficiency, quality of care, patient outcomes, and operational performance across facilities and regions. This dashboard consolidates key healthcare performance metrics to support strategic decision-making, cost allocation, and quality benchmark analysis.

---

## 🎯 Project Objectives

- Analyze cost and utilization patterns across healthcare providers
- Compare facility performance using interactive visuals
- Identify cost outliers and efficiency gaps
- Support operational and strategic planning decisions

---

## 📊 Key Metrics (KPIs)
| KPI | Description |
|-----|--------------|
| **Total Billing Amount** | Overall revenue generated from healthcare services |
| **Average Billing per Visit** | Average billing per patient visit |
| **Total Insurance Coverage** | Amount covered by insurance policies |
| **Out-of-Pocket Cost** | Amount paid directly by patients |
| **Treatment Cost** | Cost incurred for patient treatment |
| **Room Charges** | Revenue from inpatient room utilization |

---

## 🌐 Dashboard Highlights
- Dual Mode Design: **Light Mode** and **Dark Mode** for user flexibility  
- **Interactive filters** for city, state, patients race and time period  
- Trend visualizations for **Year-over-Year, Quarter-over-Quarter, and Month-over-Month** performance  
- Detailed **Weekday vs Weekend** analysis  
- Departmental trend insights (e.g., Neurology +13.6% weekday growth)

---

## 📈 Trend Analysis Summary
- **YoY Billing:** ↓ 29.6% (2024 → 2025)  
- **Top Quarter:** Q1 with $1.7M billing  
- **Lowest Quarter:** Q4 with $217K billing  
- **Weekday vs Weekend:** 60% higher billing on weekdays  
- **Departmental Growth:** Neurology (+13.6%), Pediatrics (+0.2%)

---

## 🧩 Data Modeling (Star Schema)
This project uses a **Star Schema** for efficient data modeling:

**Fact Table:**  
- `visits` — contains all billing transactions

**Dimension Tables:**   
- `Dimdepartments` – Department ID and name  
- `Dimproviders` – Doctor details and specialization  
- `Dimpatients` – Patient demographics  

This structure enhances **query performance, clarity, and DAX efficiency**.

---

## 🧠 Tools & Techniques Used
- **Power BI Desktop**
- **Power Query Editor**
- **DAX (Data Analysis Expressions)**
- **Data Modeling (Star Schema)**
- **Interactive Visualization Design (Light & Dark Modes)**

---

## 💡 Key Insights
- 66% of total billing covered by insurance  
- Weekday revenue dominates weekends by 60%  
- Cardiology & Orthopedics contribute 70% of total billing  
- Seasonal drop in Q4 revenue — improvement opportunity  
- Neurology shows consistent growth, indicating expansion potential  

---

## 🧭 Business Recommendations
- Focus on high-revenue departments (Cardiology, Orthopedics)  
- Extend weekend operations to balance workload  
- Promote Neurology’s positive trend  
- Optimize insurance handling to maintain 66% coverage  
- Launch engagement initiatives in Q3–Q4 to stabilize revenue  
---
## 🧮 Sample DAX Measures
- DateTable = ADDCOLUMNS(
    CALENDARAUTO(),
    "Year", YEAR([Date]),
    "Month", FORMAT([Date], "mmm"),
    "Monthnum", MONTH([Date]),
    "Weekday", FORMAT([Date], "ddd"),
    "Weeknum", WEEKDAY([Date]),
    "Qtr", "Q-" & FORMAT([Date], "Q"),
    "WeekType", IF(WEEKDAY([Date]) = 1 || WEEKDAY([Date]) = 7, "Weekend", "Weekday")
)
- Total Billing Amount = [Total Medication cost] + [Total Room Charges] + [Total Treatment Cost]
- Average Billing Amount per Visit = DIVIDE([Total Billing], [Total Patients])
---
### 🖼️ Dashboard Previews
![Detail Analysis Dashboard-Light](Images/Detail_Light.png)
![Detail Analysis Dashboard-Dark](Images/Detail_Dark.png)
![Trend Analysis Dashboard-Light](Images/Trend_Light.png)
![Trend Analysis Dashboard-Dark](Images/Trend_Dark.png)

## 🎥 Dashboard Demo Video

Watch the demo here:  
[Healthcare Provider Dashboard Demo](Video/Healthcare_Provider_Dashboard.mp4)



