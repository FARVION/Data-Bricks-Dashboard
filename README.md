# 🌍 US Emission Dashboard — Databricks Project

> **Scenario:** Contracted by the Environmental Protection Agency (EPA) to build an interactive emission analytics dashboard that identifies *where*, *when*, and *which locations* greenhouse gas emissions are most concentrated across the United States.

---

The dashboard surfaces EPA 2023 emissions data with four core visualizations:
- **Geo Spot Map** — Emission hotspots plotted across all US counties
- **Emission vs Population Scatter Plot** — Per-capita emission patterns by county
- **Top 10 States Donut Chart** — Texas, Florida, Ohio, Illinois and 6 others account for 51% of all US emissions
- **Total Emissions Bar Chart** — Top counties ranked by mTon CO₂e (Maricopa County, AZ leads at 9.81M)

---

## 🛠️ Tech Stack

| Tool | Usage |
|------|-------|
| **Databricks** | Cloud lakehouse platform for data + BI |
| **SQL** | Data querying, aggregation, custom table creation |
| **Python / R** | Notebook-based analysis |
| **Databricks SQL Warehouse** | Serverless compute for dashboard queries |
| **AI Genie** | Natural language Q&A over emission data |
| **Google Drive (Data Ingestion)** | Source data pipeline via folder connection |
| **Unity Catalog** | Data governance — new catalog + default schema |

---

## 🔄 Project Workflow

### 1. Data Ingestion
Connected a Google Drive folder to Databricks using the **Data Ingestion** tool, automating the pipeline from raw EPA CSV files into a managed Delta table.

### 2. Catalog & Table Setup
Created a new **Unity Catalog** and registered the emission dataset as a table in the `default` schema, enabling governed, queryable access across the workspace.

### 3. SQL Query Development
Wrote custom SQL queries using aggregate functions to generate derived tables powering each visualization. Example aggregations include:
- Total emissions grouped by state and county
- Per-capita emissions (emissions / population)
- State-level percentage contribution to national total

### 4. Dashboard Creation
Built an interactive **Databricks SQL Dashboard** with:
- Global filters (filter all charts simultaneously by state/region)
- Map, scatter, donut, and bar chart visualizations
- Custom data tables via SQL-defined views

### 5. AI Genie Integration
Used **AI Genie** to enable natural language querying of the emission dataset — configured with custom instructions so business stakeholders can ask questions like *"Which county has the highest per-capita emissions?"* directly from the dashboard or workspace.

---

## 📌 Key Findings

- The **top 10 states** (TX, FL, OH, IL, GA, MO, CA, TN, PA, NC) account for **51% of total US emissions**
- **Maricopa County, AZ** (9.81M mTon CO₂e) and **Harris County, TX** (9.68M) are the two highest-emitting counties
- Emission per person varies widely — several counties show high total emissions but low per-capita rates, indicating industrial (not population-driven) sources
- **Los Angeles County, CA** ranks 6th in total emissions despite being the most populous county, suggesting relatively better per-capita efficiency

---

## 💡 Databricks Skills Demonstrated

- Navigating the Databricks UI: Catalog, SQL Editor, Dashboards, Genie, Notebooks, Compute
- Importing and querying structured data with SQL
- Writing aggregate SQL (`GROUP BY`, `SUM`, `COUNT`, window functions) to create analysis-ready views
- Building production-style dashboards with global filters
- Connecting external data sources (Google Drive) via Data Ingestion
- Using AI Genie for natural language data exploration with custom instructions
- Working across SQL, Python, and R in unified notebooks

---

## 📁 Repository Structure

```
├── queries/
│   ├── emissions_by_state.sql
│   ├── emissions_by_county.sql
│   └── emissions_per_capita.sql
├── notebooks/
│   └── emission_analysis.ipynb
├── dashboard/
│   └── emission_dashboard_export.json
└── README.md
```

---

## 🗃️ Data Source

**U.S. Environmental Protection Agency (EPA) — 2023 Emissions Data**  
Collected and published by the EPA, covering facility-level greenhouse gas emissions reported under the Greenhouse Gas Reporting Program (GHGRP).

---

## 👤 Author

Built as part of a hands-on Databricks learning journey — covering the full stack from data ingestion to AI-powered analytics and dashboard delivery.
