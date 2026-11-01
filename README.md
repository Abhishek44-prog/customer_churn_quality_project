# Customer Churn Data Quality Project

## Files
- `customer_churn_sample.csv` — original supplied dataset
- `cleaned_customer_churn.csv` — cleaned analysis-ready CSV
- `data_quality_analysis.ipynb` — reproducible notebook
- `data_quality_report.md` — data-quality summary/report
- `data_quality_workbook.xlsx` — optional workbook with raw/cleaned data and audit tables
- `churn_distribution.png`, `churn_by_contract.png`, `monthly_charges_by_churn.png` — visualizations

## Run in VS Code
1. Install Python 3.10 or newer.
2. Open this folder in VS Code.
3. In the terminal run: `python -m pip install pandas numpy matplotlib openpyxl`
4. Open `data_quality_analysis.ipynb`, select a Python kernel, and click **Run All**.
5. Keep `customer_churn_sample.csv` in the same folder as the notebook. The notebook writes `cleaned_customer_churn.csv`.

## One proof link (GitHub)
1. Sign in to GitHub and create a new repository, e.g. `customer-churn-data-quality`.
2. Upload all files in this folder (or push this folder using Git).
3. Ensure the repository is **Public**, or use a private repository only if your reviewer has access.
4. Copy the repository URL and submit that single URL. It will contain the notebook, cleaned CSV, report, workbook, and charts.

## Alternative (Google Drive)
Upload the project files into one folder, choose **Share → General access → Anyone with the link → Viewer**, then copy the folder link. Check it in a private/incognito window before submission.

## Interpretation caveat
The dataset has 15 rows and is synthetic. Group comparisons are descriptive and should not be treated as robust prediction, causal evidence, or population estimates.
