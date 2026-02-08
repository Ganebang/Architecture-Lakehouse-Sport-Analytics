
# Architecture Lakehouse Sport Analytics

## Project Overview
This project implements a Lakehouse architecture for football (soccer) match analytics using web scraping, PySpark, and Delta Lake. The pipeline ingests raw match data from Transfermarkt, processes it through Bronze, Silver, and Gold layers, and enables advanced analytics and visualization.

## Pipeline Structure

1. **00_Web_Scraping_Ingestion.ipynb**
	- Scrapes match data for major European leagues from Transfermarkt.
	- Stores raw data in Delta format, partitioned by season.
	- Modular code: configuration, helpers, scraping, and main loop are separated for clarity.

2. **01_Raw_To_Bronze_Transformations.ipynb**
	- Reads raw Delta files and loads them into the Bronze table.
	- Performs basic schema enforcement and data quality checks.

3. **02_Bronze_To_Silver_Transformations.ipynb**
	- Cleans and transforms Bronze data (type casting, date parsing, filtering).
	- Stores results in the Silver table, partitioned by season.

4. **03_Silver_To_Gold_Transformations.ipynb**
	- Aggregates and enriches Silver data (team stats, rankings).
	- Produces Gold tables for advanced analytics.

5. **04_Exploratory_Data_Analysis.ipynb**
	- Loads Gold data for visualization and exploratory analysis.
	- Example: league champions, best attacking teams, title counts.

## How to Run

1. **Environment**: Databricks or local PySpark with Delta Lake support.
2. **Order**: Run notebooks in order (00 → 04).
3. **Data Output**: All intermediate and final tables are stored in Delta format for efficient querying.

## Key Features
- Modular, well-commented code for maintainability.
- Robust scraping with polite delays and error handling.
- Follows Lakehouse best practices: Raw → Bronze → Silver → Gold.
- Ready for extension to more leagues or analytics.

## Requirements
- Python 3.8+
- PySpark
- pandas
- requests
- beautifulsoup4
- Delta Lake (Databricks or compatible local setup)

## Authors
- [Your Name]

---

For questions or contributions, please open an issue or pull request.
