## PROPOSED ANALYSIS

Our project will analyse crime rates in NSW. We will look at crime rates in general, and by major categories of crime (Drug Offences, Assaults etc.). Crime sub-categories will not be used in this analysis. 


## GOALS AND TECHNIQUES


**Goal 1:** 
Estimate crime rates for the next five years in NSW, collectively and by major areas.

**Technique 1:**
We use historical data provided by BOCSAR for annual crime rates since 1995. We use simple linear regression to provide a model that will allow us to project crime rates into the future.

**Goal 2:**\
Identify crime hotspots in NSW, by crime rates overall and then by major offence category. 

**Technique 2:**\
We use basic summary crime statistics to compare NSW regions. We use population data to compare crime rates on a per capita basis. 

We will also analyse the distribution of crime categories graphically (histogram) against regions. We can analyse and identify areas by which quantile they reside in. 

We can also identify outlier regions by use of box plots. We will use the latest annual crime statistics available (2019).

**Goal 3:**\
To identify similar areas in NSW with regards to demographics and crime rates. 

**Technique 3:**\
We use K means clustering using three dimensions (age, income, crime per capita) to identify similar regions in NSW. The number of clusters will need to be determined by inspection of a scatter plot. 


**Goal 4:**\
Determine to what degree, age and income affect crime rates. 

**Technique 4:**\
The age and income data will be normalised to create a multi-linear regression model for crime rates per capita in each local government area. It may be necessary to remove extreme outliers to fit a linear model. If the model is valid, we can interpret the effect of age and income by the magnitude of its coefficient. 

We use the latest annual crime statistics from BOCSAR and demographic information (age, income) from the ABS. We combine both data sets by local government area (LGA) which is provided by both sources. Since LGA fields are not identical, we will need to clean the LGA fields to ensure they match. This is feasible since there are only 128 local government areas in NSW. 


## PROJECT PLAN

1. __Data Preparation__
- Data from both datasets is converted from Excel format to CSV.
- Crime statistics are given by month but need to totalled by year. 
- LGA fields from both data sets need to match to enable join.
- generate per capita field

2. __Exploratory Analysis of Crime data from BOCSAR__
- Summary statistics by region/crime category
- Graphical exploration

3. **Modelling**
- simple linear regression of historical crime data
- clustering of age * income * crime per capita
- multiple linear regression: crime/capita = age + income

4. **Evaluation**
- evaluate simple linear regression and multiple linear regression models
- determine correct number of clusters 

5. **Conclusions/Analysis**
- determine if we can make forecasts by simple linear regression 
- predict crime rates in 5 years? 
- What are the high crime areas in NSW? Have they always been high? 
- What NSW areas are similar?
- Are median age and income good predictors for crime rates 
- interpretation of model.




---
## DATA SOURCES

### ___NSW Bureau of Crime Statistics and Research (BOCSAR)___

https://www.bocsar.nsw.gov.au/Pages/bocsar_datasets/Datasets-.aspx \
*Name:* Recorded Crime by offence\
*Geographical Breakdown:* LGA\
*Released:* 4/4/2020\
*Format:* MS Excel\
https://www.bocsar.nsw.gov.au/Documents/Datasets/RCI_offencebymonth.xlsm


### ___Australian Bureau of Statistics (ABS)___
https://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1410.02013-18?OpenDocument \
*Name:* Population and People \
*Geographical Breakdown:* LGA \
*Released:* 17/01/2020\
*Format:* MS Excel\
https://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&14100ds0002_2011-18.xls&1410.0&Data%20Cubes&CD00A471A1A74938CA2584F1000F82F5&0&2013-18&17.01.2020&Latest 
