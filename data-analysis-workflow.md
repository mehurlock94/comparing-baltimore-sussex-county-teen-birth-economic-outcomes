# This document outlines the workflow of data collection and analysis in Excel for Mini Project #2, labeled comparing-baltimore-sussex-county-teen-birth-economic-outcomes

Raw data for this project were taken from the Opportunity Atlas [database](https://www.opportunityatlas.org/). All sets are organized by tract, which are areas that have a few thousand inhabitants.

Data were imported into Excel and filtered based on two locations: 
1. Baltimore, MD
1. Sussex County, DE

A [previous analysis](https://github.com/mehurlock94/comparing-baltimore-lewes-social-status/blob/main/README.md) investigated similar properties specific to Lewes, DE. The differences between Baltimore and Lewes were subsequently assumed to have many confounding variables, so the scope for Delaware was expanded to Sussex County to better align total population and to better diversify demographics. Data from Baltimore locations were processed to include only locations which exist within Baltimore city limits. Some data points were designated as Baltimore, MD but truly occurred outside these boundaries. With the locations filtered, datasets for individual variables obtained from Opportunity Atlas were matched to the filtered list using the VLOOKUP Excel function. The raw data compiled for analysis are included [here](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/balt_sussex_raw_data.xlsx). The Excel file with manupulated data is inlcuded [here](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/comparing_balt_sussex_teen_birth_economic_outcomes_data.xlsx)

## Multiple Linear Regression
For each location, multiple linear regression was performed using the regression tool within the Microsoft Excel Data Analysis Toolpack. The independent variables analyzed were Teen Birth Rate, Fraction Married, Median rent, and Single Parent Frequency with the dependent variable being Poverty Rate. For both locations, the F-value for the MLR was significant (F<1E-6). For each variable, a p-value below 0.05 was taken to be significant. Significant variables were considered for analysis via simple linear regression.

## Simple Linear Regression
Simple linear regression was performed to compare teen birth rate vs. single parent frequency and to compare single parent frequency vs. poverty rate using the SLOPE, INTERCEPT, and RSQ functions in excel. The values were likewise plotted on a scatterplot and fitted with a line representing the simple linear regression. Since the spread for each dataset was moderate to severe (the highest R-squared value was .533), outliers were not considered, as it is expected that several would have qualified using two standard errors from predicted values as a criteria. The Slope, Intercept and R-squared value for each location and comparison were summarized in a table.

All tables and plots were organized into figures within the main [README.md](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/README.md)
