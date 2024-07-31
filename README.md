# Supervised Machine Learning
# hallmarks-of-Alzeihemers

Alzheimer’s disease (AD) is an incredibly complex and presently incurable age-related brain disorder. To better understand this debilitating disease, we collated and performed a meta-analysis on publicly available proteomics, and microRNA samples derived from AD patients and non-AD controls. From the samples originating from brain tissues and blood remained after applying quality filters. Since disease progression in AD correlates with age, we tried to stratify this large dataset into three different age groups: < 75 years, 75–84 years, and ≥ 85 years.

## DATASET OVERVIEW
combinedSTARcounts.txt. contains STAR count data from RNA seq experiments. It lists the number of unmapped reads across different samples, with each column representing a specific sample. This raw count data will require further normalization and differential expression analysis.​

meta.txt provides experimental conditions, sample IDs, age, sex, diagnosis, tissue type, and batch information.​
​
Proteins.txt contains protein expression data across various samples. Each column represents a sample, with identifiers indicating the condition, sex, age, and disease stage. This data is important for studying the patterns of protein expression in relation to Alzheimer's disease.​

New_meta.csv provides experimental conditions, sample IDs, age, sex, diagnosis, tissue type, and batch information, genes, and proteins from combinedSTARcounts.csv and meta.csv​

## PROJECT WORKFLOW
<img width="439" alt="Screenshot 2024-07-31 at 12 43 33" src="https://github.com/user-attachments/assets/59b25472-bbd1-485e-92f2-3d6458146212">

## PREPROCESSING
Data Cleaning:
• Created new meta file with details of samples, gene, proteins. Which are present in different file.
• Generated three additional files for proteins with three groups: Young, Middle-age, and old age.
• Converted txt files to csv.
• Checked for missing values.
• Converted categorical values to numeric values using LabelEncoder().
• Calculated mean() for columns and replaced missing NaN values with the mean.
• Saved preprocessed files as new csv files for future use.

Normalization:
• Column names and protein lists.
• Checked for any mismatched column names.
• Filtered protein data by age groups : Young, Middle-age, and old age.
• Combined metadata with protein expression

Feature Engineering:
• Using LabelEncoder(), we changed the categorical values into numerical values such as ‘Sex’ , etc.
• Replaced the NA values with the mean of that specific column using fillna() and mean().

Preprocessed data based upon the age group Young(<74 years), Middle-Aged(74 - 85) and Old-Aged(>85)
<img width="791" alt="Screenshot 2024-07-31 at 17 05 27" src="https://github.com/user-attachments/assets/265c3928-9786-4868-80c0-7b14c42dddda">
<img width="824" alt="Screenshot 2024-07-31 at 17 05 34" src="https://github.com/user-attachments/assets/8f43d255-5151-4593-ad05-295435a85044">

## MODELS USED:
<img width="891" alt="Screenshot 2024-07-31 at 12 44 29" src="https://github.com/user-attachments/assets/041f8df0-9bf8-4953-b2e0-708beb4a0ec4">

## MODEL COMPARISON
|          |  Logistic Regression |   Random Forest   |  Decision Tree   | SVM   |
|----------|----------------------|-------------------|------------------|-------|
| MAE      |      0.341           |     0.325         |   0.341          | 0.325 |
| MSE      |      0.341           |     0.325         |   0.341          | 0.325 |
| R-Square |     -0.554           |    -0.554         |  -0.554          | -0.482|

Here negative R² value in the models indicates that none of the models are fitting the data well. This might be due to the models being inappropriate for the data.​
​
Both Random Forest and SVM show similar performance, slightly better than the Decision Tree, which may suggest that more sophisticated models (like ensembles or SVMs) are not adding significant value over simpler models.​
​
WHAT CAN BE DONE​...
Further steps could include revisiting the feature selection process, exploring data transformations, or considering alternative modeling approaches.​

|          |  Random Forest |  Decision Tree | SVM  |
|----------|----------------|----------------|------|
| Accuracy |    0.67        |    0.67        | 0.67 |
| Recall   |    1.00        |    0.96        | 1.00 |
| f1-score |    0.81        |    0.79        | 0.81 |

The F1 scores for Decision Tree and SVM are identical at 0.81, while the Random Forest is slightly lower at 0.79. This suggests that the Decision Tree and SVM models have a slightly better balance between precision and recall compared to the Random Forest.​

## RESULTS
- Confusion matrix  :  The model effectively detects Alzheimer's disease but struggles with identifying control samples, leading to many false positives. This highlights the need for better balancing and fine-tuning to accurately differentiate between the two groups.​
- ROC curve :  for this model has an AUC of 0.55, indicating it is just a bit better than random guessing. The dashed blue line, which shows random chance with an AUC of 0.5, acts as a reference point. ​
- To make the model better at distinguishing between outcomes, more improvements are needed​
Random Forest is the best model among the three, considering it has the best combination of MSE, MAE, recall, precision, and F1 Score. While Decision Tree is very close in performance, Random Forest slightly edges it out due to a marginally better R-squared value and generally better handling of variance.​

## CONCLUSION
- As people grow older, the levels of protein expression differ across various graphs, indicating a relationship between biological processes or protein markers and the aging process. ​
- Most of these proteins are associated with Biological Processes like cell death, oxidative stress, and immune system function, suggesting that aging is connected to increased cellular stress and immune activity. ​
- Understanding these changes can help identify potential targets for interventions designed to mitigate age-related decline.​
- Trained models improve diagnostic precision, helping to identify biomarkers for early intervention.​
- Metrics like accuracy, precision, recall, F1 score, and AUC-ROC curves assess model performance, guiding the selection of the best predictive model.​
In conclusion, Supervised learning enables researchers to gain deeper insights into Alzheimer's disease mechanisms, improve diagnostics, and develop personalized treatments.​

## Group Members
- Suchita Sharma (sharma.such@northeastern.edu)
- Rima Zinjuwadia (zinjuwadia.r@northeastern.edu)
