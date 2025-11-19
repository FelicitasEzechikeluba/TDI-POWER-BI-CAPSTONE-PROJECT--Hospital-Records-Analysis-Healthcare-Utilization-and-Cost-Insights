# Hospital Records Analysis: Healthcare Utilization and Cost Insights

A comprehensive analysis of hospital encounter data to improve operational efficiency, financial performance, and healthcare policy support.

## Overview

This project explores synthetic patient data (~1,000 records) from Massachusetts General Hospital spanning 2011-2022. The analysis examines how patient demographics, insurance coverage, medical encounters, and procedures influence healthcare utilization and hospital performance.

**Key Focus**: Balancing quality care with financial sustainability while identifying opportunities to improve efficiency, patient equity, and access.

## Problem Statement

How can hospitals improve efficiency and expand access to healthcare while maintaining financial sustainability and supporting policy goals?

## Objectives

- Analyze encounter data to identify trends in utilization, costs, and claim coverage
- Measure key hospital metrics (mortality rate, readmission rate, average length of stay)
- Compare base costs and total claim costs across encounter classes and payers
- Detect inefficiencies, including encounters with zero coverage or unusually long durations
- Provide dashboards summarizing KPIs for policymakers, hospital directors, and investors

## Dataset

**Source**: Maven Analytics Playground

**Structure**: 
- **Encounters** (fact table) - daily transaction records
- **Patients** - demographics and insurance information
- **Organizations** - hospital details
- **Payers** - insurance provider information
- **Procedures** - medical procedure records

**Period**: 2011-2022

## Key Performance Indicators

### Operational Metrics
- **Total Patients**: Unique individuals served
- **Total Encounters**: All recorded visits/admissions
- **Average Visits per Patient**: Encounters per unique patient
- **Average Length of Stay**: Mean time patients spend in care
- **Readmission Rate**: % of patients returning within 30 days
- **Mortality Rate**: % of patients who died during encounters

### Financial Metrics
- **Total Encounter Cost**: Total hospital spending on all encounters
- **Average Cost per Encounter**: Mean cost per patient visit
- **Average Operating Margin**: % of profit retained after operating costs
- **Bad Debt Amount**: Unpaid costs from insurers
- **% Cost Covered**: Portion of costs paid by insurers
- **Total Out-of-Pocket Share**: Sum of costs patients personally paid

## Key Findings

### Healthcare Quality Issues
- High readmission and mortality rates in ambulatory and inpatient classes
- Many deaths linked to unclear or misclassified encounter reasons
- 3 a.m. encounter spikes suggest high overnight demand for semi-urgent cases

### Operational Efficiency
- Inpatient, ambulatory, and outpatient classes show prolonged stays (37, 9, 6 hours avg)
- Ambulatory care has highest readmissions (8,500 cases)
- Peak months: February and March; Peak days: Friday and Saturday

### Cost Management
- Inpatient, urgent care, and emergency classes drive highest treatment costs
- Urgent care (-33.90%) and emergency (-25.50%) generate negative profit margins
- Wellness (46.11%) and inpatient (34.09%) maintain positive margins

### Coverage Gaps & Inequities
- Only 36% of patients have insurance coverage
- Natives ($6.6k), Blacks ($4.1k), and Hawaiians ($3.6k) pay higher out-of-pocket costs
- Insurance coverage concentrated in lower-risk classes (wellness: 53.74%)
- High-risk groups (urgent care: 13.10%) receive minimal coverage support

## Tools & Methodology

**Primary Tool**: Power BI

**Approach**:
1. **Data Cleaning**: Addressed nulls, duplicates, and billing integrity issues in Power Query
2. **Data Modeling**: Built star schema with Encounters as fact table
3. **Time Intelligence**: Created date table for trend analysis
4. **DAX Measures**: Developed calculated columns and measures for KPIs
5. **Visualization**: Created two interactive dashboards with drill-throughs and tooltips

## Dashboards

### Dashboard 1: Encounter & Operational Overview
- Patient volume and encounter trends
- Length of stay analysis
- Readmission patterns
- Mortality tracking by encounter class

### Dashboard 2: Cost & Insurance Insights
- Revenue and cost analysis
- Insurance coverage distribution
- Out-of-pocket expense patterns
- Payer performance comparison

## Key Recommendations

1. **Improve Care Quality**: Investigate high readmission rates and unclear death classifications in ambulatory care
2. **Enhance Efficiency**: Focus on reducing length of stay in inpatient, urgent, and emergency encounters
3. **Close Coverage Gaps**: Launch enrollment drives and financial counseling to increase the 36% insured rate
4. **Address Inequities**: Review billing structures to reduce disproportionate OOP costs for vulnerable populations
5. **Negotiate Fair Coverage**: Advocate for balanced payer coverage across all encounter classes
6. **Leverage Policy**: Use ACA and MHPAEA to challenge under-coverage in mental health and substance use services

## Files Structure

```
├── data/
│   ├── encounters.csv
│   ├── patients.csv
│   ├── organizations.csv
│   ├── payers.csv
│   └── procedures.csv
├── sql/
│   ├── create_hospital_db.sql
│   └── hospital_analytics_questions.sql
├── dashboards/
│   └── hospital_performance_report.pbix
├── documentation/
│   └── TDI_Power_BI_Project_Documentation.docx
└── README.md
```

## Important Notes

*This analysis uses proxy metrics (e.g., Base Encounter Cost for operating cost, Payer Coverage for revenue). These estimates offer directional insights but don't reflect full financial accuracy. Results are indicative, not definitive, and unsuitable for audited or regulatory reporting.*

## Stakeholders

- **Policymakers**: Data for designing and evaluating insurance programs
- **Hospital Directors**: Operational and financial insights for resource management
- **Investors**: Performance metrics for sustainability assessment

## Author

**Felicitas Ezechikeluba**  
Track: Data Analytics  
Cohort: Sapphire  
TDI Power BI Capstone Project

## License

This project uses synthetic data from Maven Analytics for educational purposes.

---

*For detailed analysis, DAX formulas, and methodology, please refer to the documentation folder.*
