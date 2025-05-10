# Breast Cancer Classification

## Overview

This project aims to classify breast cancer cases using machine learning models, with the dual purpose of **predicting the malignancy of tumors** and **comparing the performance of various classification models**. The goal is to predict whether a tumor is malignant or benign based on diagnostic features. Early and accurate classification of cancerous tumors plays a critical role in improving patient outcomes.

### Key Objectives:
1. **Predict breast cancer**: Develop models that can reliably predict whether a tumor is malignant or benign using features from cell nuclei measurements.
2. **Compare machine learning models**: Evaluate the performance of several machine learning algorithms on the breast cancer dataset and determine which model performs best in terms of accuracy, precision, recall, and F1-score.

## Dataset

The dataset used for this classification task comes from the **Breast Cancer Wisconsin (Diagnostic) Dataset**, which contains various features related to cell nuclei present in breast cancer biopsies. The dataset includes:

- **Features**: Mean values of various measurements (radius, texture, smoothness, compactness, etc.) from tumor cell properties.
- **Target Variable**: Tumor classification as either **malignant (M)** or **benign (B)**.

## Models Used

This project compares the performance of the following machine learning models:

1. **Support Vector Classifier (SVC)**
   - The **SVC** model was trained to maximize recall, ensuring that as many malignant tumors as possible are detected. This is especially important in cancer detection, where missing a malignant case could have serious consequences. However, this comes at the cost of slightly lower precision.

2. **Logistic Regression**
   - **Logistic Regression** was used as a baseline model, providing a solid balance between **precision** and **accuracy**. Though it does not perform as well in terms of recall compared to other models, it excels in minimizing false positives, which can be crucial in some medical applications.

3. **Random Forest Classifier (With and Without Feature Selection)**
   - **Random Forest** was trained in two different configurations:
     - **With Feature Selection** using **Recursive Feature Elimination (RFE)**.
     - **Without Feature Selection**, using all features.
   - Random Forest provides a robust ensemble method for classification, but its performance depends on feature selection and model configuration.

## Key Results

### Test Set Results:

- **SVC**: Achieved the highest recall (100%), which is essential for detecting all malignant cases in a medical context. However, its precision is slightly lower than other models, meaning it may misclassify some benign cases as malignant.
- **Random Forest** (with and without feature selection): Provided a solid balance between **precision** and **recall**, offering reliable results for tumor classification with minimal false positives. However, its recall was slightly lower than **SVC**.
- **Logistic Regression**: While performing well in terms of overall accuracy and precision, it has a lower recall than other models, meaning it may miss some cancerous cases.

### Cross-Validation Results:

- **Logistic Regression** showed the highest **accuracy** and **precision** in cross-validation, suggesting it is consistent and reliable across different data splits. However, it lags behind in **recall**, making it less effective in capturing all positive cases.
- **SVC** performed strongly in terms of **recall**, ensuring that malignant cases were not missed, though at the expense of precision.
- **Random Forest** models (especially the one without feature selection) demonstrated somewhat lower performance in **recall** and **accuracy**, suggesting that feature selection could enhance performance.
