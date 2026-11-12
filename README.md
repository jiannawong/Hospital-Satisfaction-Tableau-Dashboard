# U.S. Hospital Satisfaction Dashboard (2016–2020)

An interactive data visualization dashboard designed to help patients, healthcare professionals, and communities evaluate and compare hospital satisfaction ratings across the United States from 2016 to 2020.

🔗 **[View the Interactive Visualization](https://public.tableau.com/app/profile/jianna.wong/viz/HospitalRatingsDashboard/HospitalSatisfaction)**

---

## 📌 Project Overview

While healthcare needs are universal, hospital quality and patient experience vary significantly across regions. Originally scoped to examine global hospital readmission rates, the project pivoted due to missing international standards and restricted CMS data access during the October 2025 federal government shutdown. Using a five-year HCAHPS dataset from Kaggle (2016–2020), we shifted focus to **U.S. Hospital Satisfaction**, enabling users to compare local hospital performance against county, state, and national benchmarks.

---

## 🧹 Data Cleaning & Preparation

* **Dataset Consolidation:** Merged five annual CSV files (2016–2020) in Python (Jupyter Notebook), totaling **1,653,683 raw records** across 43 columns.
* **Filtering & Standardization:** Removed `Not Applicable`, `NaN`, and `NA` star ratings; standardized text/dates; converted survey counts, percentages, and linear mean values to numeric types; and encoded national comparison categories (`1` = above, `0` = same, `-1` = below).
* **Feature Selection & Reshaping:** Dropped columns with high missingness (e.g., footnotes, Pain Management) and pivoted the wide star-rating columns into a tall format of 12 standardized HCAHPS indicators.
* **Geocoding:** Enriched hospital records with exact latitude and longitude coordinates using the **Google Maps Geocoding API** to prevent overlapping markers at the county/city level.
* **Final Dataset:** **17,183 cleaned records** covering **4,373 unique hospitals** across **1,272 counties**, **2,300 cities**, and **53 U.S. states and territories**.

---

## 📊 Key Exploratory Data Analysis (EDA) Insights

* **National Trends:** Participating hospitals declined slightly from 3,360 (2016) to 3,250 (2020), while survey response rates dropped from **28.45% to 25.11%**. Overall average summary ratings declined slightly from **3.40 stars (2016)** to **3.19 stars (2020)**, clustering heavily around 3 stars (~35%), with only **6.84%** achieving 5 stars.
* **Geographic Disparities:** Among high-volume states, **Wisconsin (3.98)**, **Louisiana (3.67)**, and **Indiana (3.58)** led in average summary ratings, whereas **New York (2.52)**, **Florida (2.63)**, and **California (2.67)** scored lowest.
* **Indicator Performance:** **Nurse Communication (3.41)** and **Overall Hospital Rating (3.36)** ranked highest, while **Cleanliness (2.97)** and **Quietness (2.97)** ranked lowest. Strong positive correlations emerged between Summary and Overall ratings ($r > 0.85$) and Nurse and Doctor communication ($r > 0.75$).
* **Institutional Factors:** Acute Care – Department of Defense facilities (**4.06**) and Critical Access Hospitals (**3.99**) outperformed standard Acute Care Hospitals (**3.12**). Hospitals with moderate survey response rates (25%–50%) averaged higher ratings (**3.52**) than low-response facilities (0%–25%, **2.89**).

---

## 🎨 Visualization Design & Iterative Testing

Guided by Edward Tufte’s principles of **Graphical Excellence** and **Graphical Integrity**, the dashboard was refined through paper prototyping, usability testing (with classmates, a nurse, a clinical pharmacist, and a frequent inpatient), and peer critiques:

1. **Hierarchical Drill-Down Map:** Consolidated three separate map panes into a single interactive map that drills down from **State → County → Individual Hospital**, complete with a click-out/reset feature for non-linear navigation.
2. **Coordinated Views:** Linked the map to a dynamic **Indicator Bar Chart** (using single-hue length encoding) and a **Time-Series Trend Chart** (comparing hospital ownership types against a dashed national average benchmark).
3. **Accessible Visual Encoding:** Adopted a color-blind-friendly **orange-to-blue** diverging palette to clearly distinguish underperforming and top-performing facilities, supplemented by contextual tooltips (hospital count, survey response rate) and rating range sliders.
4. **Multi-Hospital Comparison View:** Added a dedicated second dashboard page allowing users to filter by facility, hospital type, ownership, and specific HCAHPS factors to compare top performers side-by-side via horizontal bar charts and facility-level time series.


# Created as a team of 5 for Data Visualization Course at UW
