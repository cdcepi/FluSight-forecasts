This folders contains forecasts submitted during the 2017-2018 influenza season. Each folder contains submissions from a single forecasting model. Further details about the forecasts are available below. 

# Background
Influenza (flu) is a respiratory virus that can result in illness ranging from mild to severe. Each year, millions of people get sick with influenza, hundreds of thousands are hospitalized and thousands of people die from flu. Tracking flu activity to inform prevention measures is an important public health function that is currently performed by CDC’s flu surveillance system, which can lag behind real-time flu activity. But what if it were possible to predict flu activity accurately weeks or months in advance for multiple locations? While this is not currently possible, the goal of flu forecasting is to provide a more-timely and forward-looking tool that health officials can use to target medical interventions, inform earlier public health actions, and allocate resources for communications, disease prevention and control. The potential benefits of flu forecasting are significant.

Since 2013, the Influenza Division at the Centers for Disease Control and Prevention has worked with external researchers to improve the science and usability of influenza forecasts by coordinating seasonal influenza prediction challenges for the United States as a whole and for the 10 Health and Human Services Regions. This work includes defining prediction targets, facilitating data access, establishing evaluation metrics to assess accuracy, and developing forecast visualizations.

Multiple outside research teams have developed different flu forecasting models that will provide flu activity forecasts to CDC for the 2017-18 influenza season. This respisitory houses the weekly influenza activity forecasts provided by the various research teams. It’s important to note that these are not CDC forecasts and that the forecasts on this website are not endorsed by CDC. These forecasts are based on different models, can vary significantly, and may be inaccurate.

# Forecast Targets
For each week during the season, participants will be asked to provide national and regional probabilistic forecasts for the entire influenza season (seasonal targets) and for the next four weeks (four-week ahead targets). The seasonal targets are the onset week, the peak week, and the peak intensity of the 2017-18 influenza season. The four-week ahead targets are the percent of outpatient visits experiencing influenza-like illness (ILI) one week, two weeks, three weeks, and four weeks ahead from date of the forecast.

## Onset Week
**Definition:** The onset of the season is defined as the MMWR surveillance week when the percentage of visits for influenza-like illness (ILI) reported through ILINet reaches or exceeds the baseline value for three consecutive weeks (updated 2017-18 ILINet baseline values for the US and each HHS region will be available the week of October 9, 2017). Forecasted "onset" week values should be for the first week of that three week period.

**Motivation:** Accurate and timely forecasts for the start of the season can be useful in planning for influenza prevention and control activities. For the general public, the start of the season offers an important opportunity to take preventive measures, such as getting vaccinated, before flu becomes widespread. For clinicians and public health authorities, the start of the season indicates that influenza should be high on their list of possible diagnoses for patients with respiratory illness. This is particularly important for the management of hospitalized patients and high-risk patients with suspected influenza when early treatment with influenza antivirals can be critical.

## Seasonal Peak Week
**Definition:** The peak week will be defined as the MMWR surveillance week that the weighted ILINet percentage, rounded to one decimal place, is the highest for the 2017-18 influenza season.

**Motivation:** Accurate and timely forecasts for the peak week can be useful for planning and promoting activities to increase influenza vaccination prior to the bulk of influenza illness. For healthcare, pharmacy, and public health authorities, a forecast for the peak week can guide efficient staff and resource allocation.

## Seasonal Peak Intensity
**Definition:** The intensity will be defined as the highest numeric value, rounded to one decimal place, that the weighted ILINet percentage reaches during the 2017-18 influenza season.

**Motivation:** Accurate and timely forecasts for the peak week and intensity of the influenza season can be useful for influenza prevention and control, including the planning and promotion of activities to increase influenza vaccination prior to the bulk of influenza illness. For healthcare, pharmacy, and public health authorities, a forecast for the peak week and intensity can help with appropriate staff and resource allocation since a surge of patients with influenza illness can be expected to seek care and receive treatment in the weeks surrounding the peak.

## Short Term Forecasts
**Definition:** One- to four-week ahead forecasts will be defined as the weighted ILINet percentage for the target week, rounded to one decimal place.

**Motivation:** Forecasts capable of providing reliable estimates of influenza activity over the next month are critical because they allow healthcare and public health officials to prepare for and respond to near-term changes in influenza activity and bridge the gap between reported incidence data and long-term seasonal forecasts.

# ILINet Data
Data on the weekly proportion of people seeing their health-care provider for influenza-like illness (ILI) is reported through the [ILINet System](https://www.cdc.gov/flu/weekly/overview.htm#anchor_1539281266932) for the United States as a whole and for each HHS health region. These data can be accessed directly from [CDC](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html) or the R package cdcfluview

# Forecast Evaluation
All forecasts will be evaluated using the weighted observations pulled from the ILINet system in week 28, and the logarithmic score will be used to measure the accuracy of the probability distribution of a forecast. Logarithmic scores will be averaged across different time periods, the seasonal targets, the four-week ahead targets, and locations to provide both specific and generalized measures of model accuracy. Forecast accuracy will be measured by log score only. Nonetheless, forecasters are requested to continue to submit point predictions, which should aim to minimize the absolute error (AE).

## Logarithmic Score
If p is the set of probabilities for a given forecast, and pi is the probability assigned to the observed outcome i, the logarithmic score is:

S(p,i)=ln(pi)

For onset week and peak week, the probability assigned to that correct bin (based on the weighted ILINet value) plus the probability assigned to the preceding and proceeding bins will be summed to determine the probability assigned to the observed outcome. In the case of multiple peak weeks, the probability assigned to the bins containing the peak weeks and the preceding and proceeding bins will be summed. For peak percentage and 4-weeks-ahead forecasts, the probability assigned to the correct bin plus the probability assigned to the five preceding and five proceeding bins will be summed to determine the probability assigned to the observed outcome. For example, if the correct peak ILINet value is 6.5%, the probabilities assigned to all bins ranging from 6.0% to 7.0% will be summed to determine the probability assigned to the observed outcome.

For all targets, if the correct bin is near the first or last bin, the number of bins summed will be reduced accordingly. No bin farther than one bin (onset and peak week) or five bins away (percentage forecasts) from the correct bin will contribute to the score. For example, if the correct ILINet percentage for a given week is 0.3%, probabilities assigned to bins ranging from 0% to 0.8% will be summed. Undefined natural logs (which occur when the probability assigned to the observed outcome was 0) will be assigned a value of -10. Forecasts which are not submitted (e.g. if a week is missed) or that are incomplete (e.g. sum of probabilities greater than 1.1) will also be assigned a value of -10.

Example: A forecast predicts there is a probability of 0.2 (i.e. a 20% chance) that the flu season starts on week 44, a 0.3 probability that it starts on week 45, and a 0.1 probability that it starts on week 46 with the other 0.4 (40%) distributed across other weeks according to the forecast. Once the flu season has started, the prediction can be evaluated, and the ILINet data show that the flu season started on week 45. The probabilities for week 44, 45, and 46 would be summed, and the forecast would receive a score of ln(0.6)=−0.51. If the season started on another week, the score would be calculated on the probability assigned to that week plus the values assigned to the preceding and proceeding week.

# References
Gneiting T and AE Raftery. (2007) Strictly proper scoring rules, prediction, and estimation. Journal of the American Statistical Association. 102(477):359-378. Available at: https://www.stat.washington.edu/raftery/Research/PDF/Gneiting2007jasa.pdf

Rosenfeld R, J Grefenstette, and D Burke. (2012) A Proposal for Standardized Evaluation of Epidemiological Models. Available at: http://delphi.midas.cs.cmu.edu/files/StandardizedEvaluationRevised12-11-09.pdf.
