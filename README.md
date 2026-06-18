# Dataset Practice 📁

A curated collection of small datasets for learning, practicing, and demonstrating data analysis workflows. Filenames have been normalized to be descriptive and human-readable. Backup copies that existed originally were preserved and renamed with `_bak_<TIMESTAMP>` to keep provenance.

---

**Table of contents**

- **Overview**
- **Datasets**
- **Quick preview (shell & Python)**
- **Suggested analyses**
- **Rollback & maintenance**
- **Contributing**
- **License & attribution**

---

**Overview** 🧭

This folder contains a variety of CSV datasets (and a single Excel file) intended for quick exercises and tutorials. Filenames were renamed for clarity — they reflect the dataset subject and, when present, include `_bak_` timestamps for original backups.

**Why these names?**
- Human-readable: easier to identify dataset purpose at a glance.
- Safe: backups were kept and suffixed with `_bak_<timestamp>`.
- Consistent: lowercase, underscores, descriptive tokens.

---

**Datasets (files & short descriptions)** 📚

- `brazil_amazon_fires_annual.csv` — Amazon-region fire counts by year/month/state (original: `amazon_fires.csv`).
- `grocery_outlet_sales_blinkit.csv` — Grocery items and outlet sales data (original: `blinkit_data.csv`).
- `zomato_restaurants_philippines.csv` — Zomato restaurant listings and ratings (original: `Dataset .csv`).
- `zomato_restaurants_philippines_bak_20260618092900.csv` — Backup of the above.
- `employee_personal_employment.csv` — Employee records: name, dept, salary, join date (original: `employee_data.csv`).
- `employee_personal_employment_bak_20260618092900.csv` — Backup of the above.
- `flipkart_orders_2024.csv` — Marketplace order data / sales sample (original: `flipkart_sales.csv`).
- `flipkart_orders_2024_bak_20260618092900.csv` — Backup of the above.
- `hr_employee_metrics.csv` — HR metrics: projects, monthly hours, tenure, turnover flag (original: `hr_data.csv`).
- `ecommerce_sales_orders.csv` — E-commerce order-level totals with dates and regions (original: `sales_dataset.csv`).
- `student_performance_scores.csv` — Student demographics and exam scores (original: `student_data.csv`).
- `restaurant_tips_bill_info.csv` — Restaurant bills and tips dataset (original: `tips.csv`).
- `titanic_passenger_manifest.csv` — Titanic passenger manifest (pclass, name, sex, age, fare, survived) (original: `titanic.csv`).
- `titanic_passenger_manifest_bak_20260618092900.csv` — Backup of the Titanic file.
- `youtube_channel_rankings.csv` — Channel ranking, subscribers, views (original: `youtube_channel.csv`).
- `youtube_channel_rankings_bak_20260618092900.csv` — Backup of the YouTube file.
- `population.xlsx` — Excel file (not modified).
- `scripts/` — Small utilities and helpers present in the folder (not modified).

---

**Quick preview — shell & Python** 🔎

List files in the folder:

```bash
ls -lah
```

Preview header lines from a CSV (shell):

```bash
head -n 3 brazil_amazon_fires_annual.csv
```

Open a dataset with pandas (Python):

```python
import pandas as pd

# load
df = pd.read_csv('titanic_passenger_manifest.csv')

# quick checks
print(df.shape)
print(df.dtypes)
print(df.head())

# preview multiple files programmatically
from pathlib import Path
for f in Path('.').glob('*_*.csv'):
	print(f.name)
	print(pd.read_csv(f, nrows=3))
	print('---')
```

---

**Suggested starter analyses** 📊

- Titanic: survival rate by class / sex / age group.
- Student scores: correlations between study hours and math reading/writing.
- HR metrics: churn prediction (left) using tenure, monthly hours, projects.
- E-commerce & Flipkart: top products by revenue, monthly trends.
- YouTube: top channels by subscribers/views, normalized metrics.

Each dataset is intentionally small and ready for quick EDA, visualization, feature engineering, and modelling tasks.

---

**Rollback & maintenance** 🔁

Backups were preserved by renaming originals with `_bak_<TIMESTAMP>` where applicable. If you want to restore the original filenames, run the corresponding `mv` commands in this folder. Example (from the repo root):

```bash
mv -n brazil_amazon_fires_annual.csv 'amazon_fires.csv'
mv -n grocery_outlet_sales_blinkit.csv 'blinkit_data.csv'
mv -n zomato_restaurants_philippines.csv 'Dataset .csv'
mv -n zomato_restaurants_philippines_bak_20260618092900.csv 'Dataset .csv.bak.20260618092900'
# ... (other mv commands available in the assistant output)
```

Tip: add `-v` to `mv` to see each rename logged, or run in `bash -x` for debugging.

If you prefer to remove backup files (cleanup), run:

```bash
rm *_bak_*.csv
```

Be careful — that permanently deletes backup files.

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
