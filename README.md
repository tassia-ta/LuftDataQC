| [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) | [![Python](https://img.shields.io/badge/Python-3.10+-black.svg)](https://www.python.org/) | [![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-red.svg)](https://jupyter.org/) | [![SQLite](https://img.shields.io/badge/Database-SQLite-darkblue.svg)](https://www.sqlite.org/index.html) | [![Pandas](https://img.shields.io/badge/Data-Pandas-purple.svg)](https://pandas.pydata.org/) | [![NumPy](https://img.shields.io/badge/Math-NumPy-blue.svg)](https://numpy.org/) | [![Matplotlib](https://img.shields.io/badge/Plots-Matplotlib-darkgreen.svg)](https://matplotlib.org/) | [![Seaborn](https://img.shields.io/badge/Plots-Seaborn-teal.svg)](https://seaborn.pydata.org/) |
|---|---|---|---|---|---|---|---|

| [![Plotly](https://img.shields.io/badge/Plots-Plotly-darkorange.svg)](https://plotly.com/python/) | [![SciPy](https://img.shields.io/badge/Stats-SciPy-navy.svg)](https://scipy.org/) | [![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-orange.svg)](https://scikit-learn.org/stable/) | [![SQLAlchemy](https://img.shields.io/badge/ORM-SQLAlchemy-brown.svg)](https://www.sqlalchemy.org/) | [![Requests](https://img.shields.io/badge/HTTP-Requests-darkred.svg)](https://docs.python-requests.org/) | [![JSON](https://img.shields.io/badge/Data-JSON-grey.svg)](https://www.json.org/) | [![Pathlib](https://img.shields.io/badge/FS-Pathlib-black.svg)](https://docs.python.org/3/library/pathlib.html) |  |
|---|---|---|---|---|---|---|---|


> This README is bilingual. The first part is in **English**, and the **Norwegian version** can be found further down.

## (EN) - LuftDataQC: Air Quality Data Analysis and Anomaly Detection  

### A Data Science Pipeline for Environmental Monitoring and Quality Assurance

##  Project Overview

Air pollution is a global challenge with direct health, economic, and environmental impacts.
This project **LuftDataQC** demonstrates how modern **Data Science and Machine Learning techniques (ML)** can be applied to real-world **air quality monitoring**.

Using PM2.5 concentration data from **NILU** (Norwegian Institute for Air Research), this pipeline:

* Collects and stores raw environmental data in a **structured database**.
* Performs **QA/QC (Quality Assurance / Quality Control)** and **exploratory data analysis (EDA)**  to identify data issues.
* Engineers temporal and rolling statistical features.
* Applies **ML-based anomaly detection (IsolationForest)** to highlight unusual pollution events.

The result is a reproducible, end-to-end workflow bridging **environmental science** with **modern data engineering**

---

##  Why This Matters

* **Public Health and Policy:** Reliable air quality data informs decisions on emissions and health advisories.
* **Business Relevance:** Useful for energy, transport, and environmental consulting sectors.
* **Applied Expertise:** End-to-end capability in **data engineering**, **statistical QA/QC**, and **machine learning** for environmental analytics used here to deliver actionable insights for monitoring and policy.

---

## Technical Pipeline

**1. Data Collection and Storage**

* PM2.5 hourly data ingested from NILU Open API.
* Stored in **SQLite database** with reproducible folder structure (`/data/raw`, `/data/processed`, `/results`).

**2. Data Cleaning and Exploratory Analysis**

* Missing values, outliers, and instrument inconsistencies inspected.
* Statistical analysis (Mann–Whitney U test) to compare station distributions.
* Visual storytelling for two monitoring stations:

  * **Skøyen (urban, Oslo)**
  * **Furulund (residential)**

**3. Feature Engineering**

* Temporal features: hour, weekday, month, season.
* Rolling averages (3h, 12h, 24h) to capture pollution dynamics.

**4. Anomaly Detection**

* **Proof of Concept:** IsolationForest on raw PM2.5 values.
* **Enhanced Model:** IsolationForest with temporal features for robust anomaly detection.
* Results flag candidate episodes for **expert environmental review**.

---

##  Results and Insights

* **QA/QC Automation:** Reduces manual inspection and improves reliability of NILU monitoring data.
* **Station Comparison:** Skøyen shows higher and more variable PM2.5 levels than Furulund, reflecting traffic vs. background environment.
* **ML Contribution:** IsolationForest successfully identified atypical pollution episodes, supporting early warning systems and research.

This pipeline can be scaled into **environmental decision-support systems** for **public health, policy, and urban planning**.

---



## Technologies Used

**Languages and Libraries:** Python · Pandas · NumPy · scikit-learn · Matplotlib · Plotly

**Database:** SQLite (lightweight, portable storage for reproducible analysis)

**Workflow:** Jupyter Notebooks · Modular, auditable folder structure · Version-controlled pipeline (Git)

**Methods:**
- **Statistical QA/QC**: distribution checks, non-parametric tests
- **Feature Engineering**: temporal variables, rolling means
- **Machine Learning (unsupervised)**: IsolationForest for anomaly detection
- **Visual Analytics**: interactive and static plots to support interpretation

---
##  Project Structure 

```text
LuftDataQC/
│
├── data/
│   ├── 01_raw/                     # (not versioned) – download via NILU Open API using Notebook 1
│   └── 02_processed/               # (not versioned) – cleaned data (SQLite, recreated by Notebook 1)
│        
├── notebooks/
│   ├── 01_data_sqlite.ipynb         # Data collection and storage
│   ├── 02_exploratory_qc.ipynb      # Data cleaning and exploratory analysis
│   ├── 03_features_anomalies.ipynb  # ML pipeline (feature eng. + anomaly detection)
│   ├── 04_report.ipynb              # Final report (EN)
│   └── 05_report_norsk.ipynb        # Final report (NO)
│ 
├── results/                         # Final figures, plots, and exported files (CSV)
│ 
├── LICENSE                          # MIT License
└── README.md                        # Project description and usage guide
```
---
## Author

**Tássia Tavares** – Data Scientist | Environmental Scientist | Biotechnologist

 **Academic Background:**  
  - BSc in Chemistry, MSc in Science, PhD in Science (Environmental and Biotechnological focus).  
  - Postdoctoral research in Biochemistry and Biotechnological Processes.  
  - All diplomas officially recognized in Norway.

 **Professional Strengths:**  
  - Specialist in **interdisciplinary projects** linking environment, biotechnology, and data.  
  - Experienced in **complex datasets, statistical analysis, and machine learning pipelines**.  

**Data Science:**  
  - Certified in **Python for Data Science, AI and Development (IBM)**.  
  - Delivers end-to-end, reproducible data products from ingestion and quality assurance to feature engineering, ML modeling, and decision ready reporting, applied to complex, real world, science-driven problems.
    
## Contact

Based in Norway – open to **Data Science and AI roles in environmental, health, biotechnology (life sciences), and in applied analytics sectors**


  [![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-blue.svg?logo=linkedin)](https://www.linkedin.com/in/tassia-/)  

---

## Navigation Links

- [Notebook 1 – Data Collection, Inspection and Storage](notebooks/01_data_sqlite.ipynb)  
- [Notebook 2 – Exploratory Analysis and Quality Checks](notebooks/02_exploratory_qc.ipynb)  
- [Notebook 3 – Feature Engineering and Anomaly Detection](notebooks/03_features_anomalies.ipynb)  
- [Notebook 4 – Summary Report (EN)](notebooks/04_report.ipynb)  
- [Notebook 5 – Sammendragsrapport (NO)](notebooks/05_report_norsk.ipynb)
_____

## License  

This project is licensed under the terms of the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

-----


# (NO) – LuftDataQC: Luftkvalitetsanalyse og anomalideteksjon

### En data science-pipeline for miljøovervåking og kvalitetssikring

---

## Prosjektoversikt

Luftforurensning er en global utfordring med direkte helse-, økonomiske og miljømessige konsekvenser.
Dette prosjektet **LuftDataQC** demonstrerer hvordan moderne **data science** og **maskinlæring (ML)** kan anvendes på reell **luftkvalitetsovervåking**.

Med utgangspunkt i PM2.5-konsentrasjonsdata fra **NILU** (Norwegian Institute for Air Research) viser denne pipelinen hvordan man:

* Samler og lagrer rå miljødata i en **strukturert database**.
* Utfører **QA/QC (kvalitetssikring/kvalitetkontroll)** og **EDA (utforskende dataanalyse)** for å identifisere dataproblemer.
* Konstruerer tidsbaserte og glidende statistiske **variabler (features)**.
* Bruker **ML-basert anomalideteksjon (IsolationForest)** for å fremheve uvanlige forurensningshendelser.

Resultatet er en reproduserbar, ende-til-ende arbeidsflyt som bygger bro mellom **miljøvitenskap** og moderne **data engineering**.

---

## Hvorfor dette er viktig

* **Folkehelse og politikk:** Pålitelige luftkvalitetsdata informerer beslutninger om utslipp og helseanbefalinger.
* **Forretningsrelevans:** Nyttig for energi-, transport- og miljøkonsulentsektorer.
* **Anvendt kompetanse:** Ende-til-ende ferdigheter i **data engineering**, **statistisk QA/QC** og **maskinlæring** for miljøanalyse — brukt her til å levere innsikt for overvåking og policy.

---

## Teknisk pipeline

**1. Datainnsamling og lagring**

* Timeoppløste PM2.5-data hentet fra **NILU Open API**.
* Lagret i **SQLite-database** med reproduserbar mappestruktur (`/data/raw`, `/data/processed`, `/results`).

**2. Datavask og utforskende analyse**

* Gjennomgang av manglende verdier, avvik (outliers) og instrumentinkonsistenser.
* Statistisk analyse (**Mann–Whitney U-test**) for å sammenligne stasjonsfordelinger.
* Visuell formidling for to målestasjoner:

  * **Skøyen (urban, Oslo)**
  * **Furulund (boligområde)**

**3. Feature engineering (variabelkonstruksjon)**

* Tidsvariabler: time (på døgnet), ukedag, måned, sesong.
* Glidende gjennomsnitt (3 t, 12 t, 24 t) for å fange forurensningsdynamikk.

**4. Anomalideteksjon**

* **Proof-of-concept:** IsolationForest på rå PM2.5-verdier.
* **Utvidet modell:** IsolationForest med tidsvariabler for mer robust anomalideteksjon.
* Resultatene flagger kandidathendelser for **faglig vurdering av miljøeksperter**.

---

## Resultater og innsikter

* **Automatisert QA/QC:** Reduserer manuell inspeksjon og øker påliteligheten i NILUs overvåkingsdata.
* **Sammenligning mellom stasjoner:** Skøyen viser høyere og mer variabel PM2.5 enn Furulund, som reflekterer trafikkpåvirkning kontra bakgrunnsmiljø.
* **Bidrag fra ML:** IsolationForest identifiserte atypiske forurensningsepisoder, noe som støtter tidlig varsling og videre forskning.

Denne pipelinen kan skaleres til **beslutningsstøttesystemer** for **folkehelse, politikk og byplanlegging**.


## Teknologier brukt

**Språk og biblioteker:** Python · Pandas · NumPy · scikit-learn · Matplotlib · Plotly

**Database:** SQLite (lettvekts, portabel lagring for reproduserbar analyse)

**Arbeidsflyt:** Jupyter Notebooks · Modulær, reviderbar/sporbar mappestruktur · Versjonskontrollert pipeline (Git)

**Metoder:**

* **Statistisk QA/QC** — fordelingskontroller og ikke-parametriske tester
* **Feature engineering (variabelkonstruksjon)** — tidsvariabler og glidende gjennomsnitt
* **Maskinlæring (usupervisert)** — IsolationForest for anomalideteksjon
* **Visuell analyse** — interaktive og statiske figurer for å støtte tolkning

---

##  Prosjektstruktur

```text
LuftDataQC/
│
├── data/
│   ├── 01_raw/                  # (ikke versjonert) – lastes ned via NILU Open API med Notebook 1
│   └── 02_processed/            # (ikke versjonert) – rensede data (SQLite, gjenskapt med Notebook 1)
│        
├── notebooks/
│   ├── 01_data_sqlite.ipynb         # Datainnsamling og lagring
│   ├── 02_exploratory_qc.ipynb      # Datavask og EDA (utforskende analyse)
│   ├── 03_features_anomalies.ipynb  # ML-pipeline (variabler og anomalier)
│   ├── 04_report.ipynb              # Sammendragsrapport (EN)
│   └── 05_report_norsk.ipynb        # Sammendragsrapport (NO)
│ 
├── results/                         # Sluttfigurer, plott og eksporterte filer (CSV)
│
├── LICENSE                          # MIT-lisens
└── README.md                        # Prosjektbeskrivelse og brukerveiledning 
```

## Forfatter

**Tássia Tavares** – Data Scientist | Miljøviter | Bioteknolog

**Utdanningsbakgrunn:**

* Bachelor i kjemi, master i naturvitenskap, ph.d. i naturvitenskap (miljø- og bioteknologisk fokus).
* Postdoktor innen biokjemi og bioteknologiske prosesser.
* Alle vitnemål formelt godkjent i Norge.

**Faglige styrker:**

* Spisskompetanse i **tverrfaglige prosjekter** som kobler miljø, bioteknologi og data.
* Erfaring med **komplekse datasett, statistiske analyser og maskinlæringspipeliner**.

**Data Science:**

* Sertifisert i **Python for Data Science, AI and Development (IBM)**.
* Leverer **ende-til-ende**, reproduserbare dataprodukter – fra datainntak og **QA/QC** til feature engineering, ML-modellering og **beslutningsklar rapportering**, anvendt på komplekse, virkelighetsnære, forskningsdrevne problemstillinger.

## Kontakt

Bosatt i Norge – åpen for **Data Science- og AI-roller innen miljø, helse, bioteknologi (life sciences) og anvendt dataanalyse.**

[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-blue.svg?logo=linkedin)](https://www.linkedin.com/in/tassia-)

---

## Navigasjonslenker 

- [Notebook 1 – Data Collection, Inspection and Storage](notebooks/01_data_sqlite.ipynb)  
- [Notebook 2 – Exploratory Analysis and Quality Checks](notebooks/02_exploratory_qc.ipynb)  
- [Notebook 3 – Feature Engineering and Anomaly Detection](notebooks/03_features_anomalies.ipynb)  
- [Notebook 4 – Summary Report (EN)](notebooks/04_report.ipynb)  
- [Notebook 5 – Sammendragsrapport (NO)](notebooks/05_report_norsk.ipynb)

_____

## Lisens  

Dette prosjektet er lisensiert under vilkårene i **MIT-lisensen**.  
Se [LICENSE](LICENSE)-filen for detaljer.

