# GDP-and-Educational-Data-Analysis
This project analyzes Gross Domestic Product (GDP) and educational data for countries to answer specific questions about GDP ranking, country matches, and education statistic
## Table of Contents

1. [Introduction](#introduction)
2. [Data Sources](#data-sources)
3. [Setup](#setup)
4. [Analysis Workflow](#analysis-workflow)
5. [Results](#results)
6. [Acknowledgements](#acknowledgements)

---

## Introduction

This project utilizes data from the **American Community Survey** and the **World Bank** to:
- Identify countries with matching IDs in GDP and education datasets.
- Rank countries by GDP.
- Analyze the 13th ranked country in the GDP list.

---

## Data Sources

1. **Gross Domestic Product (GDP) Data**  
   - URL: [Download GDP Data](https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2FGDP.csv)  
   - Contains GDP rankings for 190 countries.

2. **Educational Data**  
   - URL: [Download Education Data](https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2FEDSTATS_Country.csv)  
   - Contains educational statistics and metadata for countries.

3. **Code Book**  
   - URL: [GDP Code Book](http://data.worldbank.org/data-catalog/GDP-ranking-table)  
   - URL: [Education Code Book](http://data.worldbank.org/data-catalog/ed-stats)

---

## Setup

1. **Dependencies**  
   Install required R packages before running the scripts:
   ```R
   install.packages("dplyr")
   install.packages("tidyr")
   ```

2. **Download the Data**  
   Use `download.file()` in R to fetch the datasets:
   ```R
   gdp_url <- "https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2FGDP.csv"
   edu_url <- "https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2FEDSTATS_Country.csv"

   download.file(gdp_url, destfile = "GDP.csv", method = "curl")
   download.file(edu_url, destfile = "EDU.csv", method = "curl")
   ```

3. **Load and Clean Data**  
   Load the datasets using `read.csv()` and clean them as described in the `Analysis Workflow` section.

---

## Analysis Workflow

1. **Load GDP Data**  
   - Skip metadata rows and select relevant columns (`CountryCode`, `Rank`, `CountryName`, `GDP`).

2. **Load Educational Data**  
   - Load all columns as is.

3. **Merge Datasets**  
   - Merge GDP and educational data using the `CountryCode` column.

4. **Filter and Sort Data**  
   - Sort the merged data in descending order by GDP rank.

5. **Extract Insights**  
   - Count the number of matching IDs.
   - Identify the 13th ranked country.

---

## Results

1. **Number of Matching IDs:**  
   The number of matching country codes is **`<result>`**.

2. **13th Country in GDP Ranking:**  
   The 13th ranked country is **`<result>`**.

---

## Acknowledgements

Data used in this project is provided by:
- The American Community Survey
- The World Bank's GDP and Education Statistics
