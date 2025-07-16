# 🏥 Hospital Patient Arrival Forecasting & Prescriptive Staffing Optimization

This project was developed while volunteering for an *Emergency Room (ER) department at a hospital in England. It combines **time series forecasting* and *prescriptive analytics* to:

* *Predict hourly patient arrival volumes*, and
* *Recommend the optimal number of doctors* per hour to ensure timely care and efficient resource allocation.

---

## 📌 Objectives

* Forecast patient arrival trends on an hourly basis.
* Translate predictions into *prescriptive staffing recommendations*.
* Ensure operational goals are met:

  * *90% of patients* seen within *2 hours*.
  * *100% of patients* seen within *3 hours*.
* Support ER administrators with *data-driven dashboards*.

---

## 🧠 Problem Framing

Accurately forecasting patient arrivals is crucial for:

* Ensuring sufficient staffing levels,
* Reducing wait times,
* Improving patient outcomes, and
* Avoiding overuse of limited resources.

This project integrates machine learning and domain-specific business rules to bridge data and hospital planning needs.

---

## 🔢 Methodology

### 1. *Feature Engineering*

* Time-based features: hour, day of week, weekend, holiday flags.
* Lag features: past 7-day same-hour arrival values.
* Rolling statistics: hourly averages over prior weeks.
* Cyclical encoding for time-of-day and day-of-week.

### 2. *Forecasting Models*

* *Random Forest*
* *XGBoost*
* *LightGBM*
* *GRU (PyTorch)*

Models were trained on historical ER arrival logs to predict hourly arrivals with high accuracy.

### 3. *Prescriptive Logic*

* Assumption: *1 doctor can treat 0.5 patients per hour*.
* For each hour, compute the number of doctors required such that:

  * *90%* of patients are seen within *2 hours*.
  * *100%* are seen within *3 hours*.
* Use the *maximum of both values* as the final doctor count per hour.

### 4. *Visualization*

* Built *Power BI dashboards* to visualize:

  * Arrival patterns
  * Predicted demand
  * Hourly staffing needs

---

## 📊 Key Insights

* Weekday and hourly patterns show consistent peak times (late mornings and early evenings).
* Forecasting performance improved significantly with lag and rolling features.
* GRU provided superior temporal sensitivity but simpler models were also competitive.
* Prescriptive model recommendations closely aligned with current hospital staffing in high-traffic periods.

---

## 💡 Future Work

* **Remove incident_admincode_1** feature (potential data leakage) and retrain models.
* Test additional models (e.g., Prophet, SARIMA, temporal fusion transformers).
* Integrate real-time updates for dynamic staffing adjustments.
* Incorporate external factors (weather, holidays, local events).
* Collect feedback from hospital admins to refine prescriptive assumptions.

---

## 🛠 Tools & Technologies

* *Languages:* Python
* *Libraries:* Pandas, NumPy, Scikit-learn, LightGBM, XGBoost, PyTorch
* *Visualization:* Power BI
* *Environment:* Jupyter Notebook / Google Colab

---

## 📁 Repository Structure


hospital_patient_arrival_pred_prescript_visual/

<br>├── HospitalData_Sam.csv                         # Cleaned and transformed datasets
<br>├── HospitalArrivalPrediction_10.ipynb           # Forecasting, evaluation, and prescriptive modeling
<br>├── Hospital_Data_V03.pbix                       # Power BI dashboard file
<br>├── README.md                                    # Project documentation


---

## 🙏 Acknowledgements

This project was made possible through a volunteer collaboration with an *ER department in England*. Special thanks to the hospital team for sharing operational insight and supporting the use of data for healthcare optimization.
