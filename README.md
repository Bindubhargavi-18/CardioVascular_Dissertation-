
# Evaluation of Machine Learning and Deep Learning Models for Cardiovascular Disease Prediction with a Prototype Decision Support System

# Author Name : BinduBhargavi Madduluri
# Student id : 35054035
### 1. Project Overview

This dissertation develops and evaluates a Cardiovascular Disease (CVD)
prediction system using Machine Learning (ML) and Deep Learning (DL)
approaches. The project uses demographic, clinical and lifestyle
information to classify whether a patient is likely to have
cardiovascular disease.

The project combines predictive modelling, hyperparameter optimisation,
SHAP and LIME analysis, prototype development and human evaluation. The
purpose is to investigate model performance and demonstrate how the
selected model can be applied through a practical prediction prototype.

### 2. Aim

The aim of this project is to develop and evaluate a CVD prediction
system using ML and DL models, hyperparameter optimisation, explainable
artificial intelligence techniques and prototype-based human evaluation.

### 3. Main Objectives

1.  Prepare and analyse the CVD dataset.
2.  Develop baseline ML and DL prediction models.
3.  Evaluate the models using Accuracy, Precision, Recall, F1-Score and
    ROC-AUC.
4.  Apply hyperparameter optimisation and compare baseline and optimised
    models.
5.  Identify the best-performing model using F1-Score as the primary
    model-selection metric.
6.  Apply SHAP analysis to examine feature importance and feature
    contributions.
7.  Apply LIME analysis to examine individual prediction contributions.
8.  Develop a CVD prediction prototype.
9.  Test the prototype using different patient scenarios.
10. Conduct human evaluation to assess usability, prediction clarity,
    usefulness and confidence.

### 4. Dataset

The project uses a public cardiovascular disease dataset containing
demographic, clinical and lifestyle variables.

The main variables used in the modelling process include:

-   Age
-   Gender
-   Height
-   Weight
-   Systolic blood pressure
-   Diastolic blood pressure
-   Cholesterol
-   Glucose
-   Smoking
-   Alcohol consumption
-   Physical activity

The target variable represents the presence or absence of cardiovascular
disease.

Dataset-specific variables such as ap_hi and ap_lo represent systolic
and diastolic blood pressure respectively. BMI is derived from height
and weight.

### 5. Data Preparation

The dataset was examined before model development to identify its
structure, variables and data quality.

The main preparation stages were:

-   Dataset inspection
-   Missing-value assessment
-   Data-quality checking
-   Feature preparation
-   Target-variable preparation
-   Exploratory Data Analysis
-   Preparation of data for model training and testing

### 6. Models

The project evaluates both ML and DL approaches.

The evaluated models are:

-   Logistic Regression
-   LightGBM
-   CatBoost
-   Artificial Neural Network (ANN)

The models were evaluated using the same main performance criteria to
support a consistent comparison.

### 7. Evaluation Metrics

The following metrics were used:

-   Accuracy
-   Precision
-   Recall
-   F1-Score
-   ROC-AUC

F1-Score was selected as the primary metric for model selection because
it provides a balanced consideration of Precision and Recall.

### 8. Baseline Model Results

The baseline results were:

  -----------------------------------------------------------------------------
  Model            Accuracy    Precision       Recall     F1-Score      ROC-AUC
  ------------ ------------ ------------ ------------ ------------ ------------
  Baseline           0.7215       0.7234       0.7215       0.7207       0.7867
  Logistic                                                         
  Regression                                                       

  Baseline           0.7307       0.7315       0.7307       0.7304       0.7975
  LightGBM                                                         

  Baseline           0.7307       0.7317       0.7307       0.7303       0.7983
  CatBoost                                                         

  Baseline ANN       0.7247       0.7251       0.7247       0.7244       0.7881
  -----------------------------------------------------------------------------

Baseline LightGBM achieved the highest F1-Score of 0.7304. It was
therefore selected as the best-performing baseline model. CatBoost
produced a very similar F1-Score of 0.7303.

### 9. Optimised Model Results

The optimised results were:

  Model                   Accuracy   Precision   Recall   F1-Score   ROC-AUC
  --------------------- ---------- ----------- -------- ---------- ---------
  Logistic Regression       0.7215      0.7429   0.6688     0.7039    0.7867
  LightGBM                  0.7313      0.7449   0.6952     0.7192    0.7970
  CatBoost                  0.7306      0.7449   0.6930     0.7180    0.7975
  ANN                       0.7299      0.7418   0.6969     0.7186    0.7925

The optimisation results did not improve the primary F1-Score beyond the
baseline LightGBM result. Baseline LightGBM remained the strongest model
according to the selected F1-Score criterion.

### 10. Best-Performing Model

The best-performing model was Baseline LightGBM.

Its recorded performance was:

-   Accuracy: 0.7307
-   Precision: 0.7315
-   Recall: 0.7307
-   F1-Score: 0.7304
-   ROC-AUC: 0.7975

The F1-Score of 0.7304 was the principal reason for selecting this
model.

### 11. SHAP Analysis

SHAP analysis was applied to examine which features contributed most
strongly to the model output.

The global SHAP analysis identified the following major features:

1.  ap_hi
2.  cholesterol
3.  age
4.  age_years
5.  ap_lo
6.  weight
7.  BMI
8.  active
9.  gluc
10. id
11. smoke
12. height
13. alco
14. gender

Systolic blood pressure, represented by ap_hi, had the largest mean
absolute SHAP value. This indicates that ap_hi had the strongest overall
influence on the model output among the evaluated features.

The individual SHAP explanation also showed that an ap_hi value within
the 120 to 140 range contributed strongly to the displayed prediction,
while cholesterol and ap_lo also made positive contributions. Some
age-related variables made negative contributions for the displayed
patient instance.

### 12. LIME Analysis

LIME was used to examine an individual prediction produced by the
selected LightGBM model.

For the displayed test instance:

-   Actual Class: 1
-   Predicted Class: 1
-   Probability of Class 0: 0.1490
-   Probability of Class 1: 0.8510
-   Prediction Status: Correct

The strongest positive contributions included:

-   120.00 \< ap_hi \<= 140.00
-   cholesterol \> 1.00
-   alco \<= 0.00
-   weight \> 82.00
-   80.00 \< ap_lo \<= 90.00

The strongest negative contributions included:

-   age_years \<= 48.40
-   age \<= 17655.00

These results show how individual patient characteristics influenced the
specific prediction.

### 13. Prototype

A CVD prediction prototype was developed to demonstrate practical use of
the selected prediction model.

The prototype allows users to enter patient information including:

-   ID
-   Age
-   Gender
-   Height
-   Weight
-   Systolic blood pressure
-   Diastolic blood pressure
-   Cholesterol
-   Glucose
-   Smoking
-   Alcohol
-   Physical activity

The prototype provides:

-   Prediction
-   Confidence
-   Risk indication
-   BMI

### 14. Prototype Test Scenarios

The prototype was tested using different combinations of demographic,
clinical and lifestyle inputs.

The test scenarios demonstrated that changing important patient
characteristics can change the prediction output.

One scenario produced:

-   Prediction: No Cardiovascular Disease
-   Confidence: 86.78%
-   Risk: High
-   BMI: 22.49

A higher-risk scenario with increased blood pressure, cholesterol and
glucose, together with smoking and alcohol use, produced:

-   Prediction: Cardiovascular Disease
-   Confidence: 75.67%
-   Risk: Moderate
-   BMI: 22.49

These scenarios demonstrate the operation of the prototype rather than
clinical diagnosis.

### 15. Human Evaluation

Human evaluation was conducted with 150 participants to assess the
prototype from a user perspective.

The recorded average ratings were:

  Evaluation Factor        Average Rating
  ---------------------- ----------------
  Ease of Use                    4.67 / 5
  Prediction Clarity             4.73 / 5
  Usefulness                     4.78 / 5
  Confidence in Output           4.72 / 5
  Overall Rating                 4.88 / 5

The results indicate strong user acceptance of the prototype.
Participants evaluated the system positively in relation to ease of use,
clarity, usefulness and confidence.

### 16. Risk Management

The project considered key risks including:

-   Missing values
-   Class imbalance
-   Model overfitting
-   Poor predictive performance
-   Incorrect model output
-   Prototype failure
-   Participant misunderstanding
-   Privacy concerns

Mitigation activities included data preparation, model comparison,
validation, performance evaluation, prototype testing, clear user
instructions and appropriate handling of evaluation information.

### 17. Ethics

Ethical considerations were incorporated into the project, particularly
for the human evaluation of the prototype.

The evaluation was designed to obtain structured participant feedback on
usability and perceived usefulness. Participant information and consent
procedures were considered as part of the ethics process.

The prototype is a dissertation project and should not be treated as a
clinical diagnostic system.

### 18. Project Workflow

The overall workflow is:

Topic and Scope Definition

Literature Review

Research Gap Identification

Aim and Objectives

Ethics Documentation

Dataset Selection

Data Understanding

Data Preprocessing

Exploratory Data Analysis

Feature Preparation

Baseline Modelling

Model Evaluation

Hyperparameter Optimisation

Best Model Selection

SHAP Analysis

LIME Analysis

Prototype Development

Prototype Testing

Human Evaluation

Results Analysis

Dissertation Writing

Final Review

Appendices

Final Submission

### 19. Key Findings

The main findings of the project are:

-   Baseline LightGBM achieved the highest F1-Score.
-   The selected baseline LightGBM achieved an F1-Score of 0.7304.
-   Hyperparameter optimisation did not produce a higher F1-Score than
    the baseline LightGBM model.
-   SHAP identified systolic blood pressure as the most influential
    feature.
-   LIME demonstrated how individual patient characteristics contributed
    to a specific prediction.
-   The prototype successfully generated predictions for different test
    scenarios.
-   Human evaluation produced an overall rating of 4.88 out of 5.
-   The results support the practical feasibility of combining
    predictive modelling, model explanation, prototype development and
    human evaluation.

### 20. Limitations

The main limitations are:

-   The project relies on a single public dataset.
-   External validation using independent populations was not conducted.
-   The prototype is not a clinical diagnostic system.
-   The evaluation was based on the available dataset and test
    scenarios.
-   Human evaluation measures user perceptions rather than clinical
    effectiveness.
-   Further validation would be required before considering practical
    clinical deployment.

### 21. Future Work

Future work could include:

-   Testing the models on independent datasets.
-   Using larger and more diverse multicentre datasets.
-   Conducting prospective validation.
-   Assessing model calibration across different populations.
-   Evaluating subgroup performance.
-   Investigating multimodal cardiovascular data.
-   Exploring privacy-preserving collaborative learning.
-   Expanding human evaluation with healthcare professionals.
-   Testing the prototype in realistic clinical workflows.
-   Further improving model optimisation and validation.



### 22. Conclusion

This project developed and evaluated a complete CVD prediction workflow
covering data preparation, baseline modelling, optimisation, model
selection, SHAP analysis, LIME analysis, prototype development,
prototype testing and human evaluation. Baseline LightGBM achieved the
strongest F1-Score of 0.7304 and was selected as the best-performing
model. The prototype demonstrated practical prediction functionality,
while the human evaluation produced an overall rating of 4.88 out of 5.
The project therefore provides an integrated demonstration of CVD
prediction and evaluation using structured demographic, clinical and
lifestyle information.
