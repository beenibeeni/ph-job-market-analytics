# Raw dataset — data dictionary

**Synthetic** data for the Philippine data/analytics job market, **Jan–Jun 2026**.
Intended as a *raw* input: clean, process, model, and build a Power BI dashboard
from it. Company names are fictional Filipino startup-style names (e.g. "Kislap
Labs"). The recruitment data is a synthetic hiring funnel — there is no real
applicant PII.

## raw_job_postings.csv (one row per posting)
| column | notes |
|---|---|
| job_id | posting id (e.g. JP0001); links to applications. **Has duplicate rows to remove.** |
| job_title | role + seniority; inconsistent casing, stray "(Remote)"/whitespace |
| company | employer (fictional Filipino startup names); a few blanks |
| location | "City, Region" free text; some blanks |
| work_setup | Remote/Hybrid/Onsite — inconsistent spellings (On-site, WFH, trailing spaces) |
| employment_type | Full-time/Permanent/Contract — inconsistent casing/spacing |
| salary | **free text**, monthly PHP ranges in mixed formats; some blank or "Negotiable" |
| posted_date | **mixed date formats** (ISO, US, "Jan 15, 2026", "15-Jan-26") |
| job_description | free text; **skills are embedded here** (extract them) |

## raw_applications.csv (one row per application)
| column | notes |
|---|---|
| application_id | application id (e.g. APP00001) |
| job_id | foreign key to raw_job_postings.job_id |
| applicant_name | full name (synthetic) |
| gender | inconsistent: Male/Female/M/F/male/female/Non-binary/Prefer not to say |
| age | some blanks |
| education | inconsistent: Bachelor's/Bachelor/BS/B.S./… |
| years_experience | integer |
| city | applicant city; some blanks |
| date_applied | mixed date formats; on/after the posting date |
| interview_score | 0–100; some blanks |
| status | furthest stage: Applied/Screened/Interviewed/Offered/Hired/Rejected |

## Suggested deliverables for the Power BI dashboard
- **Market:** postings by role, work setup, top employers, postings over time
- **Skills:** in-demand skills (parse from job_description), skill co-occurrence
- **Salary:** parse `salary` → numeric monthly ₱ → median by role/skill
- **Recruitment funnel:** Applied → Screened → Interviewed → Offered → Hired
- **Hiring fairness:** hire rate by gender / age band / education (note: outcomes
  were generated independent of demographics, so expect near-parity)
