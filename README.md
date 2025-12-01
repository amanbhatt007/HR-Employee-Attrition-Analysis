# HR-Employee-Attrition-Analysis
## Project Objective
This project focuses on a comprehensive analysis of Human Resources data to understand the key factors driving employee attrition (turnover) within an organization. The goal is to identify patterns, build predictive models, and generate actionable insights that can inform HR strategy for improving employee retention and engagement.


## Dataset Used
- <a href="https://github.com/amanbhatt007/HR-Employee-Attrition-Analysis/blob/main/HR-Employee-Attrition.csv">HR Employee Attrition Dataset</a>


##  Questions (KPI)
- What is the current overall employee turnover (attrition) rate?
- Is there a relationship between OverTime and Attrition?
- How does income relate to attrition?
- Which departments are at the highest risk of attrition?
- Do employees leave due to lack of satisfaction with their environment or role?
- Does tenure or lack of career progression drive people to leave?

- Dashboard Interaction <a href="https://github.com/amanbhatt007/HR-Employee-Attrition-Analysis/blob/main/Project%204%20dashboard.png">View Dashboard</a>


## Process
The process for your HR Attrition Analysis project is structured into **four core stages**, strictly following the sequence of tools and data you specified: **Raw Data** $\rightarrow$ **Alteryx** $\rightarrow$ **Clean Data** $\rightarrow$ **Power BI**.

Here are the detailed steps:

***

## Stage 1: Data Ingestion and Source

This stage involves bringing the raw data into the environment where preparation will occur.

**Step 1.1: Identify Raw Data Source**
* **Action:** Locate and select the original, raw HR dataset.
* **Data Used:** **`HR-Employee-Attrition.csv`** (Input File).

**Step 1.2: Ingest Data into Preparation Tool**
* **Action:** Connect the raw CSV file to the input tool within the Alteryx Designer workflow.
* **Tool:** **Alteryx Designer**.

---

## Stage 2: Data Preparation, Cleaning, and Engineering (Alteryx)

This stage, as highlighted by your **`Data Preparation In Alteryx.jpg`**, is where data quality checks, transformations, and feature creation happen.

**Step 2.1: Data Cleansing and Filtering**
* **Action:** Use Alteryx tools (e.g., Data Cleansing Tool, Filter Tool) to:
    * **Handle Nulls/Missing Data** (Verify if any fields have missing values).
    * **Remove Constant Columns** (Drop fields like `EmployeeCount`, `StandardHours`, `Over18` which have no analytical value).
    * **Filter Outliers** or erroneous records, if any.

**Step 2.2: Data Transformation and Formatting**
* **Action:** Use Alteryx Formula and Select tools to:
    * **Convert Binary Variables:** Transform the **`Attrition`** column from text ('Yes'/'No') to a binary number (`1`/`0`) for easier calculation.
    * **Rename Columns:** Standardize column names (e.g., remove spaces or special characters) for better compatibility with the downstream Power BI data model.

**Step 2.3: Feature Engineering**
* **Action:** Use Alteryx Formula and Multi-Field Formula tools to create valuable new features for analysis:
    * Create **Income/Experience Bands** (e.g., **`Income Category`** from `MonthlyIncome` and **`Experience Group`** from `TotalWorkingYears`).
    * Calculate **Engagement Scores** (e.g., averaging `JobSatisfaction`, `EnvironmentSatisfaction`, `JobInvolvement`).

**Step 2.4: Export Clean Data**
* **Action:** Use the Output Data tool in Alteryx to export the completely processed and enriched dataset.
* **Data Produced:** **`Clean_HR_Data.xlsx - Employees.csv`** (Clean Excel/CSV File).
* **Tool:** **Alteryx Designer**.

---

## Stage 3: Analytical Modeling and Metric Calculation

This stage prepares the final metrics and insights that will drive the dashboard design.

**Step 3.1: Load Clean Data**
* **Action:** Import the clean, Alteryx-processed Excel/CSV file into the analytical environment (Power BI).
* **Data Used:** **`Clean_HR_Data.xlsx - Employees.csv`** (Input for Power BI).
* **Tool:** **Power BI Desktop**.

**Step 3.2: Define Key Performance Indicators (KPIs)**
* **Action:** Use Power BI's DAX language to create calculated measures (explicit metrics), such as:
    * `Overall Attrition Rate` ($\text{Count of Attrition = 1 / Total Employees}$).
    * `Average Monthly Income of Attriters`.
    * `Attrition Count by Department`.

**Step 3.3: Data Model Setup**
* **Action:** Define any necessary relationships between the primary employee data and any supplementary tables (e.g., a Date table or HR target table), though likely just one table is needed here.
* **Tool:** **Power BI Desktop**.

---

## Stage 4: Data Visualization and Reporting (Power BI)

This final stage transforms the metrics into the visual dashboard for stakeholder reporting.

**Step 4.1: Dashboard Layout and Design**
* **Action:** Set up the main reporting canvas in Power BI, prioritizing layout and color schemes that align with the HR analytics theme.

**Step 4.2: Visualization Creation**
* **Action:** Create the visual components of the dashboard to answer the core business questions:
    * **Card Visuals:** Display the main KPIs (e.g., Overall Attrition Rate).
    * **Bar Charts:** Show attrition rates segmented by key drivers (e.g., `OverTime`, `Department`, `JobRole`).
    * **Scatter Plots/Histograms:** Visualize the distribution of attriters across numerical factors (e.g., `MonthlyIncome`, `YearsAtCompany`).

**Step 4.3: Final Interactivity and Export**
* **Action:** Add necessary slicers (filters) to allow end-users to drill down (e.g., by `Gender` or `Education Field`). The final report is then saved and published.
* **Output:** The final visual report.
* **Tool:** **Power BI Desktop/Service**. The resulting visualization is represented by **`Project 4 dashboard.png`**.
