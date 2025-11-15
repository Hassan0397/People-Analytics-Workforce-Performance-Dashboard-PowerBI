# 📊 People Analytics & Workforce Performance Dashboard — Power BI

A **Power BI** project providing HR leaders, managers, and executives with actionable insights into workforce demographics, hiring & attrition trends, employee performance, engagement, and compensation.

---

## 🚨 Problem Statement

Organizations often face challenges in **monitoring workforce health** due to fragmented HR data:

- Limited visibility into headcount trends, hiring, and attrition  
- Difficulty assessing employee performance and engagement  
- Lack of consolidated insights into compensation and span of control  
- Inability to identify high-performing or at-risk employees efficiently  

**This project addresses these issues by consolidating HR data into an interactive Power BI dashboard for actionable workforce insights.**

---

## ✅ Solution

The **People Analytics Dashboard** provides:

- **Workforce KPIs:** Headcount, New Hires, Terminations, Attrition Rate, Tenure  
- **Performance Metrics:** Avg Performance Score, High/Low Performer identification  
- **Engagement Insights:** Survey trends, sentiment distribution, department-level engagement  
- **Compensation Metrics:** Total Salary Cost, Median Salary, Avg Reports per Manager  
- **Interactive Analysis:** Slicers for Date, Department, and Employee attributes  
- **Visual Storytelling:** Executive summary, hiring & attrition trends, performance & talent mapping, engagement, and compensation insights  

This empowers **HR leaders, managers, and executives** to make informed decisions on workforce planning, retention, and performance management.

---

## 🚀 Project Workflow

### 🟦 1. Data Preparation
Datasets used:

- `dim_employee.csv` → Employee master data  
- `dim_department.csv` → Department reference  
- `dim_date.csv` → Date dimension for time intelligence  
- `fact_performance.csv` → Performance review scores  
- `fact_attendance_monthly.csv` → Monthly attendance & absence  
- `fact_compensation.csv` → Salary & compensation  
- `fact_surveys.csv` → Employee engagement scores  
- `fact_events.csv` → HR-related events  

**Cleaning & Transformation:**

- Converted dates (`HireDate`, `ExitDate`, `BirthDate`) to **Date type**  
- Filled missing values and standardized formats  
- Created derived columns:  
  - `AgeYears`, `TenureYears`, `TenureMonths`, `HireYear`, `ManagerName`, `LastReviewDate`, `DaysSinceLastReview`  
- Numeric columns formatted as **Currency, Decimal, Whole Number**  

---

### 🟩 2. Data Modeling
- Built **star schema** with dimension tables: `dim_employee`, `dim_department`, `dim_date`  
- Fact tables: `fact_performance`, `fact_attendance_monthly`, `fact_compensation`, `fact_surveys`, `fact_events`  
- Linked all facts to `dim_employee` using **EmployeeID**  
- Marked `dim_date` as the **official Date Table**  
- Relationships set as **Many-to-One** from facts to dimensions  

---

### 🟨 3. Core DAX Measures

- **Headcount** → `COUNTROWS(dim_employee)`  
- **New Hires** → Employees with hire date in selected period  
- **Terminations** → Employees with exit date in selected period  
- **Attrition Rate** → `DIVIDE([Terminations], [Headcount], 0)`  
- **Avg Tenure (Years)** → Average of `TenureYears`  
- **Avg Perf Score** → Average performance score  
- **Avg Engagement Score** → Average survey score  
- **Absence Rate** → From attendance data  
- **Total Salary Cost** → Sum of salaries  
- **Median Salary** → Median salary across workforce  
- **Avg Reports per Manager** → Span of control  

---

### 🟥 4. Report Pages & Visuals

[**1️⃣ Executive Summary**](https://github.com/Hassan0397/People-Analytics-Workforce-Performance-Dashboard-PowerBI/blob/main/Executive%20Summary%20People%20Analytics.png)

- KPI Cards: Headcount, New Hires, Terminations, Attrition Rate, Avg Tenure, Avg Perf Score  
- Trend lines: Headcount over time  
- Donut charts: Gender split, Active vs Exited  
- Global slicers: Date, Department  

[**2️⃣ Hiring & Attrition**](https://github.com/Hassan0397/People-Analytics-Workforce-Performance-Dashboard-PowerBI/blob/main/Hiring%20%26%20Attrition.png)  

- Clustered Column: New Hires vs Terminations  
- Line Chart: Attrition Rate trend  
- Bar Chart: Attrition by Department  
- Table: Top 10 Departments by terminations  

[**3️⃣ Performance & Talent**](https://github.com/Hassan0397/People-Analytics-Workforce-Performance-Dashboard-PowerBI/blob/main/Performance%20%26%20Tenure%20Overview.png)

- Scatter Plot: Tenure vs Performance (bubble size = salary)  
- Employee table with performance heatmap  
- Highlights: High performers & at-risk employees  

[**4️⃣ Engagement & Surveys**](https://github.com/Hassan0397/People-Analytics-Workforce-Performance-Dashboard-PowerBI/blob/main/Survey%20dashboard.png)

- Line Chart: Engagement trends  
- Donut Chart: Sentiment distribution  
- Bar Chart: Avg Engagement by Department  

[**5️⃣ Compensation & Org Health**](https://github.com/Hassan0397/People-Analytics-Workforce-Performance-Dashboard-PowerBI/blob/main/Compensation%20%26%20Org%20Health.png)

- KPI Cards: Total Salary Cost, Median Salary, Avg Reports per Manager  
- Histogram: Salary distribution  
- Bar Chart: Avg Salary by Department  

---

### 🟪 5. Usage

1. Open the `.pbix` file in **Power BI Desktop**  
2. Refresh data sources if needed (CSV files included)  
3. Use slicers (Date, Department) to interact with dashboards  
4. Navigate through 5 pages for full HR insights  

---

### 🧠 Key Outcomes

- **HR Leaders:** Monitor workforce health, attrition, and engagement  
- **Managers:** Identify top & bottom performers, optimize teams  
- **Executives:** Track trends in compensation, performance, and workforce composition  
- Demonstrates **enterprise-grade Power BI skills** for HR analytics  

---

### 🛠 Tools Used

- **Power BI Desktop**  
- **Power Query** (ETL transformations)  
- **DAX** (KPIs & analytics)  
- **CSV / Excel** for source data  

---

### 📚 Skills Demonstrated

- Data modeling with star schema  
- DAX measures for HR KPIs  
- Professional report & dashboard design  
- Slicer-driven interactivity and cross-filtering  
- Real-world HR analytics scenario building  

