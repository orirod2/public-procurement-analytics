**English** | [Español](README.es.md)

# Elipsis: Risk Indicators in Colombian Public Procurement
## Description
Public procurement represents a significant channel through which governments allocate public resources. However, weaknesses in procurement processes, limited competition, supplier concentration, and recurring contractual patterns may create conditions associated with inefficient resource allocation and potential risks of public resource loss.

This project aims to identify and analyze risk indicators associated with the potential loss of public resources in Colombian public procurement, using open data from SECOP II, the country's electronic public procurement platform.

The research will examine contractual patterns across public entities and suppliers, focusing on variables such as contract values, procurement modalities, supplier participation, recurring contractual relationships, geographical distribution, and temporal trends. Through data extraction, processing, exploratory data analysis, statistical methods, and visualization, the study seeks to identify patterns that may warrant further investigation. Depending on data availability and analytical relevance, network analysis, clustering, and anomaly detection techniques may also be incorporated.

## Project Status
In development: data exploration

## Data
- Dataset Name: SECOP II – Electronic Contracts  
- Data Provider: National Public Procurement Agency – Colombia Compra Eficiente, Bogotá D.C.  
- Dataset Owner: Datos Abiertos CCE  
- Last Data Update: November 21, 2026  
- Last Metadata Update: October 25, 2026  
- Creation Date: September 30, 2019  
- Number of Records: 5.73 million (rows)  
- Number of Variables: 95 (columns)  
- Dataset Link: https://www.datos.gov.co/Gastos-Gubernamentales/SECOP-II-Contratos-Electr-nicos/jbjy-vk9h
- Source Website: https://www.colombiacompra.gov.co/

## Research Questions
1. Which contracts show risk signals of public resource loss, such as unjustified advance payments or expired contracts that were never completed or settled?
2. Which public entities and contractors concentrate the most risk-flagged contracts, and how much public money do they represent?
3. Are there patterns of favoritism or poor planning, such as contracts concentrated in a few suppliers, contract splitting, or disproportionate extensions?

## Project Structure
```
public-procurement-analytics/
├── 00_project_management/   # Project planning and log
├── 01_data_sources/         # Data source documentation
├── 02_data/
│   ├── raw/                 # Original downloaded data (not uploaded to GitHub)
│   └── processed/           # Cleaned and transformed data (not uploaded to GitHub)
├── 03_notebooks/            # Exploration and analysis notebooks
├── 04_src/                  # Reusable code (functions and scripts)
├── 05_visualizations/       # Charts and figures
├── 06_reports/              # Final reports and results
├── requirements.txt         # Libraries required to run the project
└── README.md
```

## Tools
- **Python 3.14**
- **httpx**: data retrieval from the datos.gov.co API
- **Polars**: large-scale data manipulation and cleaning
- **DuckDB**: SQL queries on large files
- **PyArrow**: efficient storage in Parquet format
- **Matplotlib**: visualizations
- **Jupyter Notebooks**: analysis exploration and documentation
- **Git & GitHub**: version control

## Progress
- [x] Development environment and project structure setup
- [x] Dataset metadata exploration (95 columns)
- [x] Data dictionary with 47 key variables in 5 groups: entity, contract, dates, suppliers, and budget information
- [x] Draft of risk indicators
- [x] First API connection to retrieve contracts
- [ ] Sample download and data quality assessment
- [ ] Data cleaning and transformation
- [ ] Risk indicator calculation
- [ ] Interactive dashboard with results

## Disclaimer

This project identifies **risk indicators** based on public data. A risk signal **is not evidence of corruption or wrongdoing**: it may result from data entry errors, incomplete records, or justified circumstances. The results aim to highlight cases that merit further review, not to accuse any entity or individual. To protect privacy, names and ID numbers of private individuals are not published.