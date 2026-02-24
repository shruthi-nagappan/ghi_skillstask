# 🌍 Global Health Impact (GHI) – HIV Data Analysis (2015)

This project analyzes global HIV treatment data from 2015 to compute treatment impact scores across countries and WHO regions using the **Global Health Impact (GHI)** methodology.

The primary goal of this project is to **validate and check compliance of programmatically computed impact scores against the official impact scores provided in the original Excel model**.

---

## 📌 Project Objective

The objective of this project is to:

✅ Automate HIV treatment impact calculations using Python
✅ Reproduce drug and regimen impact computations from structured health data
✅ **Verify whether calculated impact scores match and remain compliant with the impact scores reported in the original Excel workbook**

This ensures consistency between automated analysis pipelines and the established Excel-based GHI framework.

---

## ⚙️ Project Workflow

### 1️⃣ Data Acquisition

* Loads HIV data directly from the Google Sheets source (`HIV2015`).
* Imports epidemiological and treatment indicators used in the original Excel model.

---

### 2️⃣ Data Cleaning

Preprocessing steps include:

* Cleaning raw Excel headers
* Handling missing values (`NaN`)
* Parsing formatted numeric entries:

  * Removing commas (`1,000`)
  * Converting percentages (`85%`)
* Standardizing values for accurate comparison with Excel outputs

---

### 3️⃣ Regimen Analysis

Antiretroviral (ARV) treatment regimens are extracted and mapped exactly as structured in the Excel sheet, including:

* Adult First-Line regimens
* Children First-Line regimens
* Second-Line regimens

Each regimen retains alignment with:

* Drug efficacy values
* Treatment proportions
* Excel row/column mappings

---

## 🧮 Impact Score Validation

Impact scores are calculated using epidemiological inputs such as:

```
Impact Score =
DALYs × Treatment Coverage × Retention × Drug Efficacy × Regimen Proportion
```

The computed results are then **compared directly with the impact scores already present in the Excel dataset** to:

* Check computational correctness
* Identify mismatches
* Validate row mappings and drug attribution
* Ensure methodological compliance

---

## 📈 Key Validation Variables

| Variable                    | Purpose                                 |
| --------------------------- | --------------------------------------- |
| `actual_*`                  | Impact scores reported in Excel         |
| `calc_*`                    | Programmatically computed impact scores |
| `adult_daly` / `child_daly` | Disease burden inputs                   |
| `retention_pct`             | Treatment retention factor              |

Drugs validated include:

3TC, ABC, AZT, ddl, d4T, EFV, FTC, LPV/r, NVP, TDF, ATV/r

---

## 🎯 Project Motivation

The original GHI calculations rely heavily on complex Excel formulas that are difficult to audit and scale.

This project enables:

✅ Automated verification of Excel results
✅ Transparent validation of treatment impact calculations
✅ Detection of inconsistencies between computed and reported scores
✅ Reproducible global health analytics workflows
