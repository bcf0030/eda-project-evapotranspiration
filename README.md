# EDA Project – Evapotranspiration Analysis (AmeriFlux + OpenET)
*INSY 6500 – Modern Tools for Data Analysis and Modeling*  
**Benjamin Ferguson & Stephanie Pinto**

## Project Overview
This project explores monthly ecohydrological dynamics at the **AmeriFlux US-SRG (Santa Rita Grassland)** site by combining in-situ AmeriFlux observations with satellite-derived evapotranspiration (ET) estimates from **OpenET**.

The goal was to clean and merge the datasets, conduct exploratory data analysis, and build an **interactive Streamlit dashboard** to visualize ET drivers and relationships among climate variables.

## Repository Structure
project-evapotranspiration/
│
├── Cleaning_data.ipynb # Data cleaning, unit adjustments, merging datasets
├── data_exploration.ipynb # Exploratory analysis and visualizations
├── app.py # Streamlit dashboard interface
├── core.py # Plotting functions used by the dashboard
├── data/
│ ├── raw/ # Original AmeriFlux + OpenET datasets
│ └── processed/ # Cleaned and merged dataset (pickle file)
└── README.md

## Data Processing Steps
Data preparation included:

- Importing raw AmeriFlux CSVs and OpenET ET estimates  
- Filtering both datasets to their overlapping time window  
- Renaming and standardizing variable labels  
- Adjusting units for consistency  
- Computing additional variables (e.g., **relative humidity** from VPD and temperature)  
- Merging AmeriFlux + OpenET using a shared `Date` column  
- Exporting the final cleaned dataset as a `.pkl` file  

## Exploratory Data Analysis (EDA)

The analysis focused on:

- Monthly temporal patterns of key ecohydrological variables  
- Pearson correlation structure across all variables  
- Conditions associated with **peak ET**  
- Scatterplots examining relationships such as:
  - ET vs Air Temperature  
  - ET vs Rainfall  
  - ET vs Wind Speed  
  - ET vs Soil Moisture  

### **Key Findings**
- ET is strongly and positively correlated with:  
  - **Air Temperature (r ≈ 0.67)**  
  - **Rainfall (r ≈ 0.56)**  
  - **Relative Humidity (r ≈ 0.48)**  
- The strongest negative correlation is with:  
  - **Wind Speed (r ≈ –0.56)**  
- **Peak ET occurs when:**  
  - High temperature (energy availability)  
  - High rainfall (water availability)  
  - Low wind speed (reduced aerodynamic limitations)  
- **Low ET occurs when:**  
  - Low temperature **or** low rainfall **or** high wind — any of these factors can restrict ET.  
- Soil moisture shows weak direct correlations at a monthly time scale.

## Streamlit Dashboard
An interactive dashboard was developed to provide:

- Dual-axis time-series visualization of any two selected variables  
- Correlation-based scatterplots  
- Display of the full Pearson correlation matrix  
- Year-range filtering for dynamic exploration  

The dashboard is organized into:

- `app.py` — user interface and layout  
- `core.py` — modular plotting functions used throughout the app  

https://eda-project-evapotranspiration.streamlit.app/

## Tools & Technologies
- Python 3.x  
- Pandas, NumPy, Matplotlib, Seaborn  
- Streamlit  
- JupyterLab  
- Git/GitHub  

## Course Information
*INSY 6500 – Modern Tools for Data Analysis and Modeling*  
Auburn University  
Department of Industrial & Systems Engineering  
Instructor: Dr. Dan O'Leary  

