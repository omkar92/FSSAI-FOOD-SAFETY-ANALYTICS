# FSSAI Food Safety Analytics | Python + Power BI

An end-to-end **data analytics portfolio project** using synthetic food safety inspection data to demonstrate data validation, exploratory data analysis (EDA), enforcement exception screening, and interactive reporting.

> **Important disclaimer:** All datasets in this repository are synthetic and created for learning and portfolio demonstration. This project is not affiliated with FSSAI and does not represent official FSSAI statistics, real inspections, or actual enforcement performance.

## Project Overview

The project explores simulated food businesses, inspection raids, food samples, violations, and enforcement actions. Python was used to validate and analyze the data and generate audit outputs. Power BI was used to build an interactive, three-page report.

## Tools and Technologies

- **Python** and **Pandas** — data validation, transformation, EDA, and exception screening
- **Jupyter Notebook** — include this if your analysis notebook is part of the repository
- **Power BI** — data modeling, DAX measures, slicers, KPI cards, and report visuals
- **CSV** — datasets and audit outputs

## Repository Structure

Adjust the filenames below to match what you actually upload.

```text
fssai-food-safety-analytics/
├── data/
│   ├── food_businesses.csv
│   ├── food_raids.csv
│   ├── food_samples.csv
│   ├── violations.csv
│   ├── enforcement_actions.csv
│   └── fssai_exception_register_all.csv
├── notebooks/
│   └── fssai_eda.ipynb
├── reports/
│   └── fssai_full_enforcement_audit.csv
├── powerbi/
│   └── FSSAI_Food_Safety_Analytics.pbix
└── README.md
```

Only retain entries for files you have actually uploaded.

## Data Model

- **Food Businesses:** simulated business details and location/category attributes.
- **Food Raids:** simulated inspection dates, reasons, outcomes, and business references.
- **Food Samples:** simulated sample results and food categories.
- **Violations:** simulated violation types and severity.
- **Enforcement Actions:** simulated actions associated with raids.
- **Exception Register:** Python-generated screening output for records selected for review.
- **Full Enforcement Audit:** audit output covering all raid records.

In Power BI, the main model connects businesses to raids and raids to samples, violations, and enforcement actions through their IDs. Treat the exception register as a separate audit output unless its relationship and intended filtering behavior have been verified.

## Python Workflow

### 1. Data quality checks
- Missing values and duplicate rows
- Unique identifier checks
- Date conversion and validation
- Referential integrity across related tables

### 2. Exploratory Data Analysis (EDA)
- Sample compliance by food category
- Non-compliance issue types
- Violation severity and violation types
- Enforcement action distribution and simulated fine totals

### 3. Exception screening
Predefined rules flag records such as:
- Serious violations associated with a “No Further Action” record
- Corrective action required without a recorded follow-up
- Unresolved cases associated with a “No Further Action” record

These are **screening flags, not proof** of misconduct, incorrect decisions, or confirmed errors. Each record requires contextual review before conclusions are drawn.

## Illustrative Findings

The following figures are from the current synthetic dataset and demonstrate the analysis workflow.

| Metric | Result |
|---|---:|
| Food businesses | 500 |
| Raid records | 1,200 |
| Food sample records | 1,795 |
| Violation records | 827 |
| Non-compliant samples | 273 |
| Violations classified as Moderate | 301 |
| Raids flagged by at least one screening rule | 391 |
| High-priority flagged raids | 48 |
| Simulated total fine amount | ₹32,89,500 |

### Sample compliance
- Packaged Snacks: **19.19% non-compliance (33 of 172 samples)**.
- Bakery Products: **18.63% non-compliance (38 samples)**.
- Sweets: **11.00% non-compliance (22 of 200 samples)**.

### Enforcement review flags
The exception screening flagged **391 unique raids** under predefined rules. These flags identify records that may warrant review; they do not establish that an enforcement action was wrong. A “No Further Action” record can be appropriate depending on the case context.

Since the data is synthetic, these are illustrative patterns—not real-world findings or conclusions about FSSAI operations.

## Power BI Report Pages

1. **Enforcement Exceptions** — screening flags, priority distribution, and raid trends.
2. **Raid & Geographic Analysis** — business and geographic distribution and sample-related KPIs.
3. **Raid Outcome Distribution** — inspection reasons, enforcement actions, and raid outcomes.

## Potential Business Questions

- Which food categories show higher simulated sample non-compliance rates?
- Which violation types and severity levels appear most frequently?
- How are recorded enforcement actions distributed?
- Which records meet predefined exception-screening rules and require contextual review?
- How do raid outcomes and inspection reasons vary across locations and time?

## How to Reproduce

1. Clone or download this repository.
2. Install Python and Pandas; install Jupyter Notebook if needed.
3. Open the notebook in `notebooks/` and update file paths to match the repository layout.
4. Run the data validation and analysis cells in order.
5. Open the `.pbix` file in Power BI Desktop, if included.
6. If prompted, update data-source paths to your local CSV files.

## Limitations

- All records and results are synthetic.
- Exception flags depend on predefined rules and may include false positives.
- One raid can have multiple samples, violations, or enforcement-action records, so related-table counts are not always directly comparable.
- This is a portfolio demonstration, not a regulatory audit or official assessment.

## Future Improvements

- Add automated data-quality tests.
- Parameterize exception-screening rules.
- Add unit tests for audit logic.
- Create a Streamlit interface for uploading datasets and reviewing flags.
- Document DAX measures and report interactions.

## Author

**Omkar Warade**  
Data Analytics Portfolio Project
