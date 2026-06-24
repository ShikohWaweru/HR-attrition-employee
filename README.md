# HR Employee Attrition Analysis
### Excel · Pivot Tables · COUNTIFS · Dashboard · Slicers

> **Can the organisation predict who will leave — and act before they do?**  
> This project analyses a 1,470-employee HR dataset to identify the structural drivers of attrition and surface targeted retention recommendations for people operations and senior leadership.

---

## Dashboard Preview

<img width="1852" height="846" alt="Project-Guide-HR-Employee-Attrition Dashboard Screenshot" src="https://github.com/user-attachments/assets/075f3b1c-a1f1-4c07-a761-c8d4809f639f" />

---

## Business Problem

Employee attrition is expensive. Replacing a single employee can cost **50–200% of their annual salary** when recruitment, onboarding, and lost productivity are factored in. Yet most organisations only act after someone resigns.

This analysis answers four questions that support proactive retention decisions:

- Which departments and job roles have the highest attrition rates?
- What employee demographics are associated with higher risk of leaving?
- How does job satisfaction drive attrition — and by how much?
- Are performance ratings a useful signal, or is the problem systemic?

---

## Dataset

| Attribute | Detail |
|---|---|
| Source | IBM HR Analytics Employee Attrition dataset |
| Records | 1,470 employees |
| Features | 35 variables — demographics, compensation, satisfaction, tenure, performance |
| Attrition labels | Binary (Yes / No) |
| Tool | Microsoft Excel |

---

## Methodology

This project followed the **CRISP-DM framework**:

1. **Business understanding** — defined attrition rate as the primary KPI; identified secondary metrics (satisfaction, income band, tenure group)
2. **Data understanding** — profiled 35 variables; flagged distribution issues (e.g. performance ratings concentrated at levels 3–4 only)
3. **Data preparation** — standardised department labels, encoded attrition as binary (1/0), created calculated fields for Age Group, Income Band, Years Group, and Satisfaction Band
4. **Modelling / analysis** — built pivot tables segmented by department, job role, demographics, satisfaction, and tenure; calculated attrition rates using `COUNTIFS` outside pivot tables to avoid calculated field limitations
5. **Evaluation** — cross-checked all rates against raw counts; identified highest-impact segments by both rate and volume
6. **Dashboard** — consolidated findings into a single slicer-enabled Excel dashboard with dynamic filtering by Department, Job Role, Age Group, and Year

---

## Key Findings

### Overall position

| Metric | Value |
|---|---|
| Total employees | 1,470 |
| Employees who left | 237 |
| **Overall attrition rate** | **16.1%** |
| Industry benchmark (professional services) | 10–13% |
| Average monthly income | $6,503 |

The organisation is losing **1 in 6 employees** — above benchmark and concentrated in specific, addressable segments.

---

### 1. Attrition by department

| Department | Employees | Attrited | Attrition Rate |
|---|---|---|---|
| Human Resources | 64 | 13 | 20.3% |
| Sales | 446 | 92 | **20.6%** |
| Research & Development | 960 | 132 | 13.8% |

HR and Sales both exceed 20% — well above the 16.1% average. Within Sales, **Sales Representatives alone have a 39.8% attrition rate**, the highest of any job role in the dataset.

---

### 2. Demographic risk factors

| Demographic | Highest-risk segment | Attrition rate | Lowest-risk segment | Attrition rate |
|---|---|---|---|---|
| Age | 18–22 | 47.4% | 43–47 | 10.4% |
| Tenure | 0–1 years | 34.9% | 11–15 years | 6.5% |
| Monthly income | Below $2,500 | 34.1% | $15,000+ | 3.8% |
| Marital status | Single | 25.5% | Divorced | 10.1% |
| Education field | Human Resources | 25.9% | Medical | 13.6% |

**Income is the strongest single predictor of attrition in this dataset.** The rate falls consistently and dramatically as compensation rises — from 34.1% at the lowest band to 3.8% at the highest. Early tenure and young age compound this: nearly half of employees aged 18–22 leave, most within their first year.

---

### 3. Satisfaction & travel

| Satisfaction band | Attrition rate |
|---|---|
| Low | 22.8% |
| Medium-Low | 16.4% |
| Medium-High | 16.5% |
| High | 11.3% |

Employees with **low job satisfaction leave at twice the rate** of highly satisfied peers (22.8% vs 11.3%). The average satisfaction score across the dataset is 2.73 / 4 — middling company-wide, not just at the tail.

Business travel compounds this: frequent travellers leave at **24.8%** vs 8.0% for non-travellers — a 3× gap that is often overlooked in retention strategies.

---

### 4. Performance & attrition

| Performance rating | Attrition rate |
|---|---|
| 3 – Excellent | 16.1% |
| 4 – Outstanding | 16.4% |

**Performance ratings do not predict attrition.** The rates across both bands are statistically indistinguishable. The organisation is losing high and average performers at the same rate — confirming that attrition is driven by structural and environmental factors, not individual underperformance.

---

## Recommendations

| Priority | Action | Owner | Signal |
|---|---|---|---|
| 🔴 1 | Review entry-level compensation — employees below $2,500/month leave at 3× the average | HR & Finance | Income band attrition rate: 34.1% |
| 🔴 2 | Structured 90-day onboarding with manager check-ins at 30/60/90 days | HR Operations | Year-one attrition: 34.9% |
| 🟡 3 | Workload and overtime audit in HR and Sales | Department heads | Dept attrition >20%; travel attrition 24.8% |
| 🟡 4 | Career pathing programme for early-career and single employees | L&D | Age 18–22: 47.4%; Single: 25.5% |
| 🟢 5 | Cohort exit analysis for Technical Degree and Marketing graduates | Talent Acquisition | Edu field attrition: 23.7% / 22.5% |

---

## Excel workbook structure

| Sheet | Contents |
|---|---|
| `Data` | Raw dataset — 1,470 rows, 35 columns, with calculated fields added |
| `Analysis` | Descriptive statistics — mean, median, standard deviation by key variable |
| `Pivot Tables` | Attrition breakdowns by department, role, age, income, satisfaction, tenure, marital status, education, travel |
| `Pivot Charts` | Chart objects linked to pivot tables |
| `Dashboard` | Single-view slicer-enabled dashboard with dynamic filtering |

---

## Technical notes

- Attrition rates calculated using `COUNTIFS` on the raw data sheet rather than pivot table calculated fields — this avoids the Grand Total distortion that occurs when calculated fields divide aggregated sums
- Age Group, Income Band, Satisfaction Band, and Years Group created as helper columns using nested `IF` statements
- All pivot tables reference the same named data range for consistency

---

## Skills demonstrated

`Excel` `Pivot Tables` `COUNTIFS` `Dashboard Design` `Slicers` `Data Cleaning` `Segmentation Analysis` `CRISP-DM` `Workforce Analytics` `Data Storytelling`

---
