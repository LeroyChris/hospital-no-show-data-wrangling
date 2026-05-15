# Comprehensive Data Wrangling Pipeline: Hospital Appointment No-Show Analytics

A production-grade, end-to-end data wrangling and exploratory analytics pipeline executed on a healthcare administration dataset. This repository demonstrates granular data hygiene operations, data type sanitization, feature alignment, and modular script engineering tailored to isolate behavioral anomalies behind medical appointment cancellations.

## 📊 Dataset Specifications & Domain Context

- **Dataset Source:** Medical Appointment No-Shows (Kaggle).
- **Core Objective:** Clean and preprocess unstructured administrative patient logs to uncover why **20% of patients skip their scheduled appointments**, directly impacting operational efficiency and healthcare hospital revenue.
- **Data Scale:** Encompasses **110,527 unique appointment records** mapped across **14 baseline features** including demographics, scheduling lead times, specific medical comorbidities, and final attendance target labels.

---

## 🛠️ Data Wrangling Lifecycle & Engineering Pipeline

The programmatic workflow is structured sequentially to transition raw, unhygienic administrative data into analytical assets:

[Raw CSV Ingestion] ──> Data Characterization & Integrity Scanning
│
▼
[Data Cleansing Phase] ──> Handles negative age variables & logical outliers
│
▼
[Type Sanitization] ──> Casts timestamps to Datetime objects & normalizes IDs
│
▼
[Feature Engineering] ──> Calculates scheduling lead-time deltas & daily mappings
│
▼
[Exploratory Analytics]──> Modular descriptive plots using Matplotlib & Seaborn


---

## 🧩 Advanced Programming & Pipeline Implementation

### 1. Robust Data Hygiene & Integrity Fixes
- **Anomaly Interception:** Isolated and purged logical errors in data rows (such as negative age inputs) that distort statistical distribution models.
- **Value Constraints:** Rectified structural inconsistencies and verified binary flags across health conditions (Scholarship, Hipertension, Diabetes, Alcoholism, Handcap, SMS_received).

### 2. High-Fidelity Type Conversions
- Formatted `PatientId` and `AppointmentID` tracking variables to remove technical numerical float mutations.
- Transformed unstructured object strings (`ScheduledDay`, `AppointmentDay`) into strict ISO standard Datetime vectors to support chronological timeline calculations.

### 3. Modular Feature Construction (`def` Ecosystem)
- Avoided long linear scripts by wrapping custom cleaning states into reusable, testable Python functions (`def`).
- Synthesized critical delta features, computing the precise waiting window between the registration date and the actual appointment date to serve as a primary behavioral indicator.

### 4. Descriptive Visual Insights (Matplotlib & Seaborn)
- Conducted univariate and multivariate analysis to identify correlation factors between demographic groups, communication touchpoints (SMS reminders), and cancellation metrics.
- Extracted explicit quantitative indicators to assist management in designing better hospital booking frameworks.

---

## 📁 Repository Structure

```text
hospital-no-show-data-wrangling/
├── data/
│   └── noshowappointments.csv   <- Core raw healthcare CSV dataset
├── Pipeline.ipynb              <- Fully documented Jupyter Notebook (English Version)
└── README.md                   <- Comprehensive pipeline architecture & data breakdown
```

---

## ⚙️ Quick Start & Reproducibility Guide

To execute this pipeline locally and reproduce the data transformation steps, follow the guide below:

### Prerequisites
Ensure you have Python 3.8+ installed along with the required analytical libraries:
```bash
pip install pandas matplotlib seaborn
```

### Execution Steps
1. Clone this specific repository to your local computer path:
   ```bash
   git clone https://github.com
   cd hospital-no-show-data-wrangling
   ```
2. Open your preferred IDE (VS Code or Jupyter Notebooks) and boot up the main pipeline file:
   ```bash
   jupyter notebook Pipeline.ipynb
   ```
3. Run all cells sequentially (`Run All`) to trace the transformation metrics from data loading up to data visualization outputs.