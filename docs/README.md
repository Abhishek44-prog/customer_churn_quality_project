# Customer Churn KPI Dashboard

An interactive, beginner-friendly dashboard for the Business KPI Dashboard data analytics task.

## Open locally
1. Extract this ZIP file.
2. Open `index.html` in Chrome, Edge, or Firefox.
3. Change the Contract type, Tenure range, and Payment method filters.
4. Review the KPI cards, segment charts, insights, and filtered customer table.

No installation, server, API key, or internet connection is required.

## Dashboard contents
- Churn rate = churned customers / total customers × 100
- Retention rate = retained customers / total customers × 100
- Monthly revenue at risk = sum of MonthlyCharges for churned customers
- Average tenure = mean TenureMonths for the filtered customers
- Filters: contract type, tenure band, payment method
- Visuals: churn by contract, retained vs churned, churn by payment method, customer count and churn by tenure band

## Dataset note
The supplied CSV contains 15 sample customers. Results are illustrative and should not be treated as statistically reliable forecasts. The dataset does not identify a currency, so monthly charges and revenue at risk are shown in dataset units.

## Publish with GitHub Pages
1. Create a GitHub repository.
2. Upload all files in this folder to the repository root.
3. In the repository, open **Settings → Pages**.
4. Choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
5. After deployment, open the GitHub Pages URL shown on that page. The dashboard will load from `index.html`.

## Files
- `index.html` — complete interactive dashboard
- `customer_churn_sample.csv` — supplied dataset
- `task-brief.md` — assignment brief
- `README.md` — this guide
