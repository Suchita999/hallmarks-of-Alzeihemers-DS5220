# Supervised Machine Learning
# hallmarks-of-Alzeihemers

Alzheimer’s disease (AD) is an incredibly complex and presently incurable age-related brain disorder. To better understand this debilitating disease, we collated and performed a meta-analysis on publicly available proteomics, and microRNA samples derived from AD patients and non-AD controls. From the samples originating from brain tissues and blood remained after applying quality filters. Since disease progression in AD correlates with age, we tried to stratify this large dataset into three different age groups: < 75 years, 75–84 years, and ≥ 85 years.

## MODELS USED:
-> Linear Regression
-> Random Forest
-> Decision Tree

## Model Comparision
Mean Square Error, Mean Absolute Error and R-Sqaure
 -----------------------------------------------------------------------
|          |  Linear Regression   |   Random Forest   |  Decision Tree   |
|----------|-------------------------------------------------------------|
| MAE      |      1.802           |     0.325         |   0.341          |
| MSE      |      1.094           |     0.325         |   0.341          |
| R-Square |     -7.212           |    -0.554         |  -0.554          |
 -----------------------------------------------------------------------

CLASSIFICATION REPORT
For Random Forest and Decison Tree
 --------------------------------------------
|          |  Random Forest |  Decision Tree |
|--------------------------------------------|
| Accuracy |    0.67        |    0.67        |
| Recall   |    1.00        |    0.96        |
| f1-score |    0.81        |    0.79        |
 --------------------------------------------


## CONCLUSION
Many of the results demonstrated unique age-specificity. For example, terms highlighting cellular senescence only emerged in the earliest and intermediate age ranges while the majority of results relevant to cell death appeared in the youngest patients.

## Group Members
- Suchita Sharma (sharma.such@northeastern.edu)
- Rima Zinjuwadia (zinjuwadia.r@northeastern.edu)
