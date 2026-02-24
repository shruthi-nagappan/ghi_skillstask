# 🌍 Global Health Impact (GHI) – HIV Data Analysis (2015)

This project analyzes global HIV treatment data to compute **treatment impact scores** across countries and WHO regions using the **Global Health Impact (GHI)** methodology.

The objective is to **replicate and automate complex Excel-based HIV treatment impact calculations** using Python, ensuring transparency, scalability, and reproducibility.

---

## 📌 Project Objective

The primary goal of this project is to calculate **drug-level and regimen-level HIV treatment impact scores** using:

* Disability-Adjusted Life Years (**DALYs**)
* Treatment coverage
* Patient retention rates
* Drug regimen efficacy
* Drug utilization proportions

The workflow replaces manual spreadsheet calculations with an automated and reproducible data pipeline.

---

## 📊 Dataset

The analysis uses HIV treatment data from **2015**, sourced from a structured Google Sheets workbook:

* **Sheet Name:** `HIV2015`
* **Columns:** 84 health and treatment indicators
* **Scope:** Country-level HIV burden and treatment data

The dataset includes:

* Adult and pediatric HIV burden
* Treatment regimen distributions
* Drug usage proportions
* Retention and efficacy metrics

---

## ⚙️ Project Workflow

### 1️⃣ Data Acquisition

* Loads HIV data directly from Google Sheets.
* Imports structured epidemiological and treatment information.
* Maintains compatibility with original Excel-based GHI models.

---

### 2️⃣ Data Cleaning

Preprocessing steps include:

* Cleaning inconsistent column headers
* Handling missing values (`NaN`)
* Converting formatted numeric strings:

  * Removing commas (`1,234`)
  * Parsing percentages (`85%`)
* Standardizing numeric formats for computation

---

### 3️⃣ Regimen Analysis

The notebook extracts and evaluates **Antiretroviral (ARV) treatment regimens**, including:

#### Adult First-Line Regimens

* TDF + 3TC + EFV
* TDF + FTC + EFV
* Other WHO-recommended combinations

#### Children First-Line Regimens

* ABC + 3TC + LPV/r
* ABC + 3TC + EFV

#### Second-Line Regimens

* LPV/r-based combinations
* ATV/r-based combinations

Each regimen is mapped to:

* Drug efficacy
* Treatment proportion
* Population coverage

---

## 🧩 Core Components

### ✅ Data Processing Utilities

#### `to_float(val, default=0.0)`

Safely converts formatted numeric values into floats.

Handles:

* Percent symbols (`%`)
* Comma-separated numbers
* Missing or invalid values

---

#### `is_numeric(val)`

Validates whether a dataset entry contains usable numeric information.

---

## 📈 Key Variables Analyzed

| Variable        | Description                                    |
| --------------- | ---------------------------------------------- |
| `adult_daly`    | DALYs attributable to adult HIV population     |
| `child_daly`    | DALYs attributable to pediatric HIV population |
| `retention_pct` | Treatment retention rate                       |
| `actual_*`      | Reported drug utilization                      |
| `calc_*`        | Computed treatment impact per drug             |

Drugs analyzed include:

* 3TC
* ABC
* AZT
* ddl
* d4T
* EFV
* FTC
* LPV/r
* NVP
* TDF
* ATV/r

---

## 🧮 Impact Score Calculation

Treatment impact scores are computed by integrating:

```
Impact Score =
DALYs × Treatment Coverage × Retention × Drug Efficacy × Regimen Proportion
```

Outputs include:

* Drug-level impact scores
* Regimen-level contributions
* Country-level treatment impact
* WHO regional summaries

---

## 🛠️ Requirements

Install dependencies before running the notebook:

```bash
pip install pandas numpy requests openpyxl
```

### Dependencies

* Python 3.x
* Pandas
* NumPy
* Requests
* OpenPyXL

---

## ▶️ How to Run

1. Clone the repository:

```bash
git clone https://github.com/your-username/ghi-hiv-impact-analysis.git
cd ghi-hiv-impact-analysis
```

2. Open the notebook:

```bash
jupyter notebook
```

3. Run all cells sequentially to:

   * Load data
   * Clean datasets
   * Compute regimen mappings
   * Generate impact scores

---

## 📦 Outputs

The pipeline produces:

* Drug Impact Scores
* Overall Treatment Impact per Country
* Validation against original Excel calculations
* Structured outputs for downstream analysis

---

## 🎯 Project Motivation

Manual epidemiological modeling in spreadsheets introduces:

* Human error
* Limited scalability
* Poor reproducibility

This project enables:
✅ Automated computation
✅ Transparent methodology
✅ Reproducible global health analysis
✅ Scalable policy evaluation

---

## 🚀 Future Improvements

* Multi-year HIV trend analysis
* Visualization dashboards
* Automated WHO regional comparisons
* Integration with additional disease datasets
* Validation pipelines for GHI replication studies

---

## 👩‍💻 Author

**Shruthi Nagappan**
Graduate Student — Data Science
Indiana University Bloomington
