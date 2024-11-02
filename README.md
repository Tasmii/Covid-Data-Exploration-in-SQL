# COVID-19 Data Exploration Project

This project performs data exploration on COVID-19 datasets, including death rates, infection rates, and vaccination data, using SQL. The objective is to analyze the impact of COVID-19 globally, regionally, and by country. The SQL script explores trends in infections, deaths, and vaccinations, and calculates statistics to show infection and death percentages in various countries and continents.

## Project Structure

- **Datasets**:
  - `CovidDeaths.xlsx`: Contains data on COVID-19 cases, deaths, and populations by country and date.
  - `CovidVaccination.xlsx`: Contains data on COVID-19 vaccinations by country and date.

- **SQL Skills Used**:
  - Joins
  - Common Table Expressions (CTEs)
  - Temporary Tables
  - Window Functions
  - Aggregate Functions
  - Views
  - Data Type Conversions

## Prerequisites

- SQL Server or compatible database system to execute SQL scripts
- Import `CovidDeaths.xlsx` and `CovidVaccination.xlsx` as tables `CovidProject..CovidDeaths$` and `CovidProject..CovidVaccination$`

## Data Exploration Process

1. **Initial Data Selection**  
   - Querying basic information to understand the structure and variables within the data.
   - Filtering by valid continent values to exclude irrelevant data.

2. **Total Cases vs Total Deaths**  
   - Calculates the death percentage (`total_deaths/total_cases * 100`) for countries to assess the mortality rate.

3. **Total Cases vs Population**  
   - Determines what percentage of the population was infected by COVID-19 (`total_cases/population * 100`).

4. **Highest Infection Rate by Country**  
   - Identifies countries with the highest infection rate relative to their population.

5. **Highest Death Count per Population**  
   - Lists countries with the highest death count to understand the mortality impact relative to the population.

6. **Analysis by Continent**  
   - Calculates the death count per population by continent to see which regions were most impacted.

7. **Global Totals**  
   - Summarizes total cases, deaths, and the global death percentage.

8. **Population vs Vaccinations**  
   - Shows the percentage of the population that has received at least one vaccine dose using `SUM()` with a rolling window on vaccinations.

9. **Using CTEs and Temporary Tables for Vaccination Calculations**  
   - Applies CTEs and temporary tables to calculate rolling vaccination data and vaccination percentages.
   - A final calculation of the percentage of population vaccinated by country is derived for visualization.

10. **Creating a View for Visualization**  
    - Saves the data with vaccination percentages as a SQL view (`PercentPopulationVaccinated`) for easy access in future analyses and visualizations.

## SQL Script Highlights

- **Window Functions**: Used to calculate rolling sums for cumulative vaccination counts.
- **CTEs and Temporary Tables**: Simplify complex calculations and allow for intermediate data storage.
- **Views**: Created for efficient access to pre-calculated data for further analysis or visualization tools.

## How to Run the Script

1. Load the `CovidDeaths.xlsx` and `CovidVaccination.xlsx` files into your SQL database as tables `CovidProject..CovidDeaths$` and `CovidProject..CovidVaccination$`.
2. Run each SQL block in the script to perform data cleaning and calculations.
3. View results or use the `PercentPopulationVaccinated` view for additional analysis or visualizations.

## Results and Analysis

- **Death and Infection Rates**: The script calculates and ranks countries and continents by death rates and infection percentages, providing insights into COVID-19's impact across different regions.
- **Vaccination Analysis**: Tracks vaccination rates as a percentage of the population to analyze vaccination efforts worldwide.
