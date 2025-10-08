# Heart Disease Prediction Project

## Project Overview

This project focuses on the exploratory data analysis (EDA) and binary classification modeling for predicting heart disease using a provided clinical dataset. The goal is to build and evaluate machine learning models to determine which patients are more likely to have heart disease.

The notebook performs the following key steps:
1.  **Data Loading and Initial Inspection**: Loading the data and checking for types and missing values.
2.  **Exploratory Data Analysis (EDA)**: Visualizing the distribution of key features, like age, and exploring relationships between variables like Cholesterol vs. Blood Pressure.
3.  **Data Preprocessing**: Checking for categorical features and preparing the data for modeling (though no object-type columns were found, the encoding logic is shown).
4.  **Model Training and Evaluation**: Training and comparing a **Logistic Regression** model and a **Random Forest Classifier**.
5.  **Feature Scaling**: Applying `StandardScaler` to the features and re-evaluating the Logistic Regression model.

## Dataset

The analysis uses the `heart_disease_dataset.csv` file.

| Feature | Description | Data Type | Non-Null Count |
| :--- | :--- | :--- | :--- |
| **age** | Age in years | `int64` | [cite_start]303 [cite: 616] |
| **sex** | Sex (1 = male; 0 = female) | `int64` | [cite_start]303 [cite: 619] |
| **cp** | Chest pain type (4 values) | `int64` | [cite_start]303 [cite: 623] |
| **trtbps** | Resting blood pressure (in mm Hg) | `int64` | [cite_start]303 [cite: 627] |
| **chol** | Serum cholestoral in mg/dl | `int64` | [cite_start]303 [cite: 631] |
| **fbs** | Fasting blood sugar > 120 mg/dl (1 = true; 0 = false) | `int64` | [cite_start]303 [cite: 635] |
| **restecg** | Resting electrocardiographic results (3 values) | `int64` | [cite_start]303 [cite: 639] |
| **thalachh** | Maximum heart rate achieved | `int64` | [cite_start]303 [cite: 643] |
| **exng** | Exercise induced angina (1 = yes; 0 = no) | `int64` | [cite_start]303 [cite: 647] |
| **oldpeak** | ST depression induced by exercise relative to rest | `float64` | [cite_start]303 [cite: 651] |
| **slp** | The slope of the peak exercise ST segment | `int64` | [cite_start]303 [cite: 654] |
| **caa** | Number of major vessels (0-3) colored by flourosopy | `int64` | [cite_start]303 [cite: 657] |
| **thall** | Thalassemia (3 values: 1, 2, 3) | `int64` | [cite_start]303 [cite: 660] |
| **output** | Target variable (0 = less chance of heart disease; 1 = greater chance) | `int64` | [cite_start]303 [cite: 663] |

[cite_start]The dataset contains **303 entries** and **no missing values** in any column[cite: 610, 616, 855].

## Methodology

### Exploratory Data Analysis (EDA)
* [cite_start]**Age Distribution**: A histogram was generated to show the distribution of patient ages[cite: 672, 673, 686].
* [cite_start]**Feature Relationships**: A scatter plot analyzed the relationship between 'Cholesterol' (`chol`) and 'Resting Blood Pressure' (`trtbps`)[cite: 850, 851, 884].
* **Target Analysis**:
    * [cite_start]A bar plot showed the **Average Age by Heart Disease** outcome[cite: 901, 902, 917].
    * [cite_start]A scatter plot visualized the **Maximum Heart Rate Achieved** (`thalachh`) against the `output` (Heart Disease)[cite: 1057].
    * [cite_start]A boxplot showed the **Cholesterol Distribution by Heart Disease**[cite: 1059].
    * [cite_start]A **Correlation Matrix** heatmap was created to visualize the correlation between all features[cite: 1060].

### Modeling
1.  [cite_start]**Data Split**: The data was split into training and testing sets with a `test_size=0.2` (80% train, 20% test)[cite: 1061].
    * [cite_start]**Training Set**: 242 samples[cite: 1061].
    * [cite_start]**Testing Set**: 61 samples[cite: 1061].
2.  [cite_start]**Model 1: Logistic Regression** (Baseline)[cite: 1062].
3.  [cite_start]**Model 2: Random Forest Classifier**[cite: 1063].
4.  [cite_start]**Model 3: Scaled Logistic Regression** (Features were scaled using `StandardScaler` before training)[cite: 1066, 1067].

## Results and Model Comparison

| Model | Accuracy | Precision | Recall | F1-score |
| :--- | :--- | :--- | :--- | :--- |
| **Logistic Regression** (Unscaled) | [cite_start]0.8033 [cite: 1065] | [cite_start]0.7692 [cite: 1065] | [cite_start]0.9091 [cite: 1065] | [cite_start]0.8333 [cite: 1065] |
| **Random Forest Classifier** | [cite_start]0.8361 [cite: 1066] | [cite_start]0.7805 [cite: 1066] | [cite_start]0.9697 [cite: 1066] | [cite_start]0.8649 [cite: 1066] |
| **Logistic Regression** (Scaled) | [cite_start]0.8197 [cite: 1068] | [cite_start]0.7805 [cite: 1068] | [cite_start]0.9394 [cite: 1068] | [cite_start]0.8525 [cite: 1068] |

[cite_start]The **Random Forest Classifier** achieved the highest overall performance, demonstrating the best **Accuracy** (0.8361) and **F1-score** (0.8649)[cite: 1066].

## Getting Started

### Prerequisites
You will need **Python 3** and the following libraries:
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn`

### Installation
You can install the required libraries using pip:
```bash
pip install pandas matplotlib seaborn scikit-learn
