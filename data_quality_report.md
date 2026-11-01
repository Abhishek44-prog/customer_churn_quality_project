# Customer Churn Data Quality Report

## 1. Objective and source
This project profiles and cleans the supplied `customer_churn_sample.csv`, validates documented rules, and performs a small exploratory analysis. The assignment brief asks for column/data-type profiling, missing values, outliers, duplicates, cleaning assumptions, validation, summary statistics, meaningful distributions, and one shareable project link. The supplied dataset contains synthetic customer records; findings are descriptive only.

## 2. Dataset overview
- Raw records: **15**
- Cleaned records: **15**
- Columns: **11**
- Exact duplicate rows detected/removed: **0**
- Missing cells before cleaning: **0**
- Missing cells after cleaning: **0**
- Customer IDs duplicated after cleaning: **0**
- Validation checks passed: **10/10**
- Churn labels: **Yes = 7, No = 8** (observed churn proportion **46.7%**).

## 3. Profiling results
See the notebook and `data_quality_workbook.xlsx` for column data types, missing counts, unique values, numeric summary statistics, and IQR-based outlier review. The raw file has 0 missing cells and 0 exact duplicate rows. The dataset is small (15 rows), so distribution and churn comparisons should be interpreted cautiously.

## 4. Cleaning assumptions
1. **Text normalization:** trim whitespace and title-case categorical labels. Customer IDs are trimmed and uppercased.
2. **Types:** age, tenure, and support-ticket count are treated as nullable integers; charges are numeric values rounded to two decimal places.
3. **Duplicates:** remove exact duplicate rows only. Do not drop records merely because a category or value repeats. Check `CustomerID` uniqueness separately.
4. **Validity ranges:** age outside 0–120, negative tenure, negative support tickets, or negative charges are treated as invalid and set to missing. Zero charges and zero tenure are allowed.
5. **Missing values:** do not impute values automatically in this sample. Any missing values are retained and reported because there is no domain context to justify a replacement.
6. **Churn labels:** expected values are `Yes` or `No` (case-insensitive after normalization).
7. **Charge consistency:** check whether `TotalCharges` is approximately `MonthlyCharges × TenureMonths` within 0.01. This is an assumption inferred from the supplied rows, not a guaranteed business rule; investigate discrepancies with a data owner before overwriting values.
8. **Outliers:** flag values beyond 1.5×IQR fences for review. Do not remove them automatically; legitimate customers can be statistical outliers.

## 5. Validation checks
See `validation_checks` in the workbook and the validation table in the notebook. Checks cover exact duplicates, unique customer IDs, missing-value handling, plausible numeric ranges, allowed churn labels, and the approximate charge consistency relationship. The notebook uses assertions so the workflow visibly fails if a required validation rule does not pass. A passing check only means the data conforms to the chosen rule; it does not prove the data is factually correct.

## 6. Exploratory findings
- Observed churn is **7/15 (46.7%)** in this sample.
- The contract-level and subscription-level tables compare customer counts, churned counts, and average monthly charges.
- The charts inspect overall churn distribution, churn rate by contract type, and monthly charges by churn status.
- Because the dataset has only 15 records, these are sample patterns, not statistically reliable predictions or causal conclusions.

## 7. Reproducibility
Open `data_quality_analysis.ipynb` in VS Code or Jupyter, keep `customer_churn_sample.csv` in the same folder, and run all cells top-to-bottom. The notebook exports `cleaned_customer_churn.csv`. Install dependencies with:
`python -m pip install pandas numpy matplotlib openpyxl`

## 8. Deliverables
- `data_quality_analysis.ipynb` — reproducible profiling, cleaning, validation, statistics, and charts.
- `cleaned_customer_churn.csv` — cleaned analysis-ready dataset.
- `data_quality_report.md` — this report.
- `data_quality_workbook.xlsx` — optional review workbook with raw/cleaned data and summary tabs.
- PNG chart files — visual evidence used in the analysis.

## 9. Limitations
This is a small synthetic sample. Results may not generalize to actual customers. No records were deleted except exact duplicates, and no imputation was applied because the supplied file has no missing values. Business rules should be confirmed before operational use.
