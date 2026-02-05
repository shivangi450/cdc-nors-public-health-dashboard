# 🦠 Targeting High-Risk Enteric Disease Outbreaks (NORS)

An interactive **public health analytics dashboard** built using CDC outbreak data to identify where enteric disease outbreaks occur most frequently and where interventions should be prioritized.

---

## 📊 Project Overview

Foodborne and waterborne disease outbreaks are a major public health concern. Using the **CDC NORS (National Outbreak Reporting System)** dataset, this project analyzes:

- Outbreak trends over time  
- Primary transmission modes  
- High-risk outbreak settings  
- Geographic distribution of outbreaks  

The goal is to help **public health professionals identify high-risk environments and guide prevention strategies**.

---

## 🗂 Dataset

**Source:** CDC National Outbreak Reporting System (NORS)  
🔗 https://data.cdc.gov/Foodborne-Waterborne-and-Related-Diseases/NORS/5xkq-dg7x/about_data  

The dataset includes outbreak reports across the United States, including:
- Illness counts  
- Transmission mode (Food, Water, Person-to-person, etc.)
- Setting of outbreak
- State and year

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Tableau** | Dashboard design and visualization |
| **CDC NORS Data** | Public health outbreak data |
| **Data Grouping Logic** | AI-assisted calculated field creation |

---

## 🧮 Key Feature: Setting Grouping Calculation

To simplify analysis, individual outbreak settings were grouped into broader public health categories using a Tableau calculated field:

```tableau
IF CONTAINS([Setting], "Restaurant")
    OR CONTAINS([Setting], "Cater")
    OR CONTAINS([Setting], "Deli")
    OR CONTAINS([Setting], "Cafe")
    OR CONTAINS([Setting], "Food truck")
THEN "Food Service Settings"

ELSEIF CONTAINS([Setting], "School")
    OR CONTAINS([Setting], "Daycare")
    OR CONTAINS([Setting], "Child care")
    OR CONTAINS([Setting], "College")
THEN "Educational Settings"

ELSEIF CONTAINS([Setting], "Hospital")
    OR CONTAINS([Setting], "Nursing")
    OR CONTAINS([Setting], "Long-term care")
    OR CONTAINS([Setting], "Clinic")
THEN "Healthcare Settings"

ELSEIF CONTAINS([Setting], "Private")
    OR CONTAINS([Setting], "Home")
    OR CONTAINS([Setting], "Residence")
THEN "Private / Household Settings"

ELSEIF CONTAINS([Setting], "Correctional")
    OR CONTAINS([Setting], "Prison")
    OR CONTAINS([Setting], "Jail")
THEN "Correctional Facilities"

ELSEIF CONTAINS([Setting], "Camp")
    OR CONTAINS([Setting], "Park")
    OR CONTAINS([Setting], "Recreational")
    OR CONTAINS([Setting], "Pool")
THEN "Recreational Settings"

ELSE
    "Other / Unknown"
END
```
