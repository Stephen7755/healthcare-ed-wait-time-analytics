# Emergency Department Wait Time Analysis (Analytics + ML)

## Project Overview
This project analyzes **Emergency Department (ED) wait times** to identify congestion patterns, operational bottlenecks, 
and patient flow issues. It also includes a **machine learning model** to predict expected wait times based on arrival characteristics.

The goal is to support **ED operations, staffing decisions, and patient experience improvements** using data-driven insights.

------------

## Business / Clinical Problem
Long ED wait times can:
- Increase clinical risk
- Reduce patient satisfaction
- Signal staffing or capacity issues

Key questions addressed:
- How long do patients wait on average?
- Which patients wait the longest?
- When does ED congestion peak?
- Can we predict wait times at arrival?

-------------

## Dataset Description
Simulated ED operations data (no real patient data).

| Column | Description |
|------|------------|
| `patient_id` | Unique ED patient ID |
| `arrival_time` | Date & time of arrival |
| `arrival_hour` | Hour of arrival (0–23) |
| `arrival_day` | Day of week |
| `triage_level` | Critical / Urgent / Non-Urgent |
| `wait_time_minutes` | ED wait time |
| `outcome` | Admitted or Discharged |

------------------

## Tools Used
- **Python**
  - Pandas, NumPy
  - scikit-learn
- **Tableau Public**
  - Operational dashboards
  - Time-based analysis
- **GitHub**
  - Documentation and version control

------------------------

## Key Analytics Insights
- Average ED wait time is **~127 minutes**
- **Non-urgent patients** experience the longest waits
- ED congestion **peaks around 11:00**
- Triage prioritization functions correctly, but demand exceeds capacity at peak hours

----------------------------

## Machine Learning: Wait Time Prediction (Regression)

### Objective
Predict expected ED wait time (in minutes) at patient arrival.

### Features Used
- Arrival hour
- Day of week
- Triage level

### Model
- Random Forest Regressor
- Evaluated using **Mean Absolute Error (MAE)** in minutes

### Use Case
- Early identification of long waits
- Staffing and load-balancing support
- Real-time decision assistance for ED managers

-----------------

## Tableau Dashboard
Interactive dashboard visualizing:
- Average ED wait time KPI
- Wait time by triage level
- Wait time by hour of day (peak at 11:00)
- Filters for triage and day of week

 **Tableau Dashboard:**  
https://public.tableau.com/app/profile/stephen.sefa/viz/EmergencyDepartmentWaitTimeAnalysis/Dashboard1?publish=yes

--------------------

## Future Enhancements
- Include staffing levels and bed availability
- Add queue-length features
- Deploy long-wait risk classifier
- Integrate predictions directly into Tableau

----------------------

## Author
**Stephen Sefa**  
Aspiring Data Analyst | Healthcare Analytics  
Python • Tableau • Machine Learning
