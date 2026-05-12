Heart Disease Analysis Description
 
 
PROJECT OVERVIEW
 
This project focuses on predicting whether a patient has heart disease based on clinical and diagnostic measurements. Using a dataset of 1,025 patient records sourced from the Cleveland Heart Disease database, a supervised machine learning model was built and evaluated to classify patients as either having heart disease or not. The goal was to demonstrate that non-invasive clinical measurements alone can provide meaningful predictive power for cardiac diagnosis.
 
 
DATASET
 
Source: Cleveland Heart Disease Database (UCI Machine Learning Repository / Kaggle)
Records: 1,025 patients
Features: 13 clinical predictors and 1 binary target variable
Target: 1 = Heart Disease, 0 = No Disease
 
 
MODEL
 
Algorithm: Random Forest Classifier
Tuning: GridSearchCV with 5-fold cross-validation optimizing ROC-AUC
Baseline: DummyClassifier using the most-frequent-class strategy
 
 
RESULTS
 
Baseline Accuracy: 54.1%
Random Forest Accuracy: 77.1%
ROC-AUC: 0.857
Precision - No Disease: 0.75
Precision - Heart Disease: 0.79
Recall - No Disease: 0.75
Recall - Heart Disease: 0.79
False Negatives: 7 out of 61 test patients
 
The model improved accuracy by over 23 percentage points above the baseline.
 
 
KEY FINDINGS
 
1. cp - Chest Pain Type (importance 0.20)
The strongest predictor of heart disease in this dataset. Patients reporting atypical chest pain patterns showed significantly higher disease rates, consistent with how physicians clinically assess cardiac risk.
 
2. thalach - Maximum Heart Rate (importance 0.13)
Patients with heart disease consistently showed lower maximum heart rates. A reduced ability to elevate heart rate during exercise is a known marker of cardiovascular impairment and reduced cardiac output.
 
3. ca - Number of Major Vessels (importance 0.11)
More vessels colored by fluoroscopy directly indicates arterial blockage. This is one of the most medically meaningful features in the dataset as it reflects the physical state of the coronary arteries.
 
4. thal - Thalassemia Type (importance 0.11)
Certain thalassemia defect types are strongly associated with reduced cardiac function. Bar charts confirmed clear differences in disease rate across thal values.
 
5. exang - Exercise-Induced Angina (importance 0.09)
Patients who experienced chest pain during exercise were far more likely to have heart disease, consistent with the clinical understanding that exertional angina signals insufficient blood supply to the heart.
 
 
CLINICAL SIGNIFICANCE
 
The balanced precision and recall scores of 0.75 and 0.79 indicate the model performs consistently across both classes without bias toward either outcome. In a real clinical setting, the 7 false negatives are the most critical metric. A missed heart disease diagnosis carries far greater risk than a false alarm, as it could result in a patient not receiving timely treatment.
 
The ROC-AUC of 0.857 means the model correctly ranks a randomly selected disease patient above a non-disease patient 85.7% of the time, making it a strong screening tool when used alongside physician judgment. The findings confirm that non-invasive clinical measurements alone can provide meaningful predictive power for heart disease classification.