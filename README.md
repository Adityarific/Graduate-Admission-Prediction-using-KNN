<div align="center">

# 🎓 Getting Admission in College Prediction

[![Python](https://img.shields.io/badge/Python-3.7+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/mohansacharya/graduate-admissions)


> Predicts whether a student is likely to get graduate college admission based on 7 academic and profile features using **K-Nearest Neighbors (KNN) Classification**.

[🔙 to Portfolio Repository](https://github.com/Adityarific/aditya-portfolio.git)

</div>

---

## 🔬 About the Project

Getting into a good graduate program is one of the most competitive processes for students worldwide. This project uses **K-Nearest Neighbors (KNN) Classification** to predict a student's admission outcome based on their academic and profile information.

The model uses seven features:

* GRE Score
* TOEFL Score
* University Rating
* SOP
* LOR
* CGPA
* Research Experience

The project focuses on understanding and implementing **KNN Classification** as a supervised machine learning algorithm for predicting a categorical admission outcome.

**What this project covers:**

* Exploratory Data Analysis on 500 graduate applicant profiles
* Data preprocessing and feature preparation
* Correlation and feature analysis
* Conversion of admission probability into classification categories
* Train/test data splitting
* Feature scaling
* KNN Classification implementation using scikit-learn
* Model evaluation using classification metrics
* Prediction of admission outcome for new applicants

---

## 📊 Dataset

| Property           | Details                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------- |
| **File**           | `admission_predict.csv`                                                                  |
| **Source**         | [Kaggle — Graduate Admissions](https://www.kaggle.com/mohansacharya/graduate-admissions) |
| **Rows**           | 500 student records                                                                      |
| **Columns**        | 9 (including Serial No. and target)                                                      |
| **Task**           | Classification — predict admission category                                              |
| **Missing Values** | None                                                                                     |

The original dataset contains academic and profile information about graduate applicants along with their corresponding **Chance of Admit**.

For this project, the `Chance of Admit` value is converted into a **categorical target** so that KNN Classification can be applied.

> **Note:** The exact classification threshold/categories used are defined in the Jupyter Notebook.

---

## 🔬 Features

| Column              | Type    |   Range   | Description                                                    |
| ------------------- | ------- | :-------: | -------------------------------------------------------------- |
| `GRE Score`         | Integer |  290–340  | Graduate Record Examination score                              |
| `TOEFL Score`       | Integer |   92–120  | Test of English as a Foreign Language score                    |
| `University Rating` | Integer |    1–5    | Prestige rating of undergraduate university                    |
| `SOP`               | Float   |  1.0–5.0  | Strength of Statement of Purpose                               |
| `LOR`               | Float   |  1.0–5.0  | Strength of Letter of Recommendation                           |
| `CGPA`              | Float   |  6.8–9.92 | Undergraduate GPA (out of 10)                                  |
| `Research`          | Binary  |   0 / 1   | Research experience (0 = No, 1 = Yes)                          |
| `Chance of Admit` ⭐ | Float   | 0.34–0.97 | Original admission probability used to create the target class |

> `Serial No.` is dropped before training as it does not provide useful predictive information.

---

## ⚙️ Methodology

```text
Load admission_predict.csv
          │
          ▼
Exploratory Data Analysis
(Distributions, correlations, visualizations)
          │
          ▼
Data Preprocessing
Drop 'Serial No.'
          │
          ▼
Convert Admission Probability
into Classification Classes
          │
          ▼
Define Features (X)
and Target (y)
          │
          ▼
Train/Test Split
80% Training / 20% Testing
          │
          ▼
Feature Scaling
(Standardization)
          │
          ▼
K-Nearest Neighbors
Classification Model
          │
          ▼
Model Evaluation
(Accuracy, Confusion Matrix,
Classification Report, etc.)
          │
          ▼
Prediction on New
Applicant Profiles
```

---

## 🤖 KNN Classification

This project uses **K-Nearest Neighbors (KNN) Classification** to predict the admission category of a student.

KNN is a **distance-based supervised learning algorithm**. Instead of learning an explicit mathematical equation, it compares a new data point with existing training examples and determines its class based on the nearest neighbors.

For a new applicant:

1. Calculate the distance between the new applicant and training samples.
2. Find the **K nearest neighbors**.
3. Check the classes of those neighbors.
4. Assign the class based on the **majority vote**.
5. Return the predicted admission category.

### Why KNN?

KNN was selected for this project to understand how a **distance-based classification algorithm** works on structured numerical data.

Since the features have different scales—for example, GRE scores range around 290–340 while SOP and LOR range from 1–5—**feature scaling** is important so that larger-valued features do not dominate the distance calculation.

### Basic KNN Workflow

```text
New Applicant
      │
      ▼
Calculate Distance
      │
      ▼
Find K Nearest Applicants
      │
      ▼
Majority Voting
Among Neighbors
      │
      ▼
Predicted Admission Class
```

---

## 🏆 Model Performance

The KNN Classification model is evaluated using standard classification metrics.

| Metric        |          Value         |
| ------------- | :--------------------: |
| Model         | `KNeighborsClassifier` |
| Training Data |           80%          |
| Testing Data  |           20%          |
| Evaluation    | Classification Metrics |

The model's performance can be evaluated using:

* **Accuracy Score**
* **Confusion Matrix**
* **Precision**
* **Recall**
* **F1-Score**
* **Classification Report**

> The exact performance scores are available in the Jupyter Notebook after training and evaluation.

---

## 🔮 Sample Predictions

```python
# Input:
# [GRE, TOEFL, University Rating, SOP, LOR, CGPA, Research]

model.predict([[337, 118, 4, 4.5, 4.5, 9.65, 0]])

model.predict([[320, 113, 2, 2.0, 2.5, 8.64, 1]])
```

The model returns a **class label** representing the predicted admission category rather than a continuous admission probability.

---

## 📁 Project Structure

```
Getting Admission in College Prediction/
│
├── Admission_prediction.ipynb      # Main notebook — EDA, model comparison, training
├── admission_predict.csv           # Dataset (500 student records)
├── requirements.txt                # Python dependencies
└── README.md                       # You are here
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Adityarific/Graduate-Admission-Prediction-using-KNN.git
```

### 2. Set up environment

```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows

pip install -r requirements.txt
```

### 3. Launch the notebook

```bash
jupyter notebook Admission_prediction.ipynb
```

---



## 🛠️ Tech Stack

| Layer           | Technology                   |
| --------------- | ---------------------------- |
| Language        | Python                       |
| ML Library      | scikit-learn                 |
| Model           | `KNeighborsClassifier`       |
| Data Processing | Pandas, NumPy                |
| Visualization   | Matplotlib                   |
| Notebook        | Jupyter                      |
| Dataset         | Kaggle — Graduate Admissions |

---
