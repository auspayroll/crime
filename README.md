## COMP 6200 NSW Crime Report

#### Authors

- Priya Chotalia
- Aidan Van Klaveren
- Brigid Onyowo Echikwu
- Simon Grant

### Introduction

Crime is a highly contentious and politically charged issue. In this
report we attempt to analysis Crime in NSW through statistics and data modelling
to gain some insight. 

We collect crime data and combine it with other sources for our analysis. There are two
main datasets we create - one is a time series datasets crimeTS from 2013 to 2018 that combines
raw crime data with population figures for each local government area. 

The second dataset is a snapshot of crime in 2016 combined with some predictors available from the most recent
Australian census (2016) 

The predictors we have chosen are as follows:

- population density
- % children (5-14)
- % youth (15 - 24)
- % young adult( (25 - 34)
- % adult (40 - 54)
- % senior (55 and over)
- death rate
- fertility rate

- % speak language other than English
- % Australian citizen
- % born overseas
- % born in Europe
- % born in Asia
- % born in Africa
- % born in Middle-East
- % born in Americas

- median income
- % professional workers
- % trade workers
- % office workers

### Goals

- Identify crime trends in previous years, both for NSW overall and 
in each crime category using summary statistics and simple linear regression. 

- Identify major crime hotspots for particular categories through unsupervised clustering. 

- To identify some factors that may contribute to crime using supervised modelling techniques. 



### Data Collection / Cleaning

Crime data was collected from NSW Bureau of Crime Statistics and Research (BOCSAR). 
The data was provided as raw crime figures for each month since 1995 to 2019 by
crime category and subcategory. These figures were transformed into yearly totals. 

Because we were interested in crime rates per capita for each area, population data 
was obtained from the Australian Bureau of Statistics (ABS). The most complete population
data by region was from 2013. 

Datasets used were categorised by NSW local government areas (LGA's) which are larger regions
usually containing a number of smaller suburbs. The ABS uses a four digit LGA code preceeded
by a state code (1 - for NSW). Crime data from BOCSAR didn't contain LGA codes and had
to be matched by LGA name. 

Finally each LGA was matched with latitude and longitude data in order to gain 
insights into crime clusters. LGA latitude and longitude data could not be found directly
but a postcode database was used. A postcode/suburb within each LGA was used to attribute
a latitude and longitude value. 

[Transformation and cleaning](clean.ipynb)



### NSW Crime Summary

A basic overview of NSW crime data can be found at

[NSW Crime Summary](nsw.ipynb)

All crime categories are explored collectively in NSW overall and by 
local government area. 


### Offences by Category

Each main category of crime is explored in more detail, and
in some cases by subcategory. We have chosen offences that are most common
in order to given greater power when creating predictive models. 

[Drug Offences](dugs.ipynb) by Simon

[Theft and Sexual Offences](Theft_Sexual offences.ipynb) by Aidan

[Assault](Assault.ipynb) by Priya

[Robbery and Arson](Drugs-Mal-Arson+Robbery.ipynb) by Breegid


#### Data Sources 

## DATA SOURCE REFERENCE

---
### DATA SOURCES

####  ___NSW Bureau of Crime Statistics and Research (BOCSAR)___

https://www.bocsar.nsw.gov.au/Pages/bocsar_datasets/Datasets-.aspx \
*Name:* Recorded Crime by offence\
*Geographical Breakdown:* LGA\
*Released:* 4/4/2020\
*Format:* MS Excel\
https://www.bocsar.nsw.gov.au/Documents/Datasets/RCI_offencebymonth.xlsm


#### ___Australian Bureau of Statistics (ABS)___
https://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1410.02013-18?OpenDocument \

*Name:* Population and People \
*Geographical Breakdown:* LGA \
*Released:* 17/01/2020\
*Format:* MS Excel\
https://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&14100ds0002_2011-18.xls&1410.0&Data%20Cubes&CD00A471A1A74938CA2584F1000F82F5&0&2013-18&17.01.2020&Latest 

*Name:* Income (including Government Allowances) \
*Geographical Breakdown:* LGA \
*Released:* 04/03/2020\
*Format:* MS Excel\
https://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&14100ds0006_2011-18.xls&1410.0&Data%20Cubes&A10EF1AF3082022CCA2584F1000F85EE&0&2013-18&17.01.2020&Latest

*Name:* Education and Employment \
*Geographical Breakdown:* LGA \
*Released:* 17/01/2020\
*Format:* MS Excel\
https://www.abs.gov.au/ausstats/subscriber.nsf/log?openagent&14100ds0008_2011-18.xls&1410.0&Data%20Cubes&7E8A33B57A8F6649CA2584F1000F873E&0&2013-18&17.01.2020&Latest


#### Matthew Proctor
*Name:* Australian postcode database
*Updated:* 16/05/2020
https://www.matthewproctor.com/australian_postcodes



