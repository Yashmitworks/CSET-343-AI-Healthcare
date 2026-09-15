Dermatology Disease Classification

Overview

This project aims to classify dermatology diseases using a machine learning approach. The dataset contains various clinical and histopathological features extracted from patients, and the goal is to build and evaluate multiple classification models to accurately predict the type of skin disease.

Dataset

The dataset, `dermatology_database_1.csv`, consists of 366 instances and 35 attributes. The first 34 attributes are clinical and histopathological features, while the last attribute is the target class (disease type). Missing values are represented by '?'.

Features:

*   `erythema`
*   `scaling`
*   `definite_borders`
*   `itching`
*   `koebner_phenomenon`
*   `polygonal_papules`
*   `follicular_papules`
*   `oral_mucosal_involvement`
*   `knee_and_elbow_involvement`
*   `scalp_involvement`
*   `family_history`
*   `melanin_incontinence`
*   `eosinophils_in_the_infiltrate`
*   `PNL_infiltrate`
*   `fibrosis_of_the_papillary_dermis`
*   `exocytosis`
*   `acanthosis`
*   `hyperkeratosis`
*   `parakeratosis`
*   `clubbing_of_the_rete_ridges`
*   `elongation_of_the_rete_ridges`
*   `thinning_of_the_suprapapillary_epidermis`
*   `spongiform_pustule`
*   `munro_microabcess`
*   `focal_hypergranulosis`
*   `disappearance_of_the_granular_layer`
*   `vacuolisation_and_damage_of_basal_layer`
*   `spongiosis`
*   `saw_tooth_appearance_of_retes`
*   `follicular_horn_plug`
*   `perifollicular_parakeratosis`
*   `inflammatory_monoluclear_infiltrate`
*   `band_like_infiltrate`
*   `age`

Target:

*   `class`: The type of dermatology disease (1-6).

Problem Statement

Given the clinical and histopathological features of a patient, the task is to build a multiclass classification model that can accurately predict the specific type of dermatology disease. This involves data preprocessing, exploratory data analysis, model selection, training, and evaluation.

Data Preprocessing and Exploratory Data Analysis (EDA)

The following steps were performed:

1.  **Data Loading**: The dataset was loaded using `pandas`, with '?' treated as missing values.
2.  **Column Renaming**: Meaningful column names were assigned to features and the target variable.
3.  **Data Type Conversion**: All feature columns and the target column were converted to numeric types, coercing errors to `NaN`.
4.  **Summary Statistics**: Basic information and descriptive statistics were displayed, including `mean`, `median`, `std`, `min`, `max`, and quartiles for all features.
5.  **Missing Values Handling**: Missing values in feature columns were imputed using the median strategy. Rows with missing target values were removed.
6.  **Duplicate Handling**: Duplicate rows were identified and removed from the dataset.
7.  **Outlier Detection**: Potential outliers in each feature were identified using the Interquartile Range (IQR) method.
8.  **Visualizations (EDA)**:
    *   **Box Plots**: Visualized the distribution and identified outliers for all features.
    *   **Histograms**: Displayed the distribution of each feature.
    *   **Correlation Heatmap**: Explored relationships between features.
    *   **Class Distribution**: Analyzed the distribution of disease classes using counts and percentages, and visualized it with a count plot.

Model Training and Evaluation

1.  **Feature and Target Separation**: `X` (features) and `y` (target) were separated.
2.  **Target Encoding**: The target variable `y` was encoded using `LabelEncoder` to convert disease classes (1-6) into numerical labels (0-5).
3.  **Data Splitting**: The dataset was split into training (80%) and testing (20%) sets using `train_test_split` with stratification to maintain class proportions.
4.  **Feature Scaling**: Features were standardized using `StandardScaler` to ensure uniform scale.
5.  **Model Selection**: The following multiclass classification models were chosen:
    *   K-Nearest Neighbors (KNN)
    *   Logistic Regression
    *   Random Forest Classifier
    *   Support Vector Machine (SVM)
6.  **Model Training**: Each model was trained on the scaled training data.
7.  **Prediction**: Predictions and probability estimates were generated for the test set.
8.  **Model Evaluation**: The performance of each model was assessed using the following metrics:
    *   **Accuracy**
    *   **Precision (weighted average)**
    *   **Recall (weighted average)**
    *   **F1-Score (weighted average)**
    *   **Classification Report**: Detailed per-class metrics.
    *   **Confusion Matrices**: Visual representation of model performance.
    *   **Multiclass ROC-AUC**: Calculated using the One-vs-Rest (OvR) strategy.
    *   **Multiclass ROC Curves**: Plotted for visual comparison.

Results

The evaluation metrics were consolidated, and models were ranked by F1-score. The Support Vector Machine (SVM) model emerged as the best-performing model based on the F1-score and other metrics:

| Model               | Accuracy | Precision | Recall   | F1-Score | Multiclass ROC-AUC |
|:--------------------|:---------|:----------|:---------|:---------|:-------------------|
| **SVM**             | 0.97     | 0.98      | 0.97     | 0.97     | 0.998              |
| Logistic Regression | 0.96     | 0.97      | 0.96     | 0.96     | 0.999              |
| Random Forest       | 0.96     | 0.96      | 0.96     | 0.96     | 0.998              |
| KNN                 | 0.91     | 0.92      | 0.91     | 0.91     | 0.987              |

Dependencies

*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`
*   `scikit-learn`
*   `google.colab.files`