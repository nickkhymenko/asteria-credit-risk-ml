# asteria-credit-risk-ml
IB99Z0 Programming &amp; Big Data Analytics Group Assignment

Predicting which Asteria Finance loan applicants will experience repayment difficulty (`TARGET` in `loan_applications.csv`).

## Notebooks (run in order)

| Notebook | CRISP-DM phase | What it does |
|---|---|---|
| `01_eda.ipynb` | Data understanding | EDA of the main application table |
| `02_data_understanding.ipynb` | Data understanding | Structure, coverage and risk signals in the six history tables |
| `03_feature_pipeline.ipynb` | Data preparation | DuckDB SQL aggregation of all seven tables to one row per applicant, data quality fixes, engineered ratios. Writes `processed/features_*.parquet` |
| `04_modelling.ipynb` | Modelling and evaluation | Scorecard vs random forest vs monotone LightGBM, cross-validation with confidence intervals, held-out test, profit-based cut-off, scorecard points, SHAP, fairness checks, `predictions.csv` |

## Data setup

The CSV files are not in the repository and must not be submitted.

* **Colab:** upload the CSVs to `/content` (the default when running in Colab).
* **Locally:** put them in a `data/` folder in the repository root.
* **Anywhere else:** set the `ASTERIA_DATA_DIR` environment variable to the folder that holds them.

Expected files: `loan_applications.csv`, `previous_loan_applications.csv`, `external_credit_accounts.csv`, `external_account_history.csv`, `instalment_payments.csv`, `pos_cash_balance.csv`, `credit_card_balance.csv`, plus the unlabelled test applicants (set its name in `TEST_FILE` in notebook 03, or with `ASTERIA_TEST_FILE`).

## Local install

```bash
pip install -r requirements.txt
```
