# 📊 COVID-19 Time-Series Forecasting & Interactive Analytics Pipeline

## 🎯 Project Overview
This repository features an end-to-end data analytics and predictive modeling pipeline designed to ingest multi-variant tracking data, reconstruct historical baselines, and project upcoming case trajectories. 

By leveraging **Meta Prophet** for additive regression modeling and **Plotly** for interactive data visualization, the project shifts standard exploratory analysis into an actionable, quantitative forecasting tool.

### 🚀 Core Technical Objectives:
* **🛠️ Production-Grade Ingestion:** Building a structural pipeline using relative pathing and robust data validation with `pandas`.
* **📈 Time-Series Forecasting:** Customizing an additive time-series regression framework configured with a 95% uncertainty interval horizon.
* **📐 Performance Accountability:** Evaluating the model using continuous regression metrics (`MAE`, `RMSE`, `MAPE`) to ensure mathematical validation.
* **🧩 Decomposition Analysis:** Isolating underlying structural data variables (macro trends vs. weekly seasonality) to replace static feature importance metrics.

---

## 📂 Repository Structure
```text
├── covid_19_forecasting.csv                   # Granular time-series tracking source dataset
├── covid19-time-series-forecasting.ipynb      # Core execution Jupyter Notebook 
└── README.md                                  # Project documentation and performance report
```
## 💻 Technical Stack & Dependencies
**🎛️ Data Manipulation & Quality Control:** pandas, numpy
**🔮 Predictive Engine:** prophet (Meta)
**📊 Interactive Visualizations:** plotly (Graph Objects & Express)

**🧪 Model Evaluation:** scikit-learn

## 🔄 Pipeline Workflow
**1. ⚙️ Data Processing & Structural Invariant Control**
Granular daily global arrays are checked for chronological sorted order, structural null variables are evaluated, and columns are explicitly aggregated programmatically via a global system macro-trend layout using:
```df_global = df_raw.groupby('Date')[['Confirmed', 'Deaths', 'Recovered', 'Active']].sum().reset_index()
```
**2. 🔀 Time-Series Structural Alignment**
Features are mapped to match structural expectations required by the forecasting engine architecture:
- ds: Chronological temporal datetime tracking vector.
- y: Target continuous numeric scalar monitoring cumulative values under prediction.
- 
**3. 📉 Quantitative Performance Results**
Unlike basic classification models that use confusion matrices, this continuous time-series regression pipeline undergoes optimization validation using regression metrics:
```
Metric                                 📝 Analytical Value
Mean Absolute Error (MAE)	             Quantifies average case trajectory deviations.
Root Mean Squared Error (RMSE)	       Highlights variance and penalizes large outlier errors.
Mean Absolute Pct Error (MAPE)	       Provides a normalized percentage error scale for operational reliability.
```
**4. 🗺️ Component Analysis (Feature Importance Equivalent)**
Instead of relying on standard classification feature ranking metrics, the predictive model’s insights are extracted by breaking down the time series into independent components:
- 📈 Macro-Trend Continuum: Tracks long-term distribution velocity across the overarching timeline.
- 📅 Weekly Seasonality Effects: Maps statistical anomalies and case acceleration tracking specific days of the week.

## 📌 Operational Insights & Actionable Business Takeaways
**📈 Executive Analytical Summary**
By transitioning historical descriptive data into an automated predictive model, this pipeline transforms static observations into forward-looking operational readiness metrics. The model outlines a definitive upward trajectory over the 30-day forecast horizon, bounded safely by a 95% statistical confidence interval.

## 🔍 Key Operational Insights & Business Use-Cases
**1. 🚀 Velocity & Scale Tracking (Capacity Planning)**
- The Insight: The forecasting engine projects a continuous, steady macro-growth trajectory over the upcoming 30 days.
- Business Application: For healthcare infrastructure managers, public health boards, or medical supply chains, this quantitative projection serves as an early-warning baseline tool to estimate systemic demand burdens and allocate physical assets before shortages occur.

**2. 📅 Weekly Seasonality Anomalies (Workforce Optimization)**
- The Insight: By isolating independent temporal variables through model component decomposition, a distinct weekly fluctuation pattern is revealed. Case metrics exhibit consistent localized acceleration midweek (typically peaking on Wednesdays and Thursdays), balanced by sharp drops over weekends.
- Business Application: This acts as an operational indicator of systemic reporting backlogs and weekend administrative lags rather than actual biological shifts. Resource planners, test-center managers, and hospital administrative heads can utilize this cyclical rhythm to dynamically scale staffing shifts and buffer inventory right before high-velocity tracking days.

**3. 🛡️ Risk Mitigation via Uncertainty Horizons (Stress Testing)**
- The Insight: The integration of shaded upper (yhat_upper) and lower (yhat_lower) variance boundaries provides an automated stress-testing framework.
- Business Application: Executive leadership should avoid planning operations solely around the average midpoint estimation (yhat). Instead, risk mitigation strategies (such as ICU bed reserves and emergency logistics budgeting) should be benchmarked against the Upper Boundary Limit to guarantee 95% operational resilience under worst-case surge conditions.

## 🛠️ Future Engineering Roadmap & Pipeline Scaling
To further elevate the commercial viability and analytical depth of this data asset, subsequent development sprints will focus on:
* **🧩 Exogenous Regressor Integration:** Incorporating external leading indicators—such as regional lockdown index tracking, public holiday schedules, and vaccination distribution rates—directly into the Prophet architecture as extra multi-dimensional features.
* **🗺️ Granular Spatial Clustering:** Segmenting the macro global aggregation layer into micro-tiered regional forecasting structures using geographic density clustering algorithms (like K-Means or DBSCAN).
* **🔄 Automated MLOps Pipeline:** Wrapping the notebook into a scheduled script using Apache Airflow to automatically ingest daily upstream tracking refreshes and update the interactive dashboards dynamically.

## 🏃‍♂️ How To Run and Reproduce
- Clone this repository to your local directory:
git clone [https://github.com/YOUR_USERNAME/covid19-time-series-forecasting.git](https://github.com/YOUR_USERNAME/covid19-time-series-forecasting.git)
- Ensure you have the file ```covid_19_forecasting.csv``` placed inside the root directory alongside the notebook.
- Install the required enterprise dependency frameworks:
pip install pandas numpy prophet plotly scikit-learn
- Launch your environment and run all cells in covid19-time-series-forecasting.ipynb to regenerate the interactive graphics and forecasting matrices.
