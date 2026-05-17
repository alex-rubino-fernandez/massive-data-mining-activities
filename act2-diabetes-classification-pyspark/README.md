# Actividad 2: PySpark, MLlib y pipelines para clasificación

## Overview

This activity consists of building a binary classification model to predict diabetes using medical diagnostic data. The implementation uses PySpark MLlib with a complete machine learning pipeline, including feature vectorization, data scaling, and logistic regression.

**Note:** The notebook (`act2-grupal.ipynb`) is written in Spanish, as it is the vehicular language of the course.

## Technologies Used

- **PySpark** - Distributed data processing and ML
- **MLlib** - Machine learning library (VectorAssembler, StandardScaler, LogisticRegression)
- **Matplotlib / Seaborn** - Data visualization (histograms, heatmaps, confusion matrix)
- **Jupyter Notebook** - Interactive development environment

## Dataset

The dataset `diagnostico_diabetes 1.csv` contains medical information of 768 patients with the following features:

- `embarazos` - Number of pregnancies
- `glucosa en sangre` - Blood glucose level
- `presion sanguinea` - Blood pressure
- `grosor piel triceps` - Triceps skin fold thickness
- `insulina` - Insulin level
- `IMC` - Body mass index
- `ascendencia diabetes` - Diabetes pedigree function
- `edad` - Age
- `diabetes` - Target variable (VERDADERO/FALSO)

## Setup & Execution

1. Configure environment variables for Spark on Windows:
   - `JAVA_HOME` - Path to JDK 17
   - `HADOOP_HOME` - Path to Hadoop binaries
2. Initialize Spark session with local mode
3. Load the dataset from CSV (semicolon-separated)
4. Execute the notebook cells sequentially

## Summary of Tasks

- **Environment setup** - Configure Java, Hadoop, and Spark session
- **Exploratory data analysis** - Histograms and correlation heatmap
- **ML Pipeline implementation**:
  - `VectorAssembler` - Combine features into a single vector
  - `StandardScaler` - Normalize data (without centering due to zero values)
  - `LogisticRegression` - Binary classification model
- **Model evaluation** - AUC-ROC, confusion matrix, precision, recall, F1-Score

## Results

| Metric | Value |
|--------|-------|
| AUC-ROC | 0.8622 |
| Accuracy | 78.05% |
| Precision | 73.53% |
| Recall (Sensitivity) | 58.14% |
| F1-Score | 0.6494 |

**Key finding:** Glucose level shows the strongest correlation with diabetes (0.47), followed by BMI (0.29) and age (0.24).

## Limitations & Future Improvements

- **Low recall (58.14%)** - 18 false negatives (undetected diabetes cases)
- **Zero values** in medical variables likely represent missing data
- **Imbalanced dataset** - 65.1% negative vs 34.9% positive cases

**Proposed improvements:**
- Impute zero values with mean/median
- Balance classes using SMOTE or class weights
- Test alternative algorithms (Random Forest, XGBoost)

## Authors

- Alex Rubiño Fernández
- Ruben Artola Rangel
- Pablo Morales Pareja
- Santiago Martín Cabrera