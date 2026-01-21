#  Emergency Department Wait Time Analytics & Explainable ML

## Project Overview
This project analyzes **Emergency Department (ED) wait times** to identify congestion patterns, operational bottlenecks, and patient flow issues. It extends traditional analytics with **machine learning and explainable AI (SHAP)** to predict wait times and evaluate how staffing levels and bed availability impact delays.

The goal is to demonstrate **end-to-end healthcare analytics**:
- Descriptive analytics (EDA)
- Operational dashboards (Tableau)
- Predictive modeling (ML)
- Explainable AI (SHAP)
- Decision-support insights for hospital operations

---

## Business / Clinical Problem
Prolonged ED wait times:
- Increase clinical risk
- Reduce patient satisfaction
- Signal staffing and capacity constraints

Key questions addressed:
- How long do patients wait on average?
- Which patient groups wait the longest?
- When does congestion peak?
- Can we **predict wait times at arrival**?
- How do **staffing levels and bed occupancy** influence delays?

---

## Dataset Description
This project uses simulated ED operations data (no real patient data).

### Core Fields
| Column | Description |
|------|------------|
| `arrival_time` | Date & time of ED arrival |
| `arrival_hour` | Hour of arrival (0–23) |
| `arrival_day` | Day of week |
| `triage_level` | Critical / Urgent / Non-Urgent |
| `wait_time_minutes` | Actual ED wait time |
| `outcome` | Admitted or Discharged |

### Operational Features (Added)
| Column | Description |
|------|------------|
| `staff_on_duty` | ED staff available at arrival |
| `beds_available` | Available ED beds |
| `beds_occupied` | Occupied ED beds |
| `bed_occupancy_rate` | Beds occupied ÷ available |

### ML Output
| Column | Description |
|------|------------|
| `pred_wait_minutes` | Predicted ED wait time (ML) |

---

## Tools & Technologies
- **Python**
  - Pandas, NumPy
  - scikit-learn
  - SHAP (Explainable AI)
- **Tableau Public**
  - Operational & ML dashboards
- **GitHub**
  - Version control & documentation

---

## Exploratory Data Analysis (EDA) Insights
- Average ED wait time is **~127 minutes**
- **Non-urgent patients wait the longest**, consistent with triage prioritization
- ED congestion **peaks around 11:00**, indicating late-morning capacity strain

These findings highlight **time-driven congestion rather than random delays**.

---

##  Tableau Dashboards
Two dashboards were built:

### 1️ ED Operations Dashboard
- Average ED wait time KPI
- Wait time by triage level
- Wait time by hour of day (peak at 11:00)
- Filters for triage level and day of week

### 2️ ML Prediction Dashboard
- Actual vs predicted ED wait times
- Hourly congestion: actual vs predicted
- Predicted wait time vs staffing levels
- Predicted wait time vs bed occupancy

 **Tableau Dashboard Link:**  
 https://public.tableau.com/app/profile/stephen.sefa/viz/EmergencyDepartmentWaitTimeAnalysis/Dashboard1?publish=yes
https://public.tableau.com/app/profile/stephen.sefa/viz/EmergencyDepartmentWaitTimeML/EmergencyDepartmentWaitTime?publish=yes

---

##  Machine Learning: Wait Time Prediction (Regression)

### Objective
Predict ED wait time (minutes) at patient arrival to support proactive operational decisions.

### Model
- **Random Forest Regressor**
- Evaluated using **Mean Absolute Error (MAE)**

### Features Used
- Arrival hour
- Day of week
- Triage level
- Staff on duty
- Bed occupancy rate

### Performance
- **MAE with operational features: 58.01 minutes**

Including staffing and bed availability **significantly improved accuracy** and made predictions operationally actionable.

---

## Explainable AI with SHAP

SHAP (SHapley Additive exPlanations) was used to interpret the ML model.

### Key SHAP Findings
- **Arrival hour** is the strongest driver of longer waits
- **Non-urgent triage** increases predicted wait times
- **Lower staffing levels** increase predicted delays
- **Higher bed occupancy** significantly raises wait times

SHAP confirms that **ED wait times are driven by operational capacity constraints**, not just patient mix.

SHAP visualizations are included in the repository to support transparency and trust.

---

## Key Takeaways
- ED congestion is **time-driven**, peaking late morning
- Triage prioritization works clinically, but non-urgent demand contributes to crowding
- Staffing levels and bed availability are **critical levers** for reducing delays
- Explainable ML bridges analytics and real hospital decision-making

---

## Future Enhancements
- Incorporate real staffing schedules and nurse-to-patient ratios
- Add queue length and arrival rate features
- Build a long-wait risk classifier (≥120 minutes)
- Deploy what-if staffing simulations in Tableau

---

## Author
**Stephen Sefa**  
Aspiring Data Analyst | Healthcare Analytics  
Python • Tableau • Machine Learning • Explainable AI
