# SaaS Support Ticket Analytics Dashboard

# SaaS Support Ticket Analytics Dashboard

This project analyzes SaaS customer support tickets using Python, DuckDB SQL, Power BI, and a light machine learning model.  
It demonstrates an end-to-end analytics workflow starting from raw data → cleaning → EDA → dashboard → ML baseline.

---

## 📁 Project Structure
SaaS Ticket Analytics Dashboard/
│
├── cleaned/
│ tickets_master_clean.csv
│ agents_clean.csv
│ customers_clean.csv
│
├── notebooks/
│ 01_data_understanding.ipynb
│ 02_data_cleaning.ipynb
│ 03_sql_eda.ipynb
│ 04_ml_basics.ipynb
│
├── outputs/
│ plots/
│ sql_monthly_trend.csv
│ sql_sla_monthly.csv
│ sql_top_issue_types.csv
│ sql_tickets_by_hour.csv
│ sql_agent_performance.csv
│
├── powerbi/
│ SaaS_Ticket_Analytics_Dashboard.pbix
│ SaaS_Ticket_Analytics_Dashboard.png
│ SaaS_Ticket_Analytics_Dashboard.pdf
│
└── README.md

---

# 📊 Power BI Dashboard  
![Dashboard](powerbi/SaaS_Ticket_Analytics_Dashboard.png)

The dashboard has:  
- KPI cards  
- Ticket trend chart  
- SLA breach trend  
- Issue-type breakdown  
- Hourly volume pattern  
- Agent performance comparison  
- Slicers (priority, issue type, date)

---

# 🚀 **Stage 1 — Data Understanding**
**Goal:** Explore the raw data and confirm structure.

**What was done:**
- Loaded raw CSV files (tickets, agents, customers)  
- Checked column types, missing values, duplicates  
- Reviewed ticket timestamps & categorical fields  
- Identified required data cleaning steps

---

# 🧹 **Stage 2 — Data Cleaning (Python)**
**Goal:** Prepare high-quality datasets for analysis.

**What was done:**
- Removed duplicates and standardized column names  
- Parsed timestamps (`created_at`, `first_response_at`, `resolved_at`)  
- Engineered features:
  - `created_hour`
  - `year_month`
  - `first_response_mins`
  - `resolution_time_hours`
  - `sla_breached`
- Cleaned categorical fields (priority, issue type, channel)  
- Exported final cleaned datasets into `/cleaned`

---

# 📈 **Stage 3 — SQL EDA (DuckDB) + Python Visuals**
**Goal:** Analyze patterns and trends using SQL.

**Key analyses performed:**
- **Monthly ticket trend**  
- **SLA breach % trend**  
- **Top 10 issue types**  
- **Tickets by hour of day**  
- **Agent performance summary**

All SQL outputs saved in `/outputs` and plotted in Python.

---

# 📊 **Stage 4 — Power BI Dashboard**
**Goal:** Build an interactive dashboard for business users.

**Dashboard highlights:**
- KPI Cards (Total Tickets, Avg Response, Avg Resolution, SLA %, CSAT)  
- Monthly trend line chart  
- Issue type bar chart  
- Hourly distribution area chart  
- Agent performance table  
- Slicers for dynamic filtering  
- Clean, professional layout and theme

PBIX, PDF, and PNG files included.

---

# 🤖 **Stage 5 — Machine Learning (Light Model)**
**Goal:** Add a simple predictive model to enhance insights.

**Model:** Logistic Regression  
**Target:** Predict **CSAT Good (>=4)** vs **Bad (<4)**  

**Features used:**
- priority  
- issue_type  
- created_hour  
- first_response_mins  
- resolution_time_hours  

**Results:**
- Baseline accuracy: **~75–80%**  
- Good separation between satisfied vs unsatisfied customers  
- Confusion matrix + classification report included  
- ML kept intentionally simple for interpretability

---

# 🧠 **Key Insights from the Project**
- Ticket volume peaks during **10 AM – 2 PM**  
- Top issue types: **API issues, Login problems, Billing**  
- SLA performance varies across months  
- Faster resolution strongly correlates with higher CSAT  
- Clear differences in agent performance (CSAT + resolution speed)

---

# 🔧 **Tools & Technologies**
- Python (pandas, matplotlib, sklearn)  
- DuckDB SQL  
- Power BI  
- Jupyter/VS Code  
- CSV datasets

---

# 📦 **How to Reproduce**
1. Clone the project  
2. Run notebooks in order (`01 → 04`)  
3. Load the PBIX file into Power BI Desktop  
4. Explore dashboard + outputs  

---

# ✉ Contact
For walkthrough or collaboration, feel free to connect.
