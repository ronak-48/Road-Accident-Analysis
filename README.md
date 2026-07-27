# Road-Accident-Analysis

An interactive Power BI dashboard analyzing 307,973 road accident records across the UK to help transport and safety stakeholders identify accident trends, high-risk locations, and casualty patterns.

<img width="592" height="335" alt="image" src="https://github.com/user-attachments/assets/2ddd4dd5-3d90-49d0-837b-6487e22ff0b9" />

---

## 1. Project Overview

- **Objective:** Build a Road Accident Dashboard for 2021 and 2022 to give stakeholders insight into casualty trends, accident severity, and high-risk conditions.
- **Tool used:** Microsoft Power BI (Power Query, DAX, Data Modeling)
- **Dataset size:** 307,973 accident records | 417,883+ casualties | 422 local authority districts
- **Time period:** January 2021 – December 2022

---

## 2. Business Problem

Stakeholders (Ministry of Transport, Road Transport Department, Police Force, Emergency Services, Road Safety Corps, Transport Operators, Traffic Management Agencies, and the Public) needed a single, interactive view to answer:

- Are casualties and accidents increasing or decreasing year-over-year?
- Which vehicle types, road types, and conditions are most associated with casualties?
- Where (geographically) are accidents concentrated?
- Do accidents happen more at night vs. day, and in urban vs. rural areas?

---

## 3. Stakeholders

- Ministry of Transport
- Road Transport Department
- Police Force
- Emergency Services Department
- Road Safety Corps
- Transport Operators
- Traffic Management Agencies
- Public / Media

---

## 4. Key Requirements

- Primary KPI: Total Casualties and Total Accidents (Current Year + YoY growth)
- Primary KPI: Total Casualties by Accident Severity (Current Year + YoY growth)
- Secondary KPI: Total Casualties by Vehicle Type (Current Year)
- Monthly trend comparing casualties: Current Year vs. Previous Year
- Casualties by Road Type (Current Year)
- Casualties by Area/Location and Day/Night (Current Year)
- Total Casualties and Accidents by Location (map view)

---

## 5. Data Cleaning & Preparation

Performed in Power Query before modeling:

- **Fixed data quality issue:** 49 records had `Accident_Severity` mislabeled as `"Fetal"` instead of `"Fatal"` — corrected to ensure accurate severity KPIs.
- **Handled missing data:** `Carriageway_Hazards` column was ~98% empty (302,549 of 307,973 rows) — excluded from primary analysis rather than imputed, to avoid introducing bias.
- **Minor gaps:** 17 missing `Time` values reviewed and handled.
- Standardized date fields and built a dedicated **Calendar/Date table** for time-intelligence calculations.
- Verified column data types (numeric, categorical, date) for accurate aggregation.

---

## 6. Data Modeling

- Built a star-schema-style model connecting the fact table (accident records) to a Calendar dimension table.
- Established relationships to support Year-over-Year (YoY) and Year-to-Date (YTD) calculations.
- Created custom DAX measures for:
  - Current Year (CY) vs. Previous Year (PY) casualties/accidents
  - YoY % growth for total casualties, accidents, and severity breakdown
  - Conditional KPI formatting (increase/decrease indicators)

---

## 7. Dashboard Features

- **Top KPI cards:** Total CY Casualties, Total CY Accidents, Fatal/Serious/Slight Casualties — each with YoY % change
- **Casualties by Vehicle Type:** Agricultural, Bike, Bus, Car, Other, Van
- **CY vs PY Monthly Trend:** line/area chart comparing casualties month-by-month across years
- **Casualties by Urban/Rural:** donut chart
- **Casualties by Location:** interactive map (Bing Maps integration)
- **Casualties by Road Type:** bar chart (Single carriageway, Dual carriageway, Roundabout, One-way street, Slip road)
- **Casualties by Light Conditions:** Day vs. Dark breakdown
- **Slicers/Filters:** Road Surface, Weather Conditions — fully cross-filter all visuals

---

## 8. Key Insights

- Total CY casualties: **195.7K** (↓11.9% YoY)
- Total CY accidents: **144.4K** (↓11.7% YoY)
- Fatal casualties: **2.9K** (↓33.3% YoY) — the steepest decline of any severity category
- **61.95%** of casualties occurred in urban areas vs. 38.05% in rural areas
- **Single carriageways** accounted for ~145K casualties — by far the highest of any road type, nearly 4.5x the next category (Dual carriageway, ~32K)
- **73.84%** of casualties occurred during daylight hours vs. 26.16% in the dark
- Cars were involved in the highest number of casualties among vehicle types (155,804), followed by Vans (15,905) and Bikes (15,610)

---

## 9. Tools & Skills Used

`Power BI` `Power Query` `DAX` `Data Modeling` `Data Cleaning` `Data Visualization` `Time Intelligence` `KPI Design` `Stakeholder Requirement Gathering`

---

## 10. Files in this Repository

| File | Description |
|---|---|
| `ROAD_AA.pbix` | Power BI project file (open in Power BI Desktop) |
| `Road_Accident_Data.xlsx` | Raw dataset used for analysis |
| `README.md` | This file |

---

## 11. How to View

1. Download `ROAD_AA.pbix`
2. Open in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. Interact
