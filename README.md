# FluSight Forecasts
This repository contains forecasts submitted to CDC as part of the FluSight influenza forecasting challenge. It is being provided as a resource to help develop ensemble models and additional methods for intepreting/visualizing forecasts. Forecast data are publically contributed by the teams involved in the challenge, and are not official CDC forecasts or endoresed by CDC. 

### Past baseline wILI values
Baseline weighted ILI values from previous seasons at both the national and HHS regional level are available in the [wILI_Baseline]( https://github.com/cdcepi/FluSight-forecasts/blob/master/wILI_Baseline.csv) CSV file.

### Data organization
Forecast submissions are organized by season, and within each season by team name or number. Submissions labeled with the same name or number across seasons were developed using the same methodology. Submissions are labeled in the format “EWXX-TeamXX-YYYY-MM-DD.csv”, where
* **EWXX** is the latest MMWR week of data used in the forecast
* **TeamXX** is the team name/number
* **YYYY-MM-DD** is the date of forecast submission

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
* **1 wk ahead:** Weighted ILINet percentage for the MMRW week following the last week of data used to generate the forecast
* **2 wk ahead:** Weighted ILINet percentage for the MMRW week two weeks after the last week of data used to generate the forecast
* **3 wk ahead:** Weighted ILINet percentage for the MMRW week three weeks after the last week of data used to generate the forecast
* **4 wk ahead:** Weighted ILINet percentage for the MMRW week four weeks after the last week of data used to generate the forecast
