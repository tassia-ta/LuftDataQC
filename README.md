| [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) | [![Python](https://img.shields.io/badge/Python-3.10+-black.svg)](https://www.python.org/) | [![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-red.svg)](https://jupyter.org/) | [![SQLite](https://img.shields.io/badge/Database-SQLite-darkblue.svg)](https://www.sqlite.org/index.html) | [![Pandas](https://img.shields.io/badge/Data-Pandas-purple.svg)](https://pandas.pydata.org/) | [![NumPy](https://img.shields.io/badge/Math-NumPy-blue.svg)](https://numpy.org/) | [![Matplotlib](https://img.shields.io/badge/Plots-Matplotlib-darkgreen.svg)](https://matplotlib.org/) | [![Seaborn](https://img.shields.io/badge/Plots-Seaborn-teal.svg)](https://seaborn.pydata.org/) |
|---|---|---|---|---|---|---|---|

| [![Plotly](https://img.shields.io/badge/Plots-Plotly-darkorange.svg)](https://plotly.com/python/) | [![SciPy](https://img.shields.io/badge/Stats-SciPy-navy.svg)](https://scipy.org/) | [![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-orange.svg)](https://scikit-learn.org/stable/) | [![SQLAlchemy](https://img.shields.io/badge/ORM-SQLAlchemy-brown.svg)](https://www.sqlalchemy.org/) | [![Requests](https://img.shields.io/badge/HTTP-Requests-darkred.svg)](https://docs.python-requests.org/) | [![JSON](https://img.shields.io/badge/Data-JSON-grey.svg)](https://www.json.org/) | [![Pathlib](https://img.shields.io/badge/FS-Pathlib-black.svg)](https://docs.python.org/3/library/pathlib.html) |  |
|---|---|---|---|---|---|---|---|

## LuftDataQC: Air Quality Analysis and Anomaly Detection  

### A Data Science Pipeline for Environmental Monitoring and Quality Assurance

##  Project Overview

LuftDataQC demonstrates how Data Science and Machine Learning (ML) can be applied to real-world air quality monitoring using PM2.5 data from NILU (Norwegian Institute for Air Research).

The goal is to bridge environmental science with data engineering through a reproducible, end-to-end workflow that automates data ingestion, validates quality, and detects atypical pollution events.

---

## Technical Pipeline

**1. Data Ingestion (Bronze Layer)**

* PM2.5 hourly data ingested directly from NILU Open API.
* Raw data is archived in a structured SQLite database to ensure traceability.
  
**2. Cleaning & Validation (Silver Layer)**

* Inspection of missing values, outliers and instrument noise.
* Statistical validation using non-parametric tests (Mann–Whitney U) to compare urban (Skøyen) vs. residential (Furulund) stations.

**3. Feature Engineering**

* Extraction of temporal signals (hour, weekday, seasonality).
* Computation of rolling averages (3h to 24h) to smooth sensor noise and capture pollution dynamics.

**4. ML Anomaly Detection**

* Implementation of an Isolation Forest model to flag atypical pollution episodes.
* The pipeline distinguishes between regular peak patterns and actual anomalous events, providing a decision-support tool for environmental experts.

##  Project Structure 

```text
LuftDataQC/
│
├── data/
│   ├── 01_raw/                     # Original API snapshots (not versioned) 
│   └── 02_processed/               # Cleaned SQLite database (reproducible)
│        
├── notebooks/
│   ├── 01_data_sqlite.ipynb         # Data Ingestion and Database Setup
│   ├── 02_exploratory_qc.ipynb      # EDA, QA/QC and Statistical Tests
│   ├── 03_features_anomalies.ipynb  # ML Pipeline: Feature Eng. & Isolation Forest
│   ├── 04_report.ipynb              # Final Executive Report (EN)
│   └── 05_report_norsk.ipynb        # Sammendragsrapport (NO)
│ 
├── results/                         # Final Insights, Interactive Charts, and processed CSVs
│ 
├── LICENSE                          # MIT License
└── README.md                        # Project Guide
```
---

## Quick Navigation

- [Notebook 1 – Ingestion and Storage](notebooks/01_data_sqlite.ipynb)  
- [Notebook 2 – QA/QC and Exploratory Analysis](notebooks/02_exploratory_qc.ipynb)  
- [Notebook 3 – ML and Anomaly Detection](notebooks/03_features_anomalies.ipynb)  
- [Notebook 4 – Summary Report (EN)](notebooks/04_report.ipynb)  
- [Notebook 5 – Sammendragsrapport (NO)](notebooks/05_report_norsk.ipynb)
_____

## License  

This project is licensed under the terms of the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

-----
