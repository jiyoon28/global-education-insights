# Global Education & Socioeconomic Dynamics

**Analyzing Gender, Performance, and Economic Correlations**

This repository contains the full workflow and report for a data-driven exploration of how education outcomes interact with gender, unemployment, birth rates, and broader socioeconomic indicators across 200+ countries.

---

## 1 Project Goals

- **Examine Education Trends**  
  Compare primary, lower-secondary, and upper-secondary completion rates, highlighting gender gaps.
- **Identify Relationships**  
  Quantify links between literacy/math proficiency and socioeconomic factors such as unemployment and birth rates.
- **Highlight Global Disparities**  
  Contrast developed vs developing regions to show where access and performance diverge most.

---

## 2 Dataset

| Field       | Detail                                                                                  |
| ----------- | --------------------------------------------------------------------------------------- |
| **Source**  | Kaggle — _World Educational Data_                                                       |
| **Rows**    | 202 countries                                                                           |
| **Columns** | 29 attributes (completion rates, proficiency, literacy, unemployment, birth rate, etc.) |

A full data dictionary is provided in `docs/`.

---

## 3 Methodology

1. **Relational DB Design** – 5 tables (`Countries`, `Out_of_School_Rates`, `Completion_Rates`, `Education_Proficiency`, `Social_Indicators`) built in SQLite.
2. **Data Cleaning** – typo fixing, zero-heavy row removal, outlier inspection (IQR), duplicate & NA checks.
3. **Exploratory Data Analysis** – bar charts, correlation heatmaps, scatter plots, and choropleth maps via Python (Pandas, Seaborn, Matplotlib, GeoPandas).
4. **Report Writing** – LaTeX (QMUL MSc template), ~40 pages plus figures.

---

## 4 Repository Layout

.
├── data/
│ └── world_education.csv
├── db/
│ └── education.db
├── notebooks/
│ ├── 01_cleaning.ipynb
│ ├── 02_eda.ipynb
│ └── 03_viz.ipynb
├── visuals/
│ ├── completion_gender.png
│ ├── corr_heatmap.png
│ ├── tertiary_vs_birthrate.png
│ └── unemployment_choropleth.png
├── report/
│ └── Global_Edu_Socio_Dynamics.pdf
└── README.md

---

## 5 Key Findings

- **Gender Gap** – Females slightly out-perform males across all completion levels, yet overall completion drops sharply by upper secondary.
- **Skill Alignment** – Strong within-stage correlation (e.g., lower-secondary reading vs math = 0.94), weak across stages → early skills don’t guarantee later success.
- **Education vs Birth Rate** – Countries with >50 % tertiary enrolment show birth rates below 10 ‰; inverse holds in Sub-Saharan Africa and parts of South Asia.
- **Unemployment Hotspots** – Highest unemployment clusters in South Africa and neighbouring regions, correlating with low education completion and high out-of-school rates.

---

## 6 How to Reproduce

```bash
# clone repo
git clone https://github.com/your-user/edu-socioecon-dynamics.git
cd edu-socioecon-dynamics

# set up Python env
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt

# (optional) rebuild SQLite DB
python src/build_db.py data/world_education.csv

# run notebooks
jupyter lab
```
