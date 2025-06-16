# A-B-Testing-Analysis-From-Python-to-Interactive-Dashboard

This project presents a complete A/B testing analysis using Python and Tableau. The aim is to evaluate the effectiveness of product experiments using statistical significance testing and visual analytics.

## Project Goal

To assess the performance of different product tests using statistical methods (Z-test for proportions) and visualize the impact on key conversion metrics.

---

## Tools & Technologies

- **Python (Pandas, Statsmodels, NumPy)** for data manipulation and statistical analysis
- **Google Colab** for cloud-based execution
- **Google Drive** for data storage
- **Tableau Public** for interactive dashboards

---

## Dataset

- Format: CSV file from **Google BigQuery** results
- Time Period: **November 1, 2020 – January 27, 2021**
- Size: ~801,000 rows
- Key Fields: `date`, `country`, `device`, `channel`, `event_name`, `test`, `test_group`, `value`

---

## Project Steps

### 1. **Data Preparation**
- Mounted Google Drive in Colab
- Loaded CSV file
- Cleaned and normalized categorical columns
- Replaced inconsistent values
- Parsed dates and ensured consistency

### 2. **Exploratory Analysis**
- Checked for nulls and duplicates
- Analyzed the number of unique countries, devices, continents, and channels per test
- Verified 50/50 distribution across control and test groups
- Evaluated balance across `device`, `continent`, and `channel`

### 3. **Statistical Significance Testing**
Performed **Z-tests for proportions** to compare the following metrics between test and control groups:

| Metric                | Description                             |
|-----------------------|-----------------------------------------|
| `add_payment_info`    | % of sessions where payment info added  |
| `add_shipping_info`   | % of sessions where shipping info added |
| `begin_checkout`      | % of sessions that started checkout     |
| `new_account`         | % of sessions with new account created  |
| `first_visit`         | % of sessions from first-time visitors  |
| `select_promotion`    | % of sessions where promotions selected |

Each test was evaluated separately for statistical significance (p < 0.05).

---

## 📈 Key Results

| Test | Significant Metrics                          | Notes |
|------|----------------------------------------------|-------|
| 1    | ✅ `add_payment_info`, `add_shipping_info`, `begin_checkout` | Strong improvement in conversion funnel steps |
| 2    | ❌ None                                       | No significant changes found |
| 3    | ✅ `begin_checkout`                           | Partial success |
| 4    | ✅ `begin_checkout`, `new_account`            | Encouraging results on user activation |

---

## Conclusion

- Tests 1, 3, and 4 showed statistically significant improvements in key metrics.
- `begin_checkout` consistently improved across successful tests.
- Test 2 requires a review of its hypothesis and implementation.
- Metrics such as `first_visit` and `select_promotion` were unaffected in all tests.

---

## Tableau Dashboard

View the full visualized analysis here:  
🔗 [A/B Testing Dashboard (Tableau Public)](https://public.tableau.com/app/profile/oksana.sitalova/viz/A_BTESTINGANALYSIS/Dashboard1?publish=yes)

---

## Output Files

- `ab_test_selected_metrics.csv`: Summary of Z-test results per test and metric.

---

## How to Reproduce

1. Open [Google Colab](https://colab.research.google.com/)
2. Mount your Google Drive
3. Upload the dataset and run the notebook step-by-step
4. Export results and visualize in Tableau

