# 🏥 Analyzing Health and Poverty Data Across US Counties (2022)

## Background
This project was created for the University of Michigan SI 618: Data Analysis and Manipulation. It is split into three main parts, each building on the previous to explore the relationship between health outcomes and poverty across US counties using public datasets.

## 👥 Team Members
- **Vaishnavi Venkataraghavan** (*vaishven*)
- **Shreya Gupta** (*gshrey*)
- **James Gair** (*jgair*)

## Overview
We examine **health statistics** and **poverty levels** across Michigan counties using:
- **CDC PLACES** (county-level health indicators)
- **U.S. Census Bureau ACS 5-Year Estimates** (poverty rates, income, demographics)

The goal is to uncover patterns in:
- Health outcomes (e.g., obesity, diabetes, stroke)
- Disabilities
- Risk behaviors (e.g., smoking, inactivity, binge drinking)
- Socioeconomic factors (poverty, income)

## Motivation & Research Questions
Health and economic conditions are deeply intertwined. We explore:
1. How does the relationship between poverty rates and disease prevalence vary across counties? Do high-poverty areas experience worse health outcomes?
2. What health risk behaviors are most prevalent in high-poverty counties, and how do these relate to disease prevalence?
3. How do rural and urban counties differ in the impact of income on disease prevalence, and what diseases are most prevalent in high-poverty counties?

## Data Sources
- **CDC PLACES Health Data**  
  [CDC PLACES](https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-County-Data-20/swc5-untb/about_data)  
  County-level health indicators (disabilities, chronic conditions, behaviors)
- **U.S. Census Bureau ACS 5-Year Estimates**  
  [Census ACS API](https://www.census.gov/data/developers/data-sets.html)  
  Socioeconomic data (poverty rates, income, demographics)

## Data Description

### CDC PLACES Variables (2022)
- **LocationName**: County name
- **Category**: Health indicator type (e.g., Health Outcomes, Disability)
- **Measure**: Health measure (e.g., "Obesity among adults")
- **Data_Value**: Percentage of county population affected (age-adjusted)
- **TotalPopulation**: County population
- **Short_Question_Text**: Short name of health measure (e.g., "Obesity", "Stroke")

### Census ACS 5-Year Poverty Dataset Variables (2022)
- **Geographic Area Name**: County and state
- **Total**: Total population
- **BP_ Total%**: Percent below poverty line
- **Median income**: Median household income
- **Demographic breakdowns**: By race, gender, etc.

### Dataset Size
| Dataset      | Rows    | Columns |
|--------------|---------|---------|
| CDC PLACES   | 120,443 | 15      |
| Census ACS   | 3,221   | 34      |

### Handling Missing Data
- CDC PLACES: No missing values.
- ACS: Invalid values (`-999999999`, `-888888888`) replaced with `0`.

## Analysis Workflow

### Part 1: Data Preparation & Exploration
- Cleaned and merged CDC and ACS data for US counties.
- Created new columns for total affected population.
- Explored health categories and summarized key variables.

### Part 2: Statistical Analysis
- Correlation and regression analysis between poverty rates and health outcomes.
- Compared high- and low-poverty counties.
- Analyzed risk behaviors (smoking, inactivity, binge drinking) and their relationship to poverty.

### Part 3: Machine Learning & Clustering
- Used K-Means and Agglomerative Clustering to group counties by health and poverty profiles.
- Identified clusters of counties with similar health outcomes and socioeconomic status.

## Key Findings

- **Obesity, diabetes, high blood pressure, and tooth loss** are significantly more prevalent in high-poverty counties.
- **Stroke** shows the strongest positive correlation with poverty rate among health outcomes.
- **Physical inactivity, smoking, and short sleep duration** are more common in high-poverty counties; **binge drinking** is more common in wealthier counties.
- **Cancer** prevalence does not correlate strongly with poverty.
- Clustering reveals two main groups: counties with lower poverty and better health, and those with higher poverty and worse health outcomes.

## Visualization Plan

- **Bar Charts**: Health disparities by county
- **Stacked Bar Charts**: Disability rates in top counties
- **Histograms/Box Plots**: Median income and health outcome distributions
- **Scatterplots**: Poverty vs. health outcomes
- **Cluster Plots**: County groupings by health and poverty

## Usage

- **Notebooks**:
  - `Part_1_Data_Description_and_Manipulation.ipynb`: Data cleaning & exploration
  - `Part_2_Data_Analysis.ipynb`: Statistical analysis & visualization
  - `Part_3_Machine_Learning.ipynb`: Clustering & advanced analysis

Open the notebooks in Jupyter Notebook or VS Code and run cells sequentially.

## Limitations & Future Work

- Data is cross-sectional (single year).
- Some health measures are self-reported.
- County-level aggregation may mask within-county disparities.
- Future work: Multi-year trends, policy impact evaluation, deeper analysis of mental health.

## License

This repository is licensed under the MIT License.

---

*Generative AI was used for code formatting, markdown editing, and some code comments*
