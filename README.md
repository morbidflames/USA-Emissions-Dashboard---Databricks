# Databricks CSV-to-Dashboard Project 

This project demonstrates a complete data engineering and analytics workflow using **Databricks Free Edition**, starting from a raw CSV file and ending with visualizations.  
Using raw 2023 environmental data from the EPA, we perform data ingestion, SQL-based cleaning/transformations, and build an interactive dashboard to visualize the carbon footprint across the United States.



## 🧩 Project Overview

The dashboard is built using the following layered approach:

1. **Raw CSV Data Ingestion**
2. **Data Cleaning & Transformation**
3. **Data Analysis**
4. **Dashboard & Visualizations**

Each step is implemented using Databricks notebooks and native visualization tools.



## 🛠️ Technologies Used

- Databricks (Free Edition): Primary platform for compute and storage.
- Spark SQL: Used for data manipulation, aggregation, and cleaning.
- Databricks Assistan ( Genie AI): Leveraged for debugging complex SQL queries and generating CTEs.
- Databricks Dashboards: Used to create visualizations including point maps, scatter plots, and pie charts.



## 📥 Step 1: Ingesting Raw CSV Data

### Data Source
- Source: Raw 2023 EPA Emissions CSV (approx. 3,000 rows with dozens of environmental metrics).
- Setup: Created a dedicated emissions_catalog and default schema to house the emissions_data table.
  


## 🧹 Step 2: Data Cleaning & Transformation

- The raw data contained numeric values stored as strings with thousands-separators (commas), which prevented mathematical calculations.
- To overcome this Spark SQL was used to:
  - Remove commas using REPLACE.
  - Cast string columns into DOUBLE for calculations like "Emissions per Person".
  


## 📊 Step 3: Data Analysis

- CTE for Market Share: A Common Table Expression to calculate what percentage of total US emissions the top 10 states account for (finding it to be 51%). [30:41]
- Geospatial Data: Selecting Latitude and Longitude for point-map visualization.



## 📈 Step 4: Building the Dashboard in Databricks

The final dashboard comprises four primary visualizations:
1. Point Map: Displays the continental US emissions density.
2. Scatter Plot: Compares population vs. emissions per person.
3. Pie Chart: Breaks down the percentage of emissions by state.
4. Bar Chart: Identifies the top 10 counties with the highest megatons of CO2.


 ## 💡 Notable Findings

- The "Top 10" Impact: Just 10 states are responsible for over half of all emissions in the United States.
- Population Paradox: Highly populated areas (like Los Angeles County) often show lower emissions per person compared to certain low-population industrial or energy-producing areas in regions like North Dakota or New England.

<img width="1666" height="817" alt="image" src="https://github.com/user-attachments/assets/50f39e9f-a190-44b9-93bf-9bb8466d9bd7" />
