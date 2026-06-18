# datases — Cleaned Example Datasets 📁

A curated collection of small, cleaned example datasets and lightweight tooling for data-practice and quick EDA. This repository contains the original raw data files, simple cleaning scripts, and preview notebooks to help you get started quickly.

This project preserves provenance: original raw CSVs are stored in `raw_dataset/`. Cleaning scripts (if used) live under `scripts/` and produce cleaned outputs under `cleaned_dataset/` when executed.
---

**Table of contents**

- Overview
- Datasets
- Quick start
- Cleaning scripts
- Reports
- Contributing & license
---

## Overview 🧭

The repository is intended for learning and prototyping. Files have been organized so you can find raw data quickly, run cleaning pipelines, and open minimal notebooks for exploration.

Naming conventions used here:
- human-readable filenames
- backups use `_bak_<TIMESTAMP>` suffix where present

---

## Datasets (short descriptions) 📚

Raw dataset files are in `raw_dataset/`. Major datasets include:
- `brazil_amazon_fires_annual.csv` — Amazon-region fire counts by year/month/state
- `grocery_outlet_sales_blinkit.csv` — Grocery items + outlet sales
- `zomato_restaurants_philippines.csv` — Restaurant listings and ratings
- `flipkart_orders_2024.csv` — Marketplace order data sample
- `ecommerce_sales_orders.csv` — E-commerce orders and totals
- `student_performance_scores.csv` — Student demographics and scores
- `titanic_passenger_manifest.csv` — Titanic passenger manifest
- `hr_employee_metrics.csv` — HR metrics dataset
- `youtube_channel_rankings.csv` — YouTube channel stats
- `restaurant_tips_bill_info.csv` — Restaurant bills & tips
- `population.xlsx` — Excel file

Backups (if any) keep original timestamps and are preserved.
---

## Quick start 🔎

Clone the repo and inspect raw files:

```bash
git clone https://github.com/sundaresan-dev/datases.git
cd datases
ls -lah raw_dataset
```

Open a CSV quickly with pandas (recommended):

```python
import pandas as pd
df = pd.read_csv('raw_dataset/titanic_passenger_manifest.csv')
print(df.shape)
print(df.columns)
print(df.head())
```

---

## Cleaning scripts (optional)

Two helper scripts are provided in `scripts/`:

- `generate_cleaned_and_notebooks.py` — copies raw CSVs into `cleaned_dataset/<name>/` and creates a minimal `01_clean_preview.ipynb` for each dataset.
- `full_clean_all.py` — simple CSV-only cleaner that normalizes headers, trims whitespace, deduplicates rows, and formats detected date columns to India format (`DD-MM-YYYY`).

Run (optional):

```bash
python3 scripts/generate_cleaned_and_notebooks.py
python3 scripts/full_clean_all.py
```

Note: `full_clean_all.py` uses only the Python standard library. For better numeric/date parsing and stronger cleaning, install `pandas` and re-run the more advanced cleaner instead (if included):

```bash
pip install --user pandas
# then run a pandas-enabled cleaner when available
```
---

## Reports

If you run `full_clean_all.py` the script generates:

- `cleaned_dataset/cleaning_report.json` — machine-readable cleaning report per file
- `cleaned_dataset/DATA_SUMMARIES.md` — human-readable summary per dataset

These files summarize row counts, columns, and missing counts.

## Contributing & license

If you improve cleaning logic or add notebooks, please open a PR. Add a concise commit message following conventional commits (e.g., `feat: add EDA notebook for titanic`).

Unless specified otherwise, assume these example datasets are provided for learning and demo purposes — verify redistribution rights before publishing.

---

Generated and maintained by the repository owner. For changes, edit files and push to the `main` branch on GitHub.

---

**Contributing / edits** ✍️

- Want shorter names? I can batch-rename to a shorter convention (e.g., `titanic.csv`) and optionally move originals to `archive/`.
- Want dataset summaries added (row counts, column types)? I can append a `DATA_SUMMARIES.md` with quick stats per file.
- Want this folder converted into a small demo Jupyter notebook? I can scaffold `notebooks/01-eda.ipynb` showing quick EDA for a chosen file.

To propose a change, open an issue or reply here with what you want renamed or added.

---

**License & attribution** 🧾

These example datasets are provided for learning and practice. If you uploaded any datasets, ensure you have rights to share them. This README is provided under a permissive note — reuse as you like for local learning and demos.

---

_Generated on 2026-06-18 — README expanded by assistant._ 🚀

# datases
