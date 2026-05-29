# Titanic Passenger Survival Analysis

An end-to-end data analytics project using Python for data preprocessing, MySQL for database querying, and Power BI for creating an interactive dashboard to explore patterns behind passenger demographics, fare classes, and survival rates.

---

## Project Objectives
* **Demographic Disparities:** Checking how survival rates differed between genders and different age groups.
* **Socio-Economic Impact:** Evaluating how ticket pricing and passenger class rankings directly correlated with survival.
* **Family Structure Metrics:** Tracking how traveling with family members (siblings or spouses) impacted a passenger's outcome.
* **Logistics & Embarkation:** Mapping passenger volume distributions back to their primary ports of embarkation.

---

## Tools Used
* **Python (Pandas, NumPy):** Data cleaning and handling missing values.
* **SQLAlchemy:** Programmatically exporting the cleaned data from Python into MySQL.
* **MySQL:** Data querying, aggregations, and ranking functions.
* **Power BI:** Data visualization and KPI dashboard building.

---

## Data Preprocessing & Cleaning (Python)
Before analyzing the data, the raw dataset was processed inside the `data preprocessing.ipynb` notebook:
* **Handling Missing Values:** Filled missing age values using the global median, imputed missing embarkation locations with 'S', and marked missing cabin data as 'Unknown'.
* **Removing Unnecessary Columns:** Dropped the highly inconsistent `Ticket` column to keep the data clean and optimize database space.
* **Database Export:** Programmatically sent the cleaned data directly into MySQL using SQLAlchemy.

---

## Data Analysis & Insights (SQL)
The queries inside your SQL script extract key passenger metrics:
* **Core Aggregations:** Calculated total passengers, total survivors, and overall mortality numbers.
* **Gender & Port Distributions:** Grouped records to isolate survival and mortality trends across male and female paths alongside port volumes.
* **Class Survival Ratios:** Calculated percentage-based survival thresholds for each individual ticket class.
* **Passenger Ranking:** Used window functions (`RANK() OVER`) to rank passenger fares within each passenger class.
* **Age Binning:** Used `CASE WHEN` logic to split passengers into demographic categories (Child, Teen, Adult, Senior) to evaluate their unique survival rates.

---

## Interactive Dashboard Preview
The final layer of the project is an interactive Power BI dashboard that monitors survival KPIs, passenger demographics, and class distributions.

<img width="1308" height="734" alt="image" src="https://github.com/user-attachments/assets/327f898f-01ec-466f-8c0b-16a0078581d8" />


---

## Repository Files
* `titanic.csv`: The raw historical passenger dataset.
* `clean_dataset.csv`: The final processed dataset exported after Python cleaning.
* `data preprocessing.ipynb`: Jupyter notebook covering data cleaning and the database export pipeline.
* `SQL Queries.sql`: SQL script containing all the analytical database queries.

---

## How to Run This Project
1. Open and run `data preprocessing.ipynb` to clean the data and load it into your local MySQL server.
2. Execute the queries inside your SQL script to view the aggregated passenger metrics.
3. Open your Power BI dashboard file in Power BI Desktop to explore the visual charts and live filters.
