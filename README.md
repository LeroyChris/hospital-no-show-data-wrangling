# Hospital Appointment No-Show Data Wrangling

This repository contains a single notebook, `Pipeline.ipynb`, that implements a complete data wrangling workflow for the Medical Appointment No-Shows dataset.

It is designed to guide you through the full analysis sequence from raw CSV ingestion to business-focused insights and visualization.

---

## What `Pipeline.ipynb` covers

The notebook is organized into clearly separated sections:

1. **Setup & Imports**
   - Load essential libraries and prepare the notebook environment.

2. **Data Understanding**
   - Load the dataset from `data/noshowappointments.csv`.
   - Verify dataset dimensions, column types, and initial data quality.
   - Identify typos and unusual values in raw columns.

3. **General Cleaning Pipeline**
   - Standardize column names to lowercase and underscore format.
   - Remove fully duplicated rows.
   - Parse string date columns into datetime objects.

4. **Dataset-Specific Cleaning**
   - Correct known typos in column names (`hipertension` → `hypertension`, `handcap` → `handicap`).
   - Remove invalid age values.
   - Convert the `No-show` label into a binary `is_no_show` feature.

5. **Data Manipulation & Feature Engineering**
   - Create `wait_days` representing days between scheduling and appointment.
   - Derive `appointment_day_of_week` to analyze weekday patterns.
   - Group patients by age brackets for demographic analysis.

6. **Business Use Cases & Insight**
   - Evaluate how wait time, SMS reminders, and age group relate to no-show behavior.
   - Produce visual summaries and practical recommendations.

---

## Repository structure

```text
hospital-no-show-data-wrangling/
├── data/
│   └── noshowappointments.csv   <- Raw dataset used by the notebook
├── Pipeline.ipynb              <- Main Jupyter Notebook with analysis workflow
└── README.md                   <- This guide
```

---

## Run the notebook

### Prerequisites
Install Python packages required by the notebook:

```bash
pip install pandas matplotlib seaborn
```

### Start the analysis

1. Open the repository in VS Code or Jupyter Notebook.
2. Open `Pipeline.ipynb`.
3. Run the notebook cells in order, section by section.

> Recommended: use the notebook's `Run All` feature after confirming the setup cell imports successfully.

---

## Notes for readers

- The notebook uses explicit Python functions to keep cleaning steps reusable and easy to follow.
- If you want to adapt the pipeline for a different dataset, start by updating the path in the first data loading cell.
- The final section is focused on business insight, so it is useful for presenting results to stakeholders.