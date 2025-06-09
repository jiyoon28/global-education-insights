# Global-Education-Insights

End-to-end Python & SQLite workflow for analysing worldwide education data and its links to gender, proficiency, and socioeconomic indicators.

---

## 1 What the code does

1. **Create & populate a relational database**

   - Builds five tables (`countries`, `out_of_school_rates`, `completion_rates`, `education_proficiency`, `social_indicators`) in **SQLite**.
   - Loads the original _Global_Education.csv_ → cleans column names → inserts into each table.

2. **Data cleaning & quality checks**

   - Verifies dtypes, missing values, duplicates, country-name typos.
   - Examines outliers with boxplots and an IQR method; keeps full sample but drops rows with ≥ 15 zero values.

3. **Exploratory Data Analysis (EDA)**

   - **Gender completion gap** – bar chart by primary / lower-sec / upper-sec.
   - **Reading ↔ Math proficiency** – correlation heatmap across stages.
   - **Tertiary enrolment vs birth rate** – scatter + correlation ( r ≈ −0.68).
   - **Choropleths** – Plotly maps for tertiary enrolment, birth rate, and unemployment.

---

## 2 Quick start

```bash
# clone and install
git clone https://github.com/your-user/global-education-insights.git
```
