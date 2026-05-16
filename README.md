# 🏨 Hospital Performance Dashboard | Power BI

> A single-page Power BI dashboard analysing hospital operational performance — tracking patient admissions, bed occupancy, billing, insurance coverage, doctor workload, and follow-up scheduling with an integrated Q&A visual for natural language querying.

---

## 🛠️ Tools & Technologies

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat)
![Power Query](https://img.shields.io/badge/Power_Query-217346?style=flat)

---

## 🎯 Objective

To build an operational hospital dashboard that gives hospital management a real-time view of:
- **Patient volume** — total admissions, admit and discharge dates
- **Bed occupancy** — how efficiently beds are being utilised
- **Billing vs. insurance coverage** — how much patients pay vs. what insurance covers
- **Doctor workload** — patient load per doctor
- **Diagnosis breakdown** — which conditions are most common
- **Follow-up scheduling** — patients requiring post-discharge follow-up
- **Q&A querying** — ask natural language questions about hospital data directly in the dashboard

---

## 📁 Dataset Overview

**Single source table:** `Sheet1`

| Column | Description |
|--------|-------------|
| `Patient_ID` | Unique patient identifier |
| `Admit_Date` | Date of hospital admission |
| `Discharge_Date` | Date of patient discharge |
| `Diagnosis` | Medical diagnosis / condition |
| `Bed_Occupancy` | Bed occupancy status / count |
| `Test` | Medical tests conducted |
| `Doctor` | Attending doctor |
| `Followup Date` | Scheduled follow-up appointment date |
| `Feedback` | Patient satisfaction feedback |
| `Billing Amount` | Total bill charged to patient |
| `Health Insurance Amount` | Amount covered by health insurance |

**Derived / calculated:**
- `Length of Stay` = `Discharge_Date` − `Admit_Date`
- `Out-of-Pocket Amount` = `Billing Amount` − `Health Insurance Amount`

---

## 📊 Dashboard Visuals (Single Page)

| Visual | Type | Purpose |
|--------|------|---------|
| Total Patients KPI | Card | Count of unique Patient_IDs |
| Total Billing KPI | Card | Sum of Billing Amount |
| Insurance Coverage KPI | Card | Sum of Health Insurance Amount |
| Bed Occupancy KPI | Card | Bed utilisation count/rate |
| Admissions Over Time | Line Chart | Admit_Date trend — monthly/weekly |
| Billing vs. Insurance | Column Chart | Side-by-side billing vs. insurance by diagnosis |
| Diagnosis Distribution | Donut Chart | Patient volume by diagnosis |
| Patients by Doctor | Funnel Chart | Doctor-wise patient load ranking |
| Follow-up Timeline | Line Chart | Followup Date distribution |
| Q&A Visual | Q&A | Natural language querying of hospital data |
| Slicers | Slicer | Filter by Diagnosis, Doctor, Admit Date, Feedback |

---

## ⭐ Special Feature — Q&A Visual

This dashboard includes Power BI's **Q&A Visual**, which allows users to type natural language questions and get instant chart answers. For example:
- *"Total billing by diagnosis"*
- *"Count of patients admitted in January"*
- *"Average bed occupancy by doctor"*

This makes the dashboard accessible to non-technical stakeholders who don't know how to use slicers or pivot tables.

---

## 🔢 Key DAX Measures

```dax
Total Patients       = DISTINCTCOUNT(Sheet1[Patient_ID])
Total Billing        = SUM(Sheet1[Billing Amount])
Insurance Coverage   = SUM(Sheet1[Health Insurance Amount])
Out of Pocket        = [Total Billing] - [Insurance Coverage]
Avg Length of Stay   = AVERAGEX(Sheet1, 
                         DATEDIFF(Sheet1[Admit_Date], Sheet1[Discharge_Date], DAY))
Bed Occupancy Total  = SUM(Sheet1[Bed_Occupancy])
```

---

## 📈 Key Insights the Dashboard Surfaces

- **Billing vs. Insurance gap** — the column chart side-by-side instantly shows which diagnoses have high out-of-pocket costs for patients, signalling where insurance coverage is weakest
- **Doctor workload funnel** — ranks doctors by patient count, helping management spot overburdened or underutilised staff
- **Admissions trend line** — identifies seasonal spikes in patient volume (e.g., flu season, monsoon diseases)
- **Follow-up date distribution** — helps scheduling teams anticipate high-demand follow-up periods and prevent appointment bottlenecks
- **Q&A visual** — empowers non-technical hospital administrators to answer ad-hoc questions without needing a data analyst

---

## 📸 Dashboard Screenshot


![Hospital Dashboard] <img width="1920" height="968" alt="hospital_dashboard" src="https://github.com/user-attachments/assets/ba5099a6-a7af-4941-aea4-4f01a2f52a1b" />


---

## 🚀 How to Open

1. Download `Hospital_Dashboard.pbit`
2. Open with **Power BI Desktop** (free — [download here](https://powerbi.microsoft.com/en-us/desktop/))
3. `.pbit` is a **Power BI Template** file — when opened, it may prompt you to load your own data source. If so, point it to the hospital dataset CSV
4. All visuals, measures, and layout are pre-built — just connect the data and the dashboard populates automatically

> ℹ️ **What is a `.pbit` file?** A Power BI Template (`.pbit`) contains the report layout, data model, and DAX measures — but not the data itself. This makes it reusable: connect any compatible dataset and the dashboard works instantly.

---

## 📂 Project Structure

```
hospital-dashboard/
├── Hospital_Dashboard.pbit         ← Power BI Template file
├── images/
│   └── hospital_dashboard.png      ← Dashboard screenshot
└── README.md
```

---

## 💡 What I Learned

- Building a **single-page, high-density dashboard** that answers multiple business questions without overwhelming the user
- Using **`DATEDIFF()`** in DAX to calculate Length of Stay dynamically from admit and discharge dates
- Implementing the **Q&A Visual** to enable natural language querying — useful for non-technical hospital staff
- Structuring **billing vs. insurance** side-by-side comparison to surface financial coverage gaps
- Working with a `.pbit` template format — understanding the difference between `.pbix` (with data) and `.pbit` (portable template)
- Designing a **funnel chart** to rank doctor workload in a visually intuitive way

---

## 🙋 About Me

Made by **[Abhishek Jain](https://github.com/abhishekjain2004)**  
Aspiring Data Analyst | PG in Data Science & Analytics with Gen AI @ Imarticus Learning  
📧 abhishek2004.jain@gmail.com · [LinkedIn]www.linkedin.com/in/abhishek-jain-297014277
