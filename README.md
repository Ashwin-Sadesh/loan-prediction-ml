# Personal Loan Prediction Using Machine Learning

## 📌 Project Overview

This project focuses on predicting whether a customer is likely to accept a personal loan offer based on their demographic, financial, and banking-related attributes.

The project uses the **Thera Bank personal loan dataset**, containing **5,000 customer records and 14 variables**. Exploratory Data Analysis (EDA), data preprocessing, feature analysis, and multiple classification algorithms are applied to develop and evaluate predictive models.
The primary objective is to compare different classification techniques and identify a model that can effectively identify customers who are likely to accept a personal loan.

---

## 🎯 Objectives

* Explore and understand customer demographic and financial data
* Identify missing values, unusual values, and potential outliers
* Analyze relationships between customer characteristics and personal loan acceptance
* Perform data preprocessing and feature preparation
* Build multiple machine learning classification models
* Compare model performance using accuracy, precision, recall, confusion matrices, ROC curves, and AUC
* Identify an appropriate model for personal loan prediction

---

## 📊 Dataset

The dataset contains **5,000 records and 14 columns**.

### Key Features

| Feature              | Description                                               |
| -------------------- | --------------------------------------------------------- |
| `Age`                | Customer age                                              |
| `Experience`         | Years of professional experience                          |
| `Income`             | Annual income                                             |
| `ZIP Code`           | Customer ZIP code                                         |
| `Family`             | Family size                                               |
| `CCAvg`              | Average monthly credit card spending                      |
| `Education`          | Education level                                           |
| `Mortgage`           | Mortgage value                                            |
| `Securities Account` | Whether the customer has a securities account             |
| `CD Account`         | Whether the customer has a certificate of deposit account |
| `Online`             | Whether the customer uses online banking                  |
| `CreditCard`         | Whether the customer uses a bank credit card              |
| `Personal Loan`      | Target variable indicating personal loan acceptance       |

The `ID` field is treated as an identifier rather than a predictive feature.

---

## 🔍 Exploratory Data Analysis

The analysis examines:

* Dataset structure and data types
* Missing values
* Target class distribution
* Descriptive statistics
* Distribution of numerical variables
* Outliers
* Relationships between features
* Categorical variables represented numerically

The target variable is imbalanced:

* **Class 0:** 4,520 customers
* **Class 1:** 480 customers

This class imbalance is an important consideration when evaluating model performance.

---

## 🧹 Data Preprocessing

Several data-quality and preprocessing steps were performed.

### Negative Experience Values

The dataset contained **52 records with negative values in the `Experience` column**. Since negative professional experience is not meaningful in this context, these values were replaced with `0`.

### Outlier Analysis

Potential outliers were investigated using descriptive statistics, boxplots, and the IQR method.

For example, the analysis identified **96 records with Income values above the calculated upper bound of 186.5**.

### Categorical Variables

Variables such as `ZIP Code`, `Education`, `Securities Account`, `CD Account`, `Online`, and `CreditCard` contain categorical information despite being numerically represented. The notebook therefore examines their treatment before model development.

---

## 🤖 Machine Learning Models

Three classification algorithms were implemented and compared:

### 1. K-Nearest Neighbors (KNN)

KNN was implemented as a distance-based classification algorithm. Feature scaling was considered because distance-based models are sensitive to differences in feature magnitude.

### 2. Logistic Regression

Logistic Regression was used as a linear classification approach for predicting the probability of personal loan acceptance.

### 3. Naive Bayes

Naive Bayes was implemented as an additional probabilistic classification approach.

---

## 📈 Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* Confusion Matrix
* ROC Curve
* Area Under the ROC Curve (AUC)

Because the dataset is imbalanced, accuracy alone is not sufficient to evaluate the models. Precision and recall for the positive class are also considered.

---

## 🏆 Results

| Model               | Accuracy | Precision | Recall | ROC-AUC |
| ------------------- | -------: | --------: | -----: | ------: |
| KNN                 |   96.47% |    92.93% | 66.67% |  0.9045 |
| Logistic Regression |        — |         — |      — |  0.9355 |
| Naive Bayes         |        — |         — |      — |  0.7864 |

KNN achieved a **96.47% test accuracy**, with **92.93% precision** and **66.67% recall** for the positive class.

Logistic Regression achieved the highest ROC-AUC among the evaluated models at **0.9355**, while Naive Bayes achieved an ROC-AUC of **0.7864**.

The notebook compares these results based on the business objective and the importance of identifying customers who may accept a personal loan.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Jupyter Notebook**



