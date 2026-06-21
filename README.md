# Customer Churn Prediction using PySpark & Google Cloud Platform

Predicting customer churn using machine learning and scalable cloud analytics on datasets ranging from 50,000 to 1,000,000 customer records.

## Project Overview

Customer retention is one of the most critical challenges faced by subscription-based businesses. Acquiring new customers is often more expensive than retaining existing ones, making churn prediction an essential business capability.

In this project, I developed and evaluated machine learning models to predict customer churn using both small-scale and large-scale datasets. The solution was first developed and tested in Google Colab and then deployed on Google Cloud Platform (GCP) using Dataproc and PySpark to demonstrate scalable analytics.

The project compares the performance of Logistic Regression, Decision Tree, and Random Forest models on datasets ranging from 50,000 to 1,000,000 customer records.

---

## Project Highlights

- Built end-to-end customer churn prediction pipeline
- Processed datasets up to 1,000,000 customer records
- Developed and evaluated 3 machine learning models
- Deployed solution on Google Cloud Dataproc using PySpark
- Achieved ROC-AUC of 0.7407 using Random Forest
- Demonstrated scalable analytics from local development to cloud deployment

## Business Problem

Customer churn occurs when customers discontinue a product or service. Organizations that can identify customers at risk of leaving can proactively engage them through retention campaigns, loyalty programs, and personalized offers.

### Project Goals

* Predict customer churn using machine learning.
* Compare multiple classification algorithms.
* Evaluate model performance using Accuracy, F1 Score, and ROC-AUC.
* Demonstrate scalable analytics using PySpark and Google Cloud Dataproc.
* Compare performance on small and big datasets.

---

## Dataset Summary

| Dataset | Records | Features |
|----------|----------|----------|
| Small Dataset | 50,000 | 17 |
| Big Dataset | 1,000,000 | 17 |

### Key Feature Categories

| Category | Features |
|-----------|-----------|
| Customer Profile | Customer_Tenure, Partner_Status, Dependents |
| Billing Information | Monthly_Charges, Total_Charges, Payment_Method |
| Service Information | Internet_Service_Type, Online_Security, Tech_Support |
| Account Information | Contract_Type, Paperless_Billing, Customer_Segment |
| Target Variable | Churn |

---

## Project Architecture

```text
Google Colab
      │
      ▼
Data Exploration & Feature Engineering
      │
      ▼
Google Cloud Storage (GCS)
      │
      ▼
Google Dataproc Cluster
      │
      ▼
PySpark ML Pipeline
      │
      ▼
Machine Learning Models
      │
      ▼
Customer Churn Prediction
```

## Project Workflow

### 1. Data Exploration

* Data quality assessment
* Missing value analysis
* Schema validation
* Class distribution analysis

### Churn Distribution

<img width="690" height="490" alt="image" src="https://github.com/user-attachments/assets/ca0a119a-20fd-43a9-908b-efeffba61002" />

### Contract Type vs Churn

<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/6c079e78-ec31-4e0a-8dec-9227596e488d" />

Insights:
- Month-to-month customers show higher churn.
- Long-term contracts demonstrate better retention.
- Contract type is a strong churn indicator.

### Internet Service Type vs Churn

<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/6c1e9a0f-c76f-43ae-87e9-7718b9acaf69" />

### Correlation Heatmap

<img width="574" height="497" alt="image" src="https://github.com/user-attachments/assets/21a600ae-74de-447e-bb0d-fd4d75d4453f" />

Insights:
- Total Charges strongly correlate with Tenure.
- Monthly Charges show moderate relationships.
- No severe multicollinearity observed.
  
### 2. Data Preprocessing

* Handling missing values
* Categorical feature encoding
* Feature assembly using PySpark
* Train-test split

### 3. Machine Learning Models

The following models were developed and evaluated:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier

### 4. Model Evaluation Metrics

* Accuracy
* F1 Score
* ROC-AUC

---

## Results

### Small Dataset (50,000 Records)

| Model               | Accuracy | F1 Score | ROC-AUC |
| ------------------- | -------- | -------- | ------- |
| Logistic Regression | 0.6691   | 0.6686   | 0.7289  |
| Decision Tree       | 0.6801   | 0.6782   | 0.6443  |
| Random Forest       | 0.6678   | 0.6649   | 0.7348  |

### Big Dataset (1,000,000 Records)

| Model               | Accuracy | F1 Score | ROC-AUC |
| ------------------- | -------- | -------- | ------- |
| Logistic Regression | 0.6757   | 0.6754   | 0.7333  |
| Decision Tree       | 0.6829   | 0.6815   | 0.6495  |
| Random Forest       | 0.6791   | 0.6776   | 0.7407  |

---

### Best Performing Models

| Metric | Best Model |
|----------|----------|
| Accuracy | Decision Tree |
| F1 Score | Decision Tree |
| ROC-AUC | Random Forest |

Random Forest achieved the highest ROC-AUC score of 0.7407, making it the strongest model for identifying churn-prone customers.

### Small Dataset

* Decision Tree achieved the highest Accuracy and F1 Score.
* Random Forest achieved the highest ROC-AUC score.

### Big Dataset

* Model performance improved with increased data volume.
* Random Forest achieved the highest ROC-AUC (0.7407).
* Decision Tree achieved the highest Accuracy and F1 Score.

### Model Performance Comparison

<img width="2700" height="1500" alt="model_comparison" src="https://github.com/user-attachments/assets/72557ed3-72a9-45c1-a8e5-5ab3a91981a3" />

### Business Insights

* Machine learning can effectively identify customers at risk of churn.
* Larger datasets generally improve predictive performance.
* Predictive churn models can support proactive customer retention strategies.
* Organizations can prioritize retention efforts toward high-risk customers.

---

## Google Cloud Implementation

The project was developed locally using Google Colab and scaled to Google Cloud Platform for distributed processing and machine learning.

### Google Cloud Storage (GCS)

<img width="1424" height="796" alt="GCS Bucket" src="https://github.com/user-attachments/assets/eba4a677-5cc4-45e4-8f55-5c85ab4a3908" />

Used as the centralized storage layer for datasets and project artifacts.

### Google Dataproc

<img width="1433" height="767" alt="Dataproc Cluster" src="https://github.com/user-attachments/assets/fb899950-4425-450f-abf7-a8090da4d4cd" />

Used to execute PySpark workloads on distributed infrastructure.

### PySpark ML

### PySpark ML Pipeline Execution

Executed machine learning workflows and model evaluation on cloud resources.

<img width="1411" height="788" alt="PART-B-1_GCP_Lab5_ProductionEnv" src="https://github.com/user-attachments/assets/dbf12da3-5570-4042-a95e-7fc0e9d72555" />

This deployment demonstrated how the same analytics workflow can scale from a local development environment to a distributed cloud environment with minimal code changes.

---

## Repository Contents

| Folder | Description |
|---------|-------------|
| notebooks | Data exploration, preprocessing, and machine learning workflows |
| reports | Final project report and supporting documentation |
| images | Visualizations, cloud deployment screenshots, and project assets |
| README.md | Project overview and documentation |
---

## Future Improvements

* Hyperparameter tuning
* Feature importance analysis
* Customer segmentation integration
* Real-time churn prediction pipeline
* Model deployment using cloud APIs
* Interactive business dashboard

---

## Learning Outcomes

Through this project, I gained hands-on experience with:

* Customer Analytics
* Predictive Modeling
* PySpark Machine Learning
* Google Cloud Platform
* Distributed Data Processing
* Model Evaluation
* Big Data Analytics
* Business Problem Solving

---

## Technology Stack

* Python
* PySpark
* Scikit-Learn
* Google Colab
* Google Cloud Platform (GCP)
* Google Cloud Storage (GCS)
* Google Dataproc
* Pandas
* NumPy

---

## Skills Demonstrated

- Machine Learning
- Customer Analytics
- Predictive Modeling
- PySpark
- Big Data Analytics
- Google Cloud Platform
- Dataproc
- Google Cloud Storage
- Data Preprocessing
- Model Evaluation
- Business Analytics

## Author

Anand Chamoli

B.S. Data Science (Business Analytics)

Arizona State University

GitHub: https://github.com/AnandChamoli
