# HR Analytics Tool 

Interactive **HR dashboard** built in **Power BI** to monitor workforce health across **Headcount, Retention, and Turnover**.  
The report is delivered as a single Power BI file: **`HR_Tool_Completed.pbix`** (~13 MB).

---

## What’s Inside

### Pages
- **Cover Page** – landing page / navigation
- **Headcount** – current workforce size + demographic and org breakdowns
- **Retention** – retention trend and comparisons across dimensions
- **Turnover** – turnover rate, departing employees, reasons/types, and termination details table
- **Tooltip** – custom tooltip page used by visuals

---

## Key KPIs (Measures)
This report includes the following core measures:
- **Headcount**
- **Retention**
- **Turnover %**
- **Departing Employees**
- **Starting Headcount (Text KPI)**
- **Ending Headcount (Text KPI)**
- **Avg. # of Employees (Text KPI)**
- **Min–Max Retention** (used for comparative trend visuals)

---

## Main Analyses by Page

### Headcount
Breakdowns of **Headcount** by:
- **Department → Sub-department** (drilldown)
- **Job level**
- **Location / City**
- **Gender**
- **Age & Age Group**
- **Race**
- **Education**
- **Marital Status**
- Includes a **Year slicer** (`Date.Year`)

### Retention
- **Retention trend over time** (by `Date.Year`)
- Retention by:
  - **Department / Sub-department**
  - **Job level**
- A **Parameter slicer** (`Parameter.Parameter`) to switch the comparison dimension in certain visuals
- Demographic and education-based comparisons using **Min–Max Retention**
- **Starting vs Ending headcount** shown as KPI text cards

### Turnover
- **Turnover % trend** over time (`Date.Year`)
- Turnover % by:
  - **Department / Sub-department**
  - **Job level**
- **Departing employees** split by:
  - **Termination type** (`term_dim.term_type`)
  - **Termination reason** (`term_dim.term_reason`)
- Terminations detail **table** including:
  - **Employee name**, **termination date**, **department**, **salary**, **departing employees measure**
- Additional demographic/education cuts (gender, race, age group, education)

---

## Data Model (Tables Observed)
The report follows a star-style model with a people fact table and multiple dimensions:

**Fact**
- `people_fact` (e.g., Full Name, salary, term_date)

**Dimensions**
- `Date`
- `department_dim` (department, sub-department)
- `job_level_dim`
- `location_dim` (location, location_city)
- `demographic_dim` (gender, race, age, Age Group)
- `education_dim`
- `marital_dim`
- `term_dim` (term_type, term_reason)

---

## How to Use

### Open the report
1. Install **Power BI Desktop**
2. Open `HR_Tool_Completed.pbix`
3. Use slicers (ex: **Year**) and click bars/segments to cross-filter other visuals

### Refresh data (if connected)
- Home → **Refresh**
- If the PBIX uses external sources, update credentials in:
  - File → Options and settings → **Data source settings**

---

## Recommended Repo Structure

