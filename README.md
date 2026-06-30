# 🇵🇭 Philippine Data/Analytics Job Market Dashboard
**Personal Portfolio Project · Power BI · 2026**

A data analytics portfolio project exploring the Philippine data and analytics job market from January to June 2026. Built end-to-end: from raw messy CSV data to a fully cleaned dataset, star schema data model, DAX measures, and an interactive Power BI dashboard.

---

## Repository Contents

| File | Description |
|---|---|
| `PowerQuery_Cleaning_Guide.html` | Step-by-step interactive guide for cleaning both datasets in Power Query |
| `raw_job_postings.csv` | Raw dataset — 100 unique job postings across the Philippines |
| `raw_applications.csv` | Raw dataset — 2,660 job applications across all postings |
| `DATA_DICTIONARY.md` | Column definitions and data notes for both datasets |

---

## Project Overview

### The Data
- **100 job postings** from fictional Filipino tech startups (Jan–Jun 2026)
- **2,660 applications** with full hiring funnel data — Applied → Screened → Interviewed → Offered → Hired
- Roles covered: Data Analyst, Data Scientist, Data Engineer, BI Analyst, Analytics Engineer, AI/ML Engineer

### Dashboard Pages *(in progress)*
| Page | What it shows |
|---|---|
| **Market Overview** | Postings by role, work setup (Remote/Hybrid/Onsite), top employers, postings over time |
| **Skills Analysis** | Most in-demand skills, skill frequency by role |
| **Salary Insights** | Median monthly PHP salary by role and seniority |
| **Recruitment Funnel** | Drop-off rates across hiring stages |
| **Hiring Fairness** | Hire rate by gender, age band, and education level |

---

## Tools & Skills Used

- **Power BI Desktop** — data modeling, DAX, dashboard design
- **Power Query (M language)** — data cleaning and transformation
- **Data modeling** — star schema design (fact + dimension tables)
- **DAX** — KPI measures, time intelligence, CALCULATE filters

---

## Data Cleaning Highlights

The raw data had several real-world messiness issues that required careful handling:

- **Mixed date formats** — 4 different formats in the same column (ISO, US, long text, short text) → parsed to uniform Date type
- **Free-text salary** — 4 different formats like `₱115.0K - ₱147.0K /mo`, `PHP 126,000-161,000 monthly`, `Up to ₱37,000/month` → extracted `salary_min`, `salary_max`, and `salary_midpoint` as whole PHP numbers
- **Inconsistent categoricals** — `WFH`, `remote`, `On-site` all meaning the same thing → standardized to 3 values
- **Embedded skills** — skills hidden inside `job_description` free text → extracted into `skills_raw` column
- **Duplicate rows** — 4 duplicate `job_id` rows removed

Full cleaning documentation with click-by-click instructions:
👉 **[Open the Power Query Cleaning Guide](https://beenibeeni.github.io/ph-job-market-analytics/PowerQuery_Cleaning_Guide.html)**

---

## Data Model *(Phase 2 — in progress)*

Star schema with:
- `fact_applications` — one row per application
- `dim_jobs` — one row per job posting
- `dim_skills` — one row per skill
- `bridge_job_skills` — many-to-many link between jobs and skills
- `dim_date` — calendar table for time intelligence

---

## Project Status

| Phase | Status |
|---|---|
| Phase 1 — Data Cleaning (Power Query) | ✅ Complete |
| Phase 2 — Data Modeling (Star Schema) | 🔄 In progress |
| Phase 3 — DAX Measures | ⏳ Upcoming |
| Phase 4 — Dashboard Design | ⏳ Upcoming |

---

## About

Hi, I'm **Jannelle** — a data analyst based in the Philippines. This is my first end-to-end Power BI portfolio project. I'm documenting every phase as I build it, including the reasoning behind each decision.

Connect with me on [LinkedIn](https://www.linkedin.com/in/jnnllcandelaria/) ← *(replace with your actual LinkedIn URL)*

---

*Data is synthetic and generated for learning purposes. Company names are fictional Filipino startup-style names. No real applicant PII is included.*
