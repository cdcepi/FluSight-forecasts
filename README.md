# FluSight Forecasts
This repository contains forecasts submitted to CDC as part of the [FluSight](https://predict.phiresearchlab.org/) influenza forecasting challenge. It is being provided as a resource to help develop ensemble models and additional methods for intepreting/visualizing forecasts. Forecast data are publically contributed by the teams involved in the challenge. They are not official CDC forecasts and are not endorsed by CDC. Anyone interested in using these data for additional research or publications is requested to contact [flucontest@cdc.gov](mailto:flucontest@cdc.gov) for information regarding attribution of the source forecasts.

### FluSight challenge
Since 2013, the Influenza Division at CDC has worked with external researchers to improve the science and usability of influenza forecasts by coordinating seasonal influenza prediction challenges. Teams create models to predict seasonal and short-term targets related to seasonal influenza and submit weekly forecasts to CDC. More information and visualizations of forecasts can be found at the FluSight [website](https://predict.phiresearchlab.org/).

### Data organization
Forecast submissions are organized by season, and within each season by team name or number. Submissions are labeled in the format “EWXX-TeamXX-YYYY-MM-DD.csv”, where
* **EWXX** is the latest MMWR week of data used in the forecast
* **TeamXX** is the team name/number
* **YYYY-MM-DD** is the date of forecast submission

### Forecast visualizations
Visualizations for current week's forecasts can now be found on the FluSight [website](https://predict.phiresearchlab.org/).

### Forecast structure
Submissions are structured in an identical matter. Each submission consists of the following variables:
* **Location:** location of forecast - either entire US or particular HHS Region
* **Target:** forecast target
* **Type:** forecast type - either "Point" for point forecast or "Bin" for probabilistic bin
* **Unit:** unit of forecast - either "week" or "percent"
* **Bin_start_incl:** inclusive starting value for probabilistic forecast bin
* **Bin_end_notincl:** exclusive ending value for probabilistic forecast bin
* **Value:** forecasted point value or probability assigned 

### Forecast targets
Each submission consists of forecasts for the following targets:
* **Season onset:** The [MMWR surveillance week](http://wwwn.cdc.gov/nndss/script/downloads.aspx) when the percentage of visits for influenza-like illness (ILI) reported through ILINet reaches or exceeds the [baseline](https://github.com/cdcepi/FluSight-forecasts/blob/master/wILI_Baseline.csv) value for three consecutive weeks. Forecasted “onset” week values are for the first week of that three week period.
* **Peak week:** The MMWR surveillance week that the weighted ILINet percentage is the highest for a given influenza season. 
* **Peak percentage:** The highest numeric value that the weighted ILINet percentage reaches during a given influenza season.
* **1 wk ahead:** Weighted ILINet percentage for the MMWR week following the last week of data used to generate the forecast
* **2 wk ahead:** Weighted ILINet percentage for the MMWR week two weeks after the last week of data used to generate the forecast
* **3 wk ahead:** Weighted ILINet percentage for the MMWR week three weeks after the last week of data used to generate the forecast
* **4 wk ahead:** Weighted ILINet percentage for the MMWR week four weeks after the last week of data used to generate the forecast

### Past baseline wILI values
Baseline weighted ILI values from previous seasons at both the national and HHS regional level are available in the [wILI_Baseline]( https://github.com/cdcepi/FluSight-forecasts/blob/master/wILI_Baseline.csv) CSV file.

### Current submission template
The submission template for the 2017-2018 challenge is available in the [2017-2018_submission_template](https://github.com/cdcepi/FluSight-forecasts/blob/master/2017-2018_submission_template.csv) CSV file.
