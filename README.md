# COVID-19 Time-Series Forecasting & Interactive Analytics Pipeline

## Project Overview
This repository features an end-to-end data analytics and predictive modeling pipeline designed to ingest multi-variant tracking data, reconstruct historical baselines, and project upcoming case trajectories. 

By leveraging **Meta Prophet** for additive regression modeling and **Plotly** for interactive data visualization, the project shifts standard exploratory analysis into an actionable, quantitative forecasting tool.

### Core Technical Objectives:
*   **Production-Grade Ingestion:** Building a structural pipeline using relative pathing and robust data validation with `pandas`.
*   **Time-Series Forecasting:** Customizing an additive time-series regression framework configured with a 95% uncertainty interval horizon.
*   **Performance Accountability:** Evaluating the model using continuous regression metrics (`MAE`, `RMSE`, `MAPE`) to ensure mathematical validation.
*   **Decomposition Analysis:** Isolating underlying structural data variables (macro trends vs. weekly seasonality) to replace static feature importance metrics.

---

## Repository Structure
```text
├── covid_19_forecasting.csv                   # Granular time-series tracking source dataset
├── covid19-time-series-forecasting.ipynb      # Core execution Jupyter Notebook 
└── README.md                                  # Project documentation and performance report
```
## Technical Stack & Dependencies
- Data Manipulation & Quality Control: pandas, numpy
- Predictive Engine: prophet (Meta)
- Interactive Visualizations: plotly (Graph Objects & Express)
- Model Evaluation Evaluation: scikit-learn

## Pipeline Workflow
- 1. Data Processing & Structural Invariant Control
Granular daily global arrays are checked for chronological sorted order, structural null variables are evaluated, and columns are explicitly aggregated programmatically via a global system macro-trend layout using:
```df_global = df_raw.groupby('Date')[['Confirmed', 'Deaths', 'Recovered', 'Active']].sum().reset_index()```

- 2. Time-Series Structural Alignment
Features are mapped to match structural expectations required by the forecasting engine architecture:
ds: Chronological temporal datetime tracking vector.
y: Target continuous numeric scalar monitoring cumulative values under prediction.

- 3. Quantitative Performance Results
Unlike basic classification models that use confusion matrices, this continuous time-series regression pipeline undergoes optimization validation using regression metrics:
```     Metric                                       Analytical Value
Mean Absolute Error (MAE)           Quantifies average case trajectory deviations.
Root Mean Squared Error (RMSE)      Highlights variance and penalizes large outlier errors.
Mean Absolute Pct Error (MAPE)      Provides a normalized percentage error scale for operational reliability.```

- 4. Component Analysis (Feature Importance Equivalent)
Instead of relying on standard classification feature ranking metrics, the predictive model’s insights are extracted by breaking down the time series into independent components:
Macro-Trend Continuum: Tracks long-term distribution velocity across the overarching timeline.
Weekly Seasonality Effects: Maps statistical anomalies and case acceleration tracking specific days of the week.
