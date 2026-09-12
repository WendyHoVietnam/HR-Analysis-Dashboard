# **HR: Workforce Insights/ Analytics**

**Author:** Nhu Quynh

**Tools:** SQL / Power BI

[View Interactive Dashboard HERE!](https://app.powerbi.com/view?r=eyJrIjoiYzNjY2FhMDktNmU2Yy00MmE3LTk0NWYtZDRhZjI4Yjk3MTFmIiwidCI6ImVkOGYxNjczLTM4OTAtNGRiNC1hM2YwLTk3YWQ5NDI3Yzc0ZiIsImMiOjEwfQ%3D%3D&pageName=b60b3c152270a064275d)
# Introduction
I built this project because I want to specialize in HR analytics specifically, not data analytics in general. Coming from an HR-adjacent role myself, I understand the operational reality behind the numbers, and I wanted to prove I could turn that understanding into a real, end-to-end analytics system: from raw employee data to insights a company could actually act on.

# Skills show-case

- **SQL**: Designed relational tables and cleaned/deduplicated raw data via ETL from flat file to structured schema
- **Power BI**: Built a star schema model with DAX measures, drill-through pages, and interactive What-If Parameters
- **Data Troubleshooting**: Diagnosed and fixed real import errors — locale/decimal mismatches, delimiter conflicts, data grain issues
- **Critical Analysis**


## 1. Project Overview

**Human Resources (HR)** is responsible for managing the entire employee lifecycle, from recruitment, onboarding, training, and performance evaluation to employee offboarding.

The report answers structured business questions grouped into 3 main sections that progressively narrow from company-level down to department and individual level. 

**What this report covers:**

1. Company-wide workforce overview
2. Recruitment and Attrition Analysis
3. Performance and Attendance Analysis

## 2. Business Objective

The business wants to build a human resources analytics system to track performance, assess resignation risk, and optimize working processes. Recently, the company has recorded:

- Employee performance fluctuating significantly across departments.
- Rising resignation rate, especially among the group with over 2 years of tenure.
- Timekeeping data showing frequent late arrivals and overtime in certain teams.
- Extended recruitment time, affecting operational capacity.

## 3. Target Audience

- **Leadership**: Gain a high-level view of workforce size, stability, and department level outliers to guide strategic decisions.
- **HR Director**: Understand where turnover and hiring inefficiencies are concentrated to prioritize retention and recruitment efforts.
- **Department Heads**: Track attendance, performance, and risk signals within their teams to take timely, targeted action.

## 4. Data & Model

The analysis is built on 1.500 employee records, 20.000 attendance logs, 20.000 performance reviews, and 8 departments across 5 job levels during the period of 2018-2025. Source data was loaded from Excel files into SQL and Power BI, then modeled using a star schema

**Dataset include:**

Employees information table

Attendance table

Department table

Performance table

**Data Model**



## 5. Dashboard Structure

### 5.1 Workforce Overview Dashboard

![Workforce Overview](/Screenshot/Overview.png)

**In general**, the company has 1,500 total employees on record, of which 1,408 remain active and 92 have resigned. The organization added 151 new hires, indicating continued hiring activity to replace the resignation levels.

**Headcount Trend:** Headcount has fluctuated significantly, starting at 223 in 2018, dropping sharply to a low of 172 in 2019, This is a great point to look at why as company **might be layoff employee during the Covid-19 Pandemic.** The headcount then not change a lot in the amount approximately 180 employee

**Department Distribution:** IT (216) and HR (209) are the two largest departments, followed by Sales (194), Customer Service (190), Supply Chain (180), and Finance (177). The spread across departments is fairly even, no single department dominates headcount, which suggests **balanced organizational structure** rather than being top-heavy in one function.

**Position/Level Distribution:** Manager is the most common level (328), followed by Senior (312), Leader (302), Staff (286), and Supervisor (272). 

**Tenure** looks uniform across departments**.** Every department shows an average tenure clustered right around 5 years, with little visible variation.

**Gender Distribution:** The workforce is almost perfectly balanced, 751 Female (50.07%) vs. 749 Male (49.93%). **This is a positive, well-balanced signal with no notable gender skew at the company-wide level.**

---

### 5.2 Attendance Analysis

![Attendance Analysis](/Screenshot/Attendance.png)

**Overall** attendance looks healthy at a glance, but the Late Arrival Rate tells a different story**.** Absent Rate is low (3%) and Attendance Rate is high (97%), which on the surface looks strong. However, **There are 60% of employee late for 15 minutes** which meaning the majority of recorded check-ins involve some lateness.

**Late Arrival Rate** over time is volatile, not steadily worsening**.** The Year trend shows a dip around 2020–2021 (~58%) followed by a rise back to ~61% by 2023, then a slight decline again.

**Lateness** is fairly consistent across departments, not concentrated in one. Late Arrival Rate by Department ranges narrowly from 59% (HR) to 62% (Finance) a spread of only ~3.4 percentage points. This confirms lateness is genuinely spread across departments rather than being one team's problem

**Thursday is the clear worst day for lateness.** The Weekday chart shows a sharp peak on Thursday (~61%), with Tuesday as the best day (~60%). 

**Average overtime hours** **by department** show a tight, compressed range across the period, roughly 1.83 to 2.15 hours,  visualized using a color gradient (white = lowest, pink = highest). This narrow spread indicates that **overtime is not concentrated in or dominated by any single department**; no department consistently stands out as a persistent outlier. Instead, the matrix review overtime spikes are likely tied to **temporary, year-specific factors** (e.g., seasonal workload, project deadlines, short-term staffing gaps) rather than a structural or department-wide overtime problem.

---

### 5.3 Attrition & Recruitment Analysis

![Attrition & Recruitment](/Screenshot/Recruitment%20&%20Attrition.png)

**Overall attrition rate (2.27%) looks low, but hides a strong tenure-based concentration.** While the headline attrition rate is modest, the tenure breakdown reveals resignations are concentrated among longer-tenured employees (2-5 years: 55.79%, +5 years: 44.21%) 

**Department attrition** is led by HR & Marketing (3.25% and 2.18%), with IT the lowest (1,39%). This is a different ranking than the earlier raw-count resignation chart (which had IT/HR highest)

**Tenure concentration remains the standout finding.** 55.79% of resignations come from the 2-5 year group, with the remaining 44.21% from +5 years. **Resignations shown come from employees with 2+ years of tenure**. 

**Younger employees (under 25) show the highest attrition rate** (3.85%), declining steadily with age the 36-45 group is far more stable (1,90%). This suggests early-career retention is a bigger risk than late-career retention.

**Recruitment Time and Hired Source are both fairly flat.** Recruitment time ranges narrowly (49-52 days) across all sources, and hiring source volume (243-264) is evenly distributed across Internal, Referral, Campus, Agency, JobStreet, and LinkedIn no single channel dominates or drags down hiring speed.

**Hire time:** Two low points stand out around September-October (119, 119) 

---

### 5.4 Performance Analysis

![Performance](/Screenshot/Performance.png)

**Average Performance Score: 72** suggests generally acceptable performance but with real room for improvement.

**High Performance:** Only about 1 in 15 reviews qualifies as high-performing (Excellent)  this number alone signals that "exceptional performance" is rare in this organization, which has implications for succession planning and internal promotion pipelines.

**Low Performance:** Nearly a third of all reviews fall into the Poor category. This is the most concerning number on the page. It's 4.5x larger than the High Performer group, and represents a substantial share of the workforce.

**Performance Distribution** Average (41.52%) is the largest slice, followed by Poor (30.28%), Good (21.43%), and Excellent (6.78%). This chart sets the frame for the whole page: performance is concentrated in the lower half of the scale (Average + Poor = 71.8% combined), while the upper half (Good + Excellent = 28.2%) is comparatively small.

**Performance By Position**: Within each Performance Rating bucket, how the 5 position levels (Leader, Manager, Senior, Staff, Supervisor) are represented. This show that **underperformance is not a "junior staff problem," it cuts across seniority levels**, which has different management implications than if it were concentrated at one level.

**Department Rating Table**:

- **Operations is a clear outlier**: only 24 Excellent ratings (vs. 169-225 everywhere else) and the highest Poor count (1,028) of any department, despite not having the most total reviews (2,370, actually mid-pack). This means Operations' rate of poor performance is unusually high, not just its raw count.
- **IT has the most total reviews (2,841)** and a relatively strong Excellent count (225, the highest), suggesting IT may have both scale and quality.
- **Marketing has the fewest total reviews (2,135)** and a middling profile across all categories, no particular strength or weakness stands out.

**Performance Score and Training Hour Scores** across all 4 training buckets are nearly identical: 72, 72, 72, 71. This is a clear, confirmed finding **training hours show no meaningful relationship with performance score**. 

---

### 5.5 Employee Details

![Employee](/Screenshot/Employees.png)

This page is built for **individual-level decisions,** a manager preparing for a 1:1, an HR Director investigating a specific resignation, or someone double-checking whether a name on the Risk List deserves urgent attention or is a borderline case. It's less useful for company-wide strategy but most valuable in the moment right after a broader chart raises a question about one particular person.

## 6. Recommendation

### **Attendance**

Review lateness by department, frequency, and average minutes late, then communicate a clear attendance policy and expected start time. HR can launch a **30-day attendance improvement program**, with managers reminding employees of expectations and HR monitoring the results.

Use a fair progressive approach such as **coaching → verbal/written warning → final warning → further disciplinary action**, while ensuring the process follows your company policy and applicable labor law

Since Thursday showed a consistent lateness peak, this is worth a root-cause conversation with managers: is there a recurring Thursday event (early meeting, different shift pattern, post-Wednesday fatigue)? If it's structural (e.g., a scheduling issue), fixing the schedule is nesccesary

### Attrition

HR should introduce a **2–5 year retention program** with career-path discussions, promotion opportunities, skills training, mentoring, and a stay interview around the 2-year mark. Review salary/benefits and external market competitiveness for this group as well, because employees at this stage may leave when they feel they have gained enough experience but see limited growth internally.

For **HR & Marketing team**, conduct focused exit interviews and manager/team-level analysis to identify why attrition is 5–6x higher than IT. Possible solutions include workload review, shift/scheduling improvements, manager training, recognition programs, and clearer career progression.

### Performance

For employees with persistent poor performance, use individual Performance Improvement Plans (PIPs) with clear targets, timelines, coaching, and consequences.

**Redesign the training approach rather than simply increasing training hours**. Since 10–30+ hours of training produces almost the same average performance score, identify the specific skills causing poor results and replace generic training with **role-specific, practical coaching and on-the-job support**, especially in Operations
