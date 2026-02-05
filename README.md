# 🦠 Targeting High-Risk Enteric Disease Outbreaks (NORS)

An interactive **public health analytics dashboard** built using CDC outbreak data to identify where enteric disease outbreaks occur most frequently and where prevention efforts should be prioritized.

---

## 🚨 Public Health Problem

Enteric diseases (foodborne, waterborne, and person-to-person infections) cause thousands of illnesses every year. Public health agencies collect large volumes of outbreak data, but the information is often too detailed and fragmented to quickly guide prevention decisions.

**Challenge:**  
How can we simplify complex outbreak data to help health officials identify:

- High-risk transmission modes  
- High-risk outbreak environments  
- Geographic hotspots  
- Trends over time  

This project transforms raw CDC outbreak data into a **decision-support dashboard**.

---

## 🎯 Project Goal

To design a **data-driven visualization tool** that helps public health professionals:

✔ Identify where outbreaks occur most often  
✔ Understand which transmission modes are most dangerous  
✔ Recognize high-risk settings (restaurants, schools, healthcare, etc.)  
✔ Support targeted prevention and intervention strategies  

---

## 🗂 Dataset

**Source:** CDC National Outbreak Reporting System (NORS)  
🔗 https://data.cdc.gov/Foodborne-Waterborne-and-Related-Diseases/NORS/5xkq-dg7x/about_data  

The dataset includes:

- Number of illnesses
- Transmission mode (Food, Water, Person-to-person, etc.)
- Outbreak setting
- State and year

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Tableau** | Dashboard development |
| **CDC NORS Dataset** | Public health outbreak data |
| **AI-assisted Logic** | Grouping outbreak settings into major categories |

---

## 🧮 Key Feature: Setting Grouping Calculation

To make analysis easier for non-technical public health audiences, detailed outbreak settings were grouped into broader categories using a Tableau calculated field.

See full logic in:  
📁 `calculated-fields/setting_group_calculation.txt`

---

## 📊 Dashboard Features

✔ Illness trends over time by transmission mode  
✔ Heatmap of high-risk settings and transmission types  
✔ Top states by outbreak burden  
✔ Interactive filters for health outcome and state  
✔ Public-health focused storytelling  

---

## 🖼 Dashboard Preview

![Dashboard Screenshot](Media/dashboard_screenshot.jpeg)

---


## 🎥 Dashboard Demo Video

Watch the full interactive walkthrough of the dashboard on YouTube:

[![Watch the Demo](https://img.youtube.com/vi/Yv-9ihYHUuo/0.jpg)](https://youtu.be/Yv-9ihYHUuo)

▶ Click the image above to view the demo




---


## 🧮 Key Feature: Setting Grouping Calculation
Purpose:
This calculated field groups detailed outbreak setting values into broader public health categories to simplify analysis and dashboard interpretation.

Calculation Logic:

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
---

## 📈 Project Outcomes & Results

The dashboard reveals key public health patterns:

- **Food-related outbreaks** contribute the largest number of illnesses overall  
- **Person-to-person transmission** is dominant in institutional settings like schools and long-term care  
- **Healthcare and long-term care facilities** show high severity risk despite fewer events  
- **Certain states consistently report higher outbreak counts**, indicating areas for stronger surveillance and prevention

These insights allow health agencies to prioritize **inspection, education, and prevention programs** where they matter most.

---

## 🌍 Impact

This project demonstrates how data visualization can:

✔ Improve understanding of disease transmission patterns  
✔ Help public health officials allocate resources effectively  
✔ Support evidence-based outbreak prevention strategies  
✔ Communicate complex epidemiological data to decision-makers  

---

## 🔮 Future Improvements

With more time and expanded data, this dashboard could be enhanced by:

- Adding **hospitalization and fatality severity metrics**
- Incorporating **seasonal outbreak trend analysis**
- Predictive modeling to **forecast outbreak risk**
- Integrating **real-time reporting systems**
- Comparing outbreak patterns **before and after public health interventions**

---

## 👩‍⚕️ Author

**Shivangi Borad**  
Healthcare Data Analytics | Public Health Analytics | AI in Healthcare  

Passionate about using data to improve healthcare operations, disease prevention, and public health decision-making.
