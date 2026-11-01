# Green Labs HR Analytics Dashboard

An end-to-end Power BI project that helps the HR team at **Green Labs**, a technology company, monitor key employee metrics and understand what drives employee attrition.

## Table of Contents

- [Business Problem](#business-problem)
- [Key Metrics](#key-metrics)
- [Tools and Skills](#tools-and-skills)
- [Data Model](#data-model)
- [DAX Measures](#dax-measures)
- [Dashboard Pages](#dashboard-pages)
- [Business Recommendations](#business-recommendations)
- [Project Approach](#project-approach)
- [Repository Structure](#repository-structure)
- [Limitations and Next Steps](#limitations-and-next-steps)
- [Contact](#contact)

## Business Problem

The Green Labs HR team needed a single, reliable view of the workforce.

- **Primary goal:** monitor key employee metrics (headcount, demographics, performance and satisfaction).
- **Secondary goal:** understand which factors influence employee attrition so HR can act on them.

## Key Metrics

| Metric | Value |
|---|---|
| Total employees | 1,470 |
| Active employees | 1,233 |
| Inactive employees | 237 |
| Attrition rate | 16.1% |
| Largest department (active) | Technology: 828 (67.15%) |
| Sales (active) | 354 (28.71%) |
| Employee age range | 18 to 51 |

## Tools and Skills

- **Power BI Desktop:** report design, navigation, branding
- **DAX:** measures and date-aware calculations
- **Power Query:** data cleaning and transformation
- **Data modelling:** Kimball dimensional modelling, snowflake schema
- **Data storytelling:** KPI design, drill-down, business recommendations

## Data Model

The model follows the **Kimball** approach, separating facts (measurable events) from dimensions (context: who, what, when, where, why) in a **snowflake schema**.

**Fact table**

- `FactPerformanceRating`: yearly performance reviews, 11 columns, multiple rows per employee. Central table of the model.

**Dimension tables**

| Table | Purpose |
|---|---|
| `DimEmployee` | Employee attributes (age, age bins, attrition, business travel, department, distance from home, education and more) |
| `DimEducationLevel` | Education level lookup, snowflaked off `DimEmployee` |
| `DimDate` | Custom-built date table (year, quarter, month, day) |
| `DimRatingLevel` | Rating labels, 1 (Unacceptable) to 5 (Above and Beyond) |
| `DimSatisfiedLevel` | Satisfaction labels, 1 (Very Dissatisfied) to 5 (Very Satisfied) |

All DAX measures live in a dedicated `_Measures` table to keep the field list organised.

## DAX Measures

| Group | Measures |
|---|---|
| Headcount | `TotalEmployees`, `ActiveEmployees`, `InactiveEmployees` |
| Date-aware headcount | `TotalEmployeesDate`, `InactiveEmployeesDate` |
| Attrition | `% Attrition Rate`, `% Attrition Rate Date` |
| Compensation | `AverageSalary` |
| Performance and satisfaction | `JobSatisfaction`, `EnvironmentSatisfaction`, `RelationshipSatisfaction`, `WorkLifeBalance`, `ManagerRating`, `SelfRating` |
| Review schedule | `LastReviewDate`, `NextReviewDate` |

## Dashboard Pages

### 1. Overview
KPI cards for total, active and inactive employees and the attrition rate, hiring trends by year split by attrition status, and active employees by department and job role.

### 2. Demographics
Age distribution, age by gender, marital status, and headcount and average salary by ethnicity, supporting diversity and pay-equity monitoring.

### 3. Performance Tracker
Select an individual employee to see their start date, last and next review dates, and yearly trends (2016 to 2022) for job satisfaction, relationship satisfaction, self rating, work-life balance, manager rating and environment satisfaction.

### 4. Attrition
Attrition rate broken down by department and job role, hire date, business travel frequency, overtime requirement and tenure (years at company).


## Business Recommendations

1. **Target retention at the highest-attrition roles** with role-specific plans (compensation, career path, workload).
2. **Review overtime and travel policies** if they show elevated attrition: caps, time in lieu, travel rotation.
3. **Strengthen early tenure** with structured onboarding, 90-day check-ins and mentoring.
4. **Use the Performance Tracker as an early warning system** by flagging falling satisfaction or manager rating trends.
5. **Close self-rating and manager-rating gaps** through review calibration and manager training.
6. **Run a pay-equity review** comparing like-for-like roles and tenures.
7. **Review hiring cohorts** with weaker retention to learn what differed.
8. **Invest in development** and test whether training participation relates to retention.


## Contact

**Muneeza Syed**
Data Analyst | [Linkedin.com/](https://www.linkedin.com/in/muneeza-syed-mia)

- Portfolio: [your portfolio link]
- LinkedIn: [your LinkedIn link]
- Email: [your email]
