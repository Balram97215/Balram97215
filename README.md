<div align="center">
  <img src="https://github.com/Balram97215/Balram97215/blob/main/profile-pic.jpg?raw=true" width="150px" style="border-radius:50%;" alt="Balram Bhanu Iyengar – profile photo"/>
  <h1>Balram Bhanu Iyengar</h1>
  <h3>Data Engineer &nbsp;·&nbsp; Analytics Engineer &nbsp;·&nbsp; Supply Chain Data Specialist</h3>
  <p><em>"I bridge the gap between Boardroom Strategy and Engine Room Code."</em></p>
  <p>
    <a href="https://www.linkedin.com/in/balram-iyengar-97shree"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
    &nbsp;
    <a href="mailto:iyengarbalram97@gmail.com"><img src="https://img.shields.io/badge/Email-iyengarbalram97%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  </p>
</div>

---

## 🟢 Open to Opportunities

> **Actively seeking** full-time roles as a **Data Engineer**, **Analytics Engineer**, or **Data Platform Engineer** — open to hybrid / remote in the US.  
> M.S. Business Analytics · UMass Amherst (Isenberg School of Management) · Work-authorized · Available now

---

## 📑 Table of Contents

1. [Impact at a Glance](#-impact-at-a-glance)
2. [Featured Projects](#-featured-projects)
3. [Technical Toolkit](#%EF%B8%8F-technical-toolkit)
4. [Professional Experience](#-professional-experience)
5. [My Story](#-my-story)
6. [Certifications](#-certifications)
7. [GitHub Activity](#-github-activity)

---

## ⚡ Impact at a Glance

| Metric | Result | Where |
|--------|--------|-------|
| ⏱️ Data validation cycle time | **↓ 80%** | NICE Actimize — T-SQL → PostgreSQL migration framework |
| 📊 Reporting latency | **↓ 90%** | IVS — Python ETL replacing 3-day manual reporting cycle |
| 🚚 Projected freight cost | **↓ ~15–20%** | Supply chain CoG simulation (synthetic-data model) |
| 🗂️ Data pipeline scale | **10.8M records** | Florida Real Estate — all 68 counties, DuckDB warehouse |

---

## 🗂️ Featured Projects

### 1 · [Florida Real Estate Data Pipeline](https://github.com/Balram97215/Florida_RealEstate_DataPipeline)
> **Stack:** Python · fiona · DuckDB · SQL · Apache Superset · Docker · pyproj

**Built for** [Community Dreams Foundation](https://communitydreamsfoundation.org) — a nonprofit focused on fair housing policy.

| | |
|---|---|
| **Problem** | Florida's Department of Revenue publishes parcel data as Esri `.gdb` files — a geospatial format that requires significant engineering work to process. No existing tooling at the organization; analysts worked from manually downloaded CSVs with no cross-county view. |
| **Approach** | Designed a 4-phase ELT pipeline: extract from `.gdb` using `fiona` + `pyproj` (CRS reprojection EPSG:6439 → WGS84) → chunk to Parquet → load into DuckDB → transform via SQL (OBT, sales, reference tables) → validate with 12+ automated quality checks. Containerised Apache Superset (Docker Compose) for 27+ dashboard views. |
| **Output** | Processed all **10.8 million** Florida parcel records across 68 counties. Key finding: **21.4% corporate ownership concentration** statewide — a headline metric for fair-housing policy analysis. Includes 8 EDA modules and an automated cross-validation layer. |

---

### 2 · [SQL Migration & Validation Framework](https://github.com/Balram97215/SQL-Migration-Case-Study)
> **Stack:** PostgreSQL · T-SQL · PL/pgSQL · pgAdmin

**Built during** internship at NICE Actimize (Financial Crime Compliance — AML/Fraud Detection).

| | |
|---|---|
| **Problem** | Migrating Actimize's AML/KYC solution library from SQL Server / Oracle to cloud PostgreSQL. The existing T-SQL scripts used proprietary functions (`CHARINDEX`, `GETDATE`, `GOTO` flow control, `MONEY` type) incompatible with PostgreSQL — causing silent validation failures in compliance-critical data pipelines. |
| **Approach** | Systematically refactored the T-SQL library to PostgreSQL-native equivalents (`POSITION`, `NOW()`, structured `EXCEPTION` blocks, `NUMERIC`). Built a reusable validation taxonomy covering null checks, referential integrity, domain integrity, and uniqueness — applied across CDD, WLF, and SAM modules. |
| **Impact** | Reduced validation cycle time by **~80%**, standardized the framework across AMER/EMEA/APAC regions, and presented findings directly to the C-suite. |

---

### 3 · [Supply Chain Network Optimizer](https://github.com/Balram97215/Supply_Chain_Network_Optimizer)
> **Stack:** Python · Pandas · Matplotlib · Power BI (embedded Python scripts)

**Note:** This is a simulation tool built on synthetic data (10,000+ generated orders).

| | |
|---|---|
| **Problem** | Logistics teams typically rely on spreadsheet heuristics to decide where to open new distribution nodes — with no dynamic modelling of how demand shift changes the optimal location. |
| **Approach** | Generated realistic order data using skewed probability distributions, then applied a **weighted Center-of-Gravity** algorithm to calculate the mathematically optimal warehouse placement. Embedded the Python calculation engine directly inside Power BI, making the map respond to user filters (region, season, volume threshold) in real time. |
| **Output** | Simulation identified a dual-node network (NJ + NV) that reduces simulated Zone 8 freight cost by **~18%** and cuts West Coast delivery time by 4 days. Tool is reusable for any demand dataset. |

---

### 4 · [Student Dropout Prediction](https://github.com/Balram97215/Student-Drop-out-Analytics)
> **Stack:** Python · scikit-learn · XGBoost · Pandas

**Academic project** — M.S. Business Analytics, UMass Amherst.

| | |
|---|---|
| **Problem** | Institutions spend resources on blanket retention programs without knowing which students are actually at risk — or why. |
| **Approach** | Trained Random Forest, XGBoost, and an ensemble Voting Classifier on 4,424 student records with 35 demographic, academic, and socioeconomic features. Applied permutation importance to identify the top predictive signals. |
| **Results** | Voting Classifier: **AUC 0.96 · F1 0.92 · Balanced Accuracy 0.93**. Top finding: tuition payment status alone predicts dropout in 87% of cases among students with unpaid fees — actionable for early financial-aid intervention. |

---

### 5 · [Employee Attrition Predictor](https://github.com/Balram97215/Employee-Attrition)
> **Stack:** Python · scikit-learn · Pandas · Logistic Regression

**Academic project** — M.S. Business Analytics, UMass Amherst.

| | |
|---|---|
| **Problem** | Blanket retention incentives are costly. HR needs to know *which* employees are at risk and *why* — not just that attrition is high. |
| **Approach** | End-to-end ML pipeline on 2,940 HR records (33 features): cleaning, one-hot encoding, z-score normalization, logistic regression with class weighting for the imbalanced 16% attrition rate. Emphasized interpretability over raw accuracy so HR could act on coefficients. |
| **Key findings** | Overtime, poor environment satisfaction, long commute, and infrequent promotions were the strongest attrition signals — translated into concrete HR intervention priorities. |

---

## 🛠️ Technical Toolkit

| **Data Engineering** | **Languages & Analytics** | **Governance & Methods** |
|---|---|---|
| DuckDB · SQL (PostgreSQL, T-SQL) | Python (Pandas, NumPy, fiona, pyproj) | Master Data Management (MDM) |
| Apache Airflow (learning) · Spark | Scikit-learn · XGBoost · Matplotlib | Data Quality & Validation frameworks |
| Docker · Superset · Parquet | Power BI (DAX) · DAX | Lean Six Sigma (Yellow Belt) |
| AWS (S3, RDS — learning) · Snowflake | Feature Engineering · EDA | Agile / Scrum · Stakeholder Mgmt |

---

## 💼 Professional Experience

### Business Intelligence Developer — Pro Bono
**[Community Dreams Foundation](https://communitydreamsfoundation.org) — Florida Real Estate Analytics** · *Aug 2025 – Present*
- Building a production ELT pipeline processing **10.8 million** Florida property records (all 68 counties) from Esri GDB format into a DuckDB analytical warehouse.
- Delivering 27+ Apache Superset dashboard views surfacing corporate ownership concentration and county-level valuation trends for fair-housing policy work.

### Business Analytics Intern
**[NICE Actimize](https://github.com/Balram97215/SQL-Migration-Case-Study) — Financial Crime Compliance** · *May 2024 – Jul 2024*
- Migrated the AML/KYC data validation script library from T-SQL to PostgreSQL-native syntax for a cloud migration affecting AMER/EMEA/APAC clients.
- Reduced validation cycle time **~80%**; presented findings and efficiency gains directly to C-suite.

### Business Intelligence Developer — Contract
**Sparcolife Digital Healthcare — Vyli AI-Diagnostic Integration** · *Sep 2022 – Aug 2023*
- Translated clinical business rules into SQL technical specifications to integrate the Vyli AI diagnostic platform with legacy systems while maintaining HIPAA-compliant PHI controls.
- Implemented a data governance framework that reduced validation errors by **~40%** and cut the compliance audit cycle by 2 weeks.

### Data Operations Analyst
**[Indian Vellness Solutions (IVS)](https://github.com/Balram97215/IVS-OLHS-Integration) — Post-Acquisition Supply Chain** · *Nov 2021 – Sep 2022*
- Built Python ETL pipelines to integrate the acquired *Oriental Lotus* division's fragmented Excel/CSV data into a central SQL instance, reducing reporting latency from 3 days to under 30 minutes (**90% reduction**).
- Co-developed a Center-of-Gravity network optimizer projecting a **15–20% reduction** in West Coast shipping costs for the new distribution node decision.

<details>
<summary>Earlier roles (2017 – 2021)</summary>

**Supply Chain Data Analyst · [Transview Enterprise (TVI)](https://github.com/Balram97215/TVI-Product_Development-Supply_Chain_Analytics)** *(Oct 2020 – Oct 2021)*  
Applied DMAIC / Lean Six Sigma to eliminate a 3-day packing backlog for QNET's global e-commerce operations. ABC slotting reduced picker travel ~30%; A/B testing framework replaced gut-feel product launches with statistically validated decisions.

**Technical Support Engineer · Fidelis Corporate Solutions (DXC Technology)** *(Mar 2020 – Jun 2020)*  
Enterprise incident triage and root cause analysis, maintaining SLAs for DXC Technology clients.

**Industrial Engineering Trainee · TI Tsubamex Pvt. Ltd.** *(May 2016 – May 2017)*  
Quality control and ISO standards adherence for precision automotive tooling.

</details>

---

## 👨‍💻 My Story

I'm a first-generation M.S. graduate (Business Analytics, UMass Amherst) who spent the early part of my career in operations — where "data" meant urgent spreadsheets, not clean pipelines.

Watching capable teams make costly decisions without reliable data made me realize the gap wasn't skill — it was infrastructure. I self-taught Python and SQL on the job, and each role pushed me further: from manual reporting to ETL automation, from gut-feel decisions to A/B testing, from spreadsheets to production data warehouses.

My 2024 internship at NICE Actimize in financial crime compliance gave me the professional context I needed: real data quality stakes, enterprise-scale SQL, and direct exposure to how data engineering decisions affect compliance outcomes. Today I build pipelines that trade fragility for reliability, and dashboards that trade noise for clarity.

---

## 📜 Certifications

| Certification | Issuer | Status |
|---|---|---|
| Lean Six Sigma Yellow Belt | NIQC International | ✅ Completed |
| Data Analyst in Python | DataCamp | ✅ Completed |
| Data Analyst in Power BI | DataCamp | ✅ Completed |
| Google Project Management | Coursera | 🔄 In Progress |
| DeepMind.AI Data Engineering | Coursera | 🔄 In Progress |

---

## 📊 GitHub Activity

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Balram97215&show_icons=true&theme=default&hide_border=true&count_private=true" width="48%" alt="Balram's GitHub stats"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Balram97215&layout=compact&hide_border=true&theme=default" width="40%" alt="Top languages used by Balram"/>
</div>

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com?user=Balram97215&hide_border=true&theme=default" width="55%" alt="Balram's GitHub streak stats"/>
</div>

---

<div align="center">
  <em>"Data without context is just noise. Data with context is strategy."</em>
  <br/><br/>
  <a href="https://www.linkedin.com/in/balram-iyengar-97shree"><img src="https://img.shields.io/badge/Let's_Connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
  &nbsp;
  <a href="mailto:iyengarbalram97@gmail.com"><img src="https://img.shields.io/badge/Email_Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email Balram"></a>
</div>
