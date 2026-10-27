# Chicago Taxi Demand Analysis

## Project Overview

This project analyzes taxi trip data from Chicago to identify leading taxi companies, the neighborhoods with the highest average number of drop-offs, and the relationship between weather conditions and trip duration.

The analysis focuses on November 2017 and combines SQL queries, web scraping, exploratory data analysis, data quality checks, visualizations, and statistical hypothesis testing.

## Business Objectives

- Identify taxi companies with the highest number of trips.
- Compare the trip volumes of selected taxi companies.
- Determine which Chicago neighborhoods have the highest average number of daily drop-offs.
- Collect and classify hourly weather conditions.
- Test whether average trip duration from the Loop to O'Hare International Airport differs between Saturdays with good and bad weather.

## Tools and Technologies

- **SQL** — querying and aggregating taxi trip, company, neighborhood, and weather data.
- **Python** — data analysis and workflow implementation.
- **Pandas** — data manipulation and preprocessing.
- **Matplotlib** — data visualization.
- **Requests and BeautifulSoup** — web scraping of Chicago weather records.
- **SciPy** — statistical hypothesis testing.
- **Jupyter Notebook** — analysis documentation and execution.

## Project Workflow

### 1. Data Collection

Hourly weather records for Chicago in November 2017 were collected from an HTML table using `Requests` and `BeautifulSoup`.

### 2. SQL Analysis

SQL queries were used to:
- Count trips by taxi company for November 15–16, 2017.
- Compare companies whose names contain "Yellow" or "Blue" during November 1–7, 2017.
- Group taxi companies into selected categories.
- Calculate average daily drop-offs by neighborhood.
- Retrieve the neighborhood identifiers for the Loop and O'Hare.
- Classify weather conditions and prepare the trip data for hypothesis testing.

### 3. Data Preprocessing and Exploratory Analysis

The resulting datasets were checked for data types, missing values, and duplicate records. Visualizations were created to compare taxi company trip volumes and identify the neighborhoods with the highest average number of drop-offs.

### 4. Statistical Hypothesis Testing

A two-sided Welch's independent-samples t-test was used to compare trip durations on Saturdays between the Loop and O'Hare under good and bad weather conditions.

The significance level was set to 0.05. Non-positive trip durations were excluded because they were not plausible for this route. Additional sensitivity checks were performed to assess the robustness of the findings.

## Key Findings

- **Taxi companies:** Flash Cab had the highest trip volume in the analyzed period, substantially exceeding the other companies.
- **Popular destinations:** Loop and River North had the highest average daily numbers of drop-offs among the neighborhoods analyzed.
- **Weather and trip duration:** The Welch's t-test returned a p-value of approximately `2.42 × 10⁻¹¹`, below the 0.05 significance level.
- **Average trip duration:** The observed mean was approximately 2,013 seconds under good weather and 2,427 seconds under bad weather.
- **Statistical conclusion:** The null hypothesis of equal mean trip durations was rejected. The observed association does not, by itself, establish that weather caused the difference.

## Repository Structure

```text
chicago-taxi-demand-analysis/
├── README.md
├── chicago_taxi_demand_analysis.ipynb
└── .gitignore
```

## How to Explore the Project

Open `chicago_taxi_demand_analysis.ipynb` in Jupyter Notebook or JupyterLab to review the SQL queries, data collection process, exploratory analysis, visualizations, and statistical test.

Some analysis steps use CSV files supplied by the original project environment. These files may need to be obtained separately to reproduce every notebook cell.

## Project Context

This project was completed as part of the TripleTen Data Analyst program, Sprint 7: Data Collection and Storage (SQL).