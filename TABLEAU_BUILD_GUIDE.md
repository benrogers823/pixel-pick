# Tableau Dashboard Build Guide
## UK Crime Analysis — Rural vs Urban

All data files are in the `data/` folder. Build two dashboards in Tableau Public Desktop,
then publish to your profile at https://public.tableau.com/app/profile/ben.rogers6008

---

## Dashboard 1: Force Overview

### Sheet 1 — Crime Distribution by Force (Grouped Bar)
- **Data file:** `crime_by_force_type.csv`
- **Chart type:** Bar
- Drag `Crime_Type` → Columns
- Drag `Count` → Rows
- Drag `Force` → Color (Marks card)
- Sort bars descending by Count
- **Title:** Crime Distribution Across Forces

### Sheet 2 — Investigation Outcomes (Donut Chart)
- **Data file:** `investigation_outcomes.csv`
- **Chart type:** Pie → convert to donut
- Drag `Outcome` → Color
- Drag `Percentage` → Angle
- Duplicate the sheet, set inner chart size to create donut effect
- **Title:** Investigation Outcomes

### Sheet 3 — Violence vs Non-Violence (100% Stacked Bar)
- **Data file:** `violence_split_by_force.csv`
- **Chart type:** Bar (stacked)
- Drag `Force` → Rows
- Drag `Percentage` → Columns
- Drag `Category` → Color
- Set axis to 100% stacked
- **Title:** Violence vs Non-Violence by Force

### Sheet 4 — Solve Rate by Force (Bar)
- **Data file:** `solve_rates_by_force.csv`
- **Chart type:** Bar
- Drag `Force` → Columns
- Drag `Charge_Rate_Percent` → Rows
- Drag `Force` → Color
- Add reference line at average
- **Title:** Charge Rate by Force (%)

### Dashboard 1 Layout
- Place Sheet 1 (large) across the top
- Sheet 2 and Sheet 3 side by side in the middle
- Sheet 4 across the bottom
- Add a filter on `Force` that applies to all sheets
- Title: **UK Crime: Force Overview**

---

## Dashboard 2: Rural vs Urban Deep Dive

### Sheet 5 — Normalised Crime Rates per 1,000 (Grouped Bar)
- **Data file:** `crime_by_force_type.csv`
- **Chart type:** Bar
- Drag `Crime_Type` → Columns
- Drag `Rate_Per_1000` → Rows
- Drag `Force` → Color
- **Key insight callout:** Avon & Somerset violence rate (491) is HIGHER than Metropolitan (320)
- **Title:** Crime Rate per 1,000 Records — Normalised Comparison

### Sheet 6 — Violence Rate by Force (Bar)
- **Data file:** `crime_by_force_type.csv`
- Filter: `Crime_Type = Violence`
- Drag `Force` → Columns
- Drag `Rate_Per_1000` → Rows
- Drag `Force` → Color
- Add `Urban_Rural` to the label
- **Title:** Violence Rate per 1,000 — Rural vs Urban

### Sheet 7 — Charge Rate by Crime Type (Bar)
- **Data file:** `charge_rates_by_crime.csv`
- **Chart type:** Bar (sorted descending)
- Drag `Crime_Type` → Columns
- Drag `Charge_Rate_Percent` → Rows
- Color: single colour (green)
- **Title:** Charge Rate by Crime Type (%)

### Sheet 8 — Theft Breakdown (Pie / Treemap)
- **Data file:** `theft_breakdown.csv`
- **Chart type:** Treemap (works better than pie in Tableau)
- Drag `Theft_Type` → Color and Label
- Drag `Count` → Size
- **Title:** Theft Crime Breakdown

### Sheet 9 — Drug Offences by Force (Bar)
- **Data file:** `crime_by_force_type.csv`
- Filter: `Crime_Type = Drugs`
- Drag `Force` → Columns
- Drag `Count` → Rows
- Drag `Force` → Color
- **Title:** Drug Offences by Force

### Dashboard 2 Layout
- Sheet 5 (large) at the top — this is the headline visual
- Sheet 6 and Sheet 9 side by side in the middle
- Sheet 7 and Sheet 8 side by side at the bottom
- Add `Urban_Rural` filter card on the right
- Title: **Rural vs Urban: Normalised Crime Analysis**

---

## Publishing to Tableau Public

1. File → Save to Tableau Public As...
2. Sign in to your Tableau Public account
3. Name the workbook: **UK Crime Analysis — Rural vs Urban**
4. Once published, copy the URL of each dashboard
5. Update the link in your portfolio HTML:
   - Open `index.html`
   - Find `https://public.tableau.com/app/profile/ben.rogers6008`
   - Replace with the direct dashboard URL (e.g. `https://public.tableau.com/app/profile/ben.rogers6008/viz/UKCrimeAnalysis/Dashboard1`)

---

## Recommended Colour Palette (matches your portfolio)
- Metropolitan Police: `#DC143C` (crimson)
- Avon and Somerset: `#FFD700` (gold)
- Northern Ireland: `#00D4FF` (cyan)
- Use these as custom hex colours in Tableau's colour picker

---

## Tips
- Use **dark background** (grey #1a1a2e or similar) to match your portfolio aesthetic
- Set all sheet titles using the same font (Source Sans Pro or similar)
- Add tooltips to every chart — employers notice this
- On Dashboard 2, add a text object explaining the normalisation methodology
