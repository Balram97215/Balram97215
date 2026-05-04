<div align="center">
  <img src="https://github.com/Balram97215/Balram97215/blob/main/profile-pic.jpg?raw=true" width="140px" style="border-radius:50%;" alt="Balram Bhanu Iyengar – profile photo"/>

  <h1>Balram Bhanu Iyengar</h1>
  <h3>Business Intelligence Developer &nbsp;|&nbsp; SQL · Power BI · Superset · Python · ELT</h3>

  <p>
    M.S. Business Analytics · UMass Amherst (Isenberg)
    &nbsp;·&nbsp;
    <em>Operations → Analytics → BI → Engineering</em>
  </p>

  <p>
    <a href="https://www.linkedin.com/in/balram-iyengar-97shree">
      <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
    </a>
    &nbsp;
    <a href="mailto:iyengarbalram97@gmail.com">
      <img src="https://img.shields.io/badge/Email-iyengarbalram97%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
    </a>
  </p>

  <p>
    <img src="https://img.shields.io/badge/Currently_Building-Florida_Real_Estate_Pipeline_%2810.8M_records%29-22c55e?style=flat-square" alt="Currently building"/>
    &nbsp;
    <img src="https://img.shields.io/badge/Learning-dbt_%7C_Airflow_%7C_AWS_Glue-f59e0b?style=flat-square" alt="Currently learning"/>
  </p>
</div>

---

## 🟢 Open to Opportunities

> Seeking full-time **Business Intelligence Developer** or **Analytics Engineer** roles — US-based, hybrid or remote.  
> I also carry the engineering rigor (ELT pipelines, DuckDB, Docker, Python) to step into a **Data Engineer** role as I continue building that stack.  
> Work-authorized in the US · Available now · Background spans supply chain, financial compliance, and healthcare data.

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
| ⏱️ Validation cycle time | **↓ 80%** | NICE Actimize — automated T-SQL → PostgreSQL migration checks |
| 📊 Reporting latency | **↓ 90%** (3 days → <30 min) | IVS — Python ETL replacing manual Excel consolidation |
| 🩺 Data validation errors | **↓ ~40%** | Sparcolife — SQL governance framework for AI-diagnostic integration |
| 🗂️ Pipeline scale delivered | **10.8 M records** | Florida Real Estate — all 68 FL counties in a DuckDB warehouse |

---

## 🗂️ Featured Projects

### 1 · [Florida Real Estate Data Pipeline](https://github.com/Balram97215/Florida_RealEstate_DataPipeline)
> `SQL` `Apache Superset` `DuckDB` `Python` `fiona` `pyproj` `Docker` `Parquet`

**Client:** [Community Dreams Foundation](https://communitydreamsfoundation.org) — nonprofit focused on fair housing policy (pro bono, ongoing).

| | |
|---|---|
| **Business question** | Where is corporate ownership concentrated across Florida, and which counties have the most distorted assessed-vs-just value ratios? No cross-county view existed — analysts downloaded county CSVs manually. |
| **BI output** | **27+ Superset dashboard views** across 8 analytical domains: ownership concentration, valuation trends, sales analysis, building age distribution, and county-level comparisons. Key finding: **21.4% corporate ownership statewide** — the headline metric for fair-housing advocacy. |
| **What made it possible** | To get clean, query-ready data I had to build the plumbing: a 4-phase ELT pipeline processing **10.8 M** parcel records from Esri `.gdb` format (EPSG:6439 → WGS84) into a DuckDB analytical warehouse, with 12+ automated data quality checks before any dashboard was built. |

<details>
<summary>Pipeline architecture</summary>

```
Parcels.gdb (Esri Geodatabase — all 68 FL counties)
       │
       ▼  fiona + pyproj (EPSG:6439 → WGS84)
  EXTRACT → Parquet chunks (50k rows each)
       │
       ▼  DuckDB read_parquet (out-of-core)
   LOAD → staging_parcels
       │
       ▼  SQL execution
TRANSFORM → parcels OBT · sales · ref tables
       │
       ▼  12+ automated quality checks
VALIDATE → PASS / WARN / FAIL per check
       │
       ▼  Docker Compose (Superset + Postgres + Redis)
DASHBOARDS → 27+ v_dash_* views · 8 EDA modules
```

</details>

---

### 2 · [Supply Chain Network Optimizer](https://github.com/Balram97215/Supply_Chain_Network_Optimizer)
> `Power BI` `Python` `Pandas` `Matplotlib` *(Python scripts embedded inside Power BI)*

> ⚠️ **Simulation tool** — built on 10,000+ synthetically generated orders, not live production data.

| | |
|---|---|
| **Business question** | Where should a retailer open a second distribution node to minimise freight cost — and how does the answer change by season or product category? |
| **BI output** | Interactive Power BI dashboard where every user filter (region, season, volume threshold) re-runs a Python Center-of-Gravity calculation live and redraws the optimal hub on the map. Decision-makers get a what-if simulator, not a static chart. |
| **Engineering detail** | Weighted CoG algorithm runs *inside* the Power BI query engine via embedded Python script visuals. Synthetic order data generated with skewed probability distributions to simulate realistic demand patterns. |
| **Simulation result** | Dual-node network (NJ + NV) reduces Zone 8 freight cost by **~18%** and cuts West Coast delivery time by 4 days in the model. |

---

### 3 · [SQL Migration & Validation Framework](https://github.com/Balram97215/SQL-Migration-Case-Study)
> `PostgreSQL` `T-SQL` `PL/pgSQL` `pgAdmin`

**Context:** Internship at NICE Actimize — Financial Crime Compliance (AML / KYC).

| | |
|---|---|
| **Problem** | Migrating Actimize's AML detection library (CDD, WLF, SAM modules) from SQL Server to cloud PostgreSQL. Proprietary T-SQL syntax (`CHARINDEX`, `GETDATE`, `GOTO`, `MONEY` type) caused silent failures in compliance-critical validation scripts. |
| **What I built** | Systematic refactoring to PostgreSQL-native equivalents (`POSITION`, `NOW()`, structured `EXCEPTION` blocks, `NUMERIC`). Paired with a reusable validation taxonomy: null checks, referential integrity, domain integrity, uniqueness. |
| **Impact** | Validation cycle time **↓ 80%**. Framework standardised across AMER/EMEA/APAC. Findings presented to C-suite. |

---

### 4 · [Student Dropout Prediction](https://github.com/Balram97215/Student-Drop-out-Analytics)
> `Python` `scikit-learn` `XGBoost` `Pandas`

**Academic project** — M.S. Business Analytics, UMass Amherst.

| | |
|---|---|
| **Problem** | Universities run blanket retention programs without knowing *which* students are at risk or *why* — expensive and often too late. |
| **What I built** | Voting Classifier (Random Forest + XGBoost ensemble) on 4,424 records with 35 features. Permutation importance surfaced the most actionable signals for early intervention. |
| **Results** | **AUC 0.96 · F1 0.92 · Balanced Accuracy 0.93.** Top finding: tuition non-payment predicts dropout in 87% of cases — actionable for targeted financial-aid outreach. |

---

### 5 · [Employee Attrition Predictor](https://github.com/Balram97215/Employee-Attrition)
> `Python` `scikit-learn` `Pandas` `Logistic Regression`

**Academic project** — M.S. Business Analytics, UMass Amherst.

| | |
|---|---|
| **Problem** | Blanket retention incentives are expensive; HR needs to know *who* is at risk and *why*. |
| **What I built** | End-to-end logistic regression pipeline on 2,940 HR records (33 features, 16% attrition base rate). Prioritised interpretability — model coefficients translate directly into HR action. |
| **Key finding** | Overtime, poor environment satisfaction, long commute, and infrequent promotions were the strongest attrition signals. |

---

## 🛠️ Technical Toolkit

**BI & Reporting** *(primary)*

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Apache Superset](https://img.shields.io/badge/Apache_Superset-20A6C9?style=flat-square&logo=apache&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Scikit--learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-189AB4?style=flat-square&logo=xgboost&logoColor=white)

**Data Engineering** *(differentiator — I build the pipes when the data isn't there yet)*

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FDD835?style=flat-square&logo=duckdb&logoColor=black)
![Parquet](https://img.shields.io/badge/Parquet-50ABF1?style=flat-square&logo=apacheparquet&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

**Currently Building Towards**

![Apache Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white)

**Domain expertise:** Supply Chain Analytics · Financial Crime Compliance (AML/KYC) · Healthcare Data Governance · Lean Six Sigma (Yellow Belt)

---

## 💼 Professional Experience

### Business Intelligence Developer — Pro Bono
**[Community Dreams Foundation](https://communitydreamsfoundation.org)** · *Aug 2025 – Present*
- Building and maintaining a production ELT pipeline processing **10.8 M** Florida property records (all 68 counties) from Esri GDB into a DuckDB analytical warehouse + Superset dashboards.
- Key output: 21.4% statewide corporate ownership concentration — surfaced for fair-housing policy work.

### Business Analytics Intern
**[NICE Actimize](https://github.com/Balram97215/SQL-Migration-Case-Study)** — Financial Crime Compliance · *May 2024 – Jul 2024*
- Migrated AML/KYC data validation library from T-SQL to PostgreSQL-native syntax for a cloud migration covering AMER/EMEA/APAC clients.
- Automated error detection cut validation cycle time **~80%**; presented efficiency gains to C-suite.

### Business Intelligence Developer — Contract
**Sparcolife Digital Healthcare** — Vyli AI-Diagnostic Integration · *Sep 2022 – Aug 2023*
- Translated clinical business rules into SQL specs to integrate an AI diagnostic platform with legacy clinical systems under HIPAA PHI constraints.
- Data governance framework reduced validation errors **~40%** and cut compliance audit cycle by 2 weeks.

### Data Operations Analyst
**[Indian Vellness Solutions (IVS)](https://github.com/Balram97215/IVS-OLHS-Integration)** — Post-Acquisition Supply Chain · *Nov 2021 – Sep 2022*
- Built Python ETL pipelines to integrate a newly acquired division's fragmented data into a central SQL instance — reporting latency from 3 days to <30 min (**90% reduction**).
- Co-developed a Center-of-Gravity network optimizer projecting **15–20% freight cost reduction** for new warehouse placement.

<details>
<summary>Earlier roles (2017 – 2021)</summary>

**Supply Chain Data Analyst · [Transview Enterprise (TVI)](https://github.com/Balram97215/TVI-Product_Development-Supply_Chain_Analytics)** *(Oct 2020 – Oct 2021)*  
DMAIC / Lean Six Sigma initiative for QNET's global e-commerce fulfillment. ABC slotting cut picker travel ~30%; A/B testing framework replaced gut-feel product launches. Eliminated a 3-day packing backlog, restoring SLAs.

**Technical Support Engineer · Fidelis Corporate Solutions (DXC Technology)** *(Mar 2020 – Jun 2020)*  
Enterprise incident triage and root cause analysis for DXC Technology clients.

**Industrial Engineering Trainee · TI Tsubamex Pvt. Ltd.** *(May 2016 – May 2017)*  
Quality control and ISO adherence for precision automotive tooling.

</details>

---

## 👨‍💻 My Story

Operations taught me what bad data costs. Early in my career — managing supply chain data at Indian Vellness Solutions (IVS) and Transview Enterprise (TVI) — I watched capable teams make expensive decisions from 3-day-old Excel files. I didn't fix the decisions; I fixed the reporting.

That's what drew me to BI. I started building dashboards and SQL reports because I could see the direct line between a clean, well-modelled dataset and a better business call. At Sparcolife I owned the data governance layer for a clinical AI integration. At NICE Actimize I automated compliance validation SQL across three global regions. The pattern was consistent: the analyst had the right questions, but the data was never in the right shape.

What separates me from most BI candidates is that I can also build the pipeline when the data isn't there yet. The Florida Real Estate project is the proof: I processed 10.8 M government records from a geospatial format nobody had tackled at the organization, built a DuckDB warehouse from scratch, and then delivered 27+ Superset dashboard views on top of it. I'm a BI developer who doesn't stop at the edge of the source system.

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
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Balram97215&layout=compact&hide_border=true&theme=default" width="40%" alt="Top languages"/>
</div>
<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com?user=Balram97215&hide_border=true&theme=default" width="55%" alt="GitHub streak"/>
</div>

---

<div align="center">
  <em>"Data without context is just noise. Data with context is strategy."</em>
  <br/><br/>
  <a href="https://www.linkedin.com/in/balram-iyengar-97shree">
    <img src="https://img.shields.io/badge/Let's_Connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"/>
  </a>
  &nbsp;
  <a href="mailto:iyengarbalram97@gmail.com">
    <img src="https://img.shields.io/badge/Email_Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email Balram"/>
  </a>
</div>
