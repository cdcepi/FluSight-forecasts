This folders contains forecasts submitted during the 2019-2020 influenza season. Each folder contains submissions from a single forecasting model. Further details about the forecasts are available below. 

# Background
When and where flu increases will occur, how large the impact of the flu season will be, and when the flu season will peak varies from season to season, making the preparation for and response to the influenza seasons difficult. Flu forecasting can change that by offering the possibility to look into the future and better plan ahead, potentially reducing the impact of flu.

To help support the development of the science of flu forecasting and its application for public health, CDC, through the Epidemic Prediction Initiative (EPI), has organized FluSight challenges to forecast the timing, intensity, and short-term activity of the influenza season since the 2013-14 season. These challenges have provided the scientific and public health community experience in real-time forecasting, the ability to evaluate forecast accuracy, and experience in communicating and applying these forecasts in real-world settings. For example, forecasts are currently used to inform CDC’s activity summaries provided to public health officials and CDC leadership and public messaging regarding the timing of the influenza season and how the public can protect themselves and their family.

As part of the forecasting initiative, CDC has developed, through EPI, the “FluSight” flu forecasting website, which facilitates the real-time sharing and visualization of weekly flu forecasts. Visitors to this site can view current and past forecasts throughout the flu season for the start and peak week, peak intensity, and the near-term activity at the national and regional levels. ILINet data are generally updated every Friday, and forecasts are generally available by Tuesday. During the 2019–20 season, CDC expects forecasting teams to provide over 30 national-level forecasts each week.

# Forecast Targets
For each week during the season, participants will be asked to provide national and regional probabilistic forecasts for the entire influenza season (seasonal targets) and for the next four weeks (four-week ahead targets). The seasonal targets are the onset week, the peak week, and the peak intensity of the 2019-20 influenza season. The four-week ahead targets are the percent of outpatient visits experiencing influenza-like illness (ILI) one week, two weeks, three weeks, and four weeks ahead from date of the forecast.

## Onset Week
**Definition:** he onset of the season is defined as the MMWR surveillance week when the percentage of visits for influenza-like illness (ILI) reported through ILINet reaches or exceeds the baseline value for three consecutive weeks. Forecasted "onset" week values should be for the first week of that three week period.

The 2019-20 ILINet baseline values for the US overall and each HHS region are the following:

- US National: 2.4%
- HHS Region 1: 1.9%
- HHS Region 2: 3.2%
- HHS Region 3: 1.9%
- HHS Region 4: 2.4%
- HHS Region 5: 1.9%
- HHS Region 6: 3.8%
- HHS Region 7: 1.7%
- HHS Region 8: 2.7%
- HHS Region 9: 2.4%
- HHS Region 10: 1.5%

**Motivation:** Accurate and timely forecasts for the start of the season can be useful in planning for influenza prevention and control activities. For the general public, the start of the season offers an important opportunity to take preventive measures, such as getting vaccinated, before flu becomes widespread. For clinicians and public health authorities, the start of the season indicates that influenza should be high on their list of possible diagnoses for patients with respiratory illness. This is particularly important for the management of hospitalized patients and high-risk patients with suspected influenza when early treatment with influenza antivirals can be critical.

## Seasonal Peak Week
**Definition:** The peak week will be defined as the MMWR surveillance week that the weighted ILINet percentage, rounded to one decimal place, is the highest for the 2019-20 influenza season.

**Motivation:** Accurate and timely forecasts for the peak week can be useful for planning and promoting activities to increase influenza vaccination prior to the bulk of influenza illness. For healthcare, pharmacy, and public health authorities, a forecast for the peak week can guide efficient staff and resource allocation.

## Seasonal Peak Intensity
**Definition:** The intensity will be defined as the highest numeric value, rounded to one decimal place, that the weighted ILINet percentage reaches during the 2019-20 influenza season.

**Motivation:** Accurate and timely forecasts for the peak week and intensity of the influenza season can be useful for influenza prevention and control, including the planning and promotion of activities to increase influenza vaccination prior to the bulk of influenza illness. For healthcare, pharmacy, and public health authorities, a forecast for the peak week and intensity can help with appropriate staff and resource allocation since a surge of patients with influenza illness can be expected to seek care and receive treatment in the weeks surrounding the peak.

## Short Term Forecasts
**Definition:** One- to four-week ahead forecasts will be defined as the weighted ILINet percentage for the target week, rounded to one decimal place.

**Motivation:** Forecasts capable of providing reliable estimates of influenza activity over the next month are critical because they allow healthcare and public health officials to prepare for and respond to near-term changes in influenza activity and bridge the gap between reported incidence data and long-term seasonal forecasts.

# ILINet Data
Data on the weekly proportion of people seeing their health-care provider for influenza-like illness (ILI) is reported through the [ILINet System](https://www.cdc.gov/flu/weekly/overview.htm#anchor_1539281266932) for the United States as a whole and for each HHS health region. These data can be accessed directly from [CDC](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html) or the R package cdcfluview

# Forecast Evaluation
All forecasts will be evaluated using the weighted observations pulled from the ILINet system in week 28, and the logarithmic score will be used to measure the accuracy of the probability distribution of a forecast. Logarithmic scores will be averaged across different time periods, the seasonal targets, the four-week ahead targets, and locations to provide both specific and generalized measures of model accuracy. Official rankings of teams by forecast accuracy will only be based on the log score. Nonetheless, forecasters are requested to continue to submit point predictions, which should aim to minimize the absolute error (AE). CDC may report on the accuracy of point predictions in manuscripts and analyses.

## Logarithmic Score
If p is the set of probabilities for a given forecast, and pi is the probability assigned to the observed outcome i, the logarithmic score is:

S(p,i)=ln(pi)

For each forecast of each target, pi will be set to the probability assigned to the single bin containing the observed outcome (based on the rounded weighted ILINet value). If onset is never reached during the season, only the probability assigned to the bin for “none” will be scored. For the peak week target, in the case of multiple peak weeks, the probability assigned to the bins containing each peak week will be summed.

Undefined natural logs (which occur when the probability assigned to the observed outcome was 0) will be assigned a value of -10. Forecasts which are not submitted (e.g. if a week is missed) or that are incomplete (e.g. sum of probabilities greater than 1.1) will also be assigned a value of -10.

In addition to the final scores, CDC may provide interim score reports to participants on a semi-regular basis during the season. Interim scores will not impact final team standings.

Example: A forecast predicts there is a probability of 0.3 (i.e., a 30% chance) that the flu season starts on week 45, with the remaining 0.7 probability distributed across other weeks according to the forecast. Once the flu season has started, the prediction can be evaluated, and the ILINet data show that true onset was on week 45. The probability assigned to week 45, 0.3, would be derived, and the forecast would receive a score of log(0.3) = -1.20. If the season started on another week, the score would be calculated on the probability assigned to that week.

# R Package
FluSight Package
The FluSight R package contains functions to help create and format forecasts, read and verify forecast CSVs, and score forecasts. These are the functions that will be used at CDC to verify and score submitted forecasts. Teams are welcome to use these tools to ensure their forecasts fit the required template and score their forecasts prior to receiving official scores from CDC

The package can be downloaded from [GitHub](https://github.com/jarad/FluSight).

Install and load package
```
devtools::install_github("jarad/FluSight")
library(FluSight)
```
Read in entry CSV
```
entry <- read_entry("your_csv.csv")
```
Verify entry
```
verify_entry(entry)
verify_entry_file("your_csv.csv")
```
Create file of observed truth from CDC surveillance data
```
truth <- create_truth(fluview = T, year = 2018)
```
Expand observed truth to take into account additional bins - 1 bin for weeks, 5 bins for percentage
```
exp_truth <- expand_truth(truth, week_expand = 1, percent_expand = 5)
```
Score a weekly entry against the observed truth
```
exact_scores <- score_entry(entry, truth)
expand_scores <- score_entry(entry, exp_truth)
```
# References
Gneiting T and AE Raftery. (2007) Strictly proper scoring rules, prediction, and estimation. Journal of the American Statistical Association. 102(477):359-378. Available at: https://www.stat.washington.edu/raftery/Research/PDF/Gneiting2007jasa.pdf

Rosenfeld R, J Grefenstette, and D Burke. (2012) A Proposal for Standardized Evaluation of Epidemiological Models. Available at: http://delphi.midas.cs.cmu.edu/files/StandardizedEvaluationRevised12-11-09.pdf.
