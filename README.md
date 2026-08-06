# Customer Segmentation using Autoencoder and K-Means

## Overview

Customer segmentation is a fundamental business problem in retail and e-commerce. Traditional clustering techniques such as K-Means often struggle to capture complex relationships between customer behaviors. This project compares a baseline K-Means model with an Autoencoder-based feature representation to evaluate whether learned latent features produce more meaningful customer segments.

The project follows a complete end-to-end machine learning workflow, including data understanding, feature engineering, preprocessing, clustering, deep learning, business interpretation, and model comparison.

---

# Business Problem

Businesses serve customers with different purchasing behaviors, spending patterns, and satisfaction levels. Treating every customer identically reduces marketing effectiveness and customer retention.

The objective of this project is to identify meaningful customer segments that can support:

* Personalized marketing
* Customer retention strategies
* Premium customer identification
* Cross-selling opportunities
* Customer experience improvement

---

# Dataset

**Source:** Brazilian E-Commerce Public Dataset (Olist)

The project combines information from multiple relational datasets, including:

* Customers
* Orders
* Order Items
* Payments
* Reviews
* Products

These datasets were integrated to create a customer-level analytical dataset.

---

# Project Pipeline

```
Raw Data
      ↓
Data Understanding
      ↓
Feature Engineering
      ↓
Feature Selection
      ↓
Data Preprocessing
      ↓
Baseline K-Means
      ↓
Autoencoder
      ↓
Latent Feature Extraction
      ↓
K-Means on Latent Space
      ↓
Business Comparison
```

---

# Feature Engineering

Customer-level features were engineered from transactional data, including:

* Recency
* Frequency
* Monetary Value
* Total Items Purchased
* Average Installments
* Average Review Score
* Review Coverage
* Product Diversity
* Category Diversity
* Seller Diversity
* Freight-to-Merchandise Ratio

Thirty-five engineered features were created initially. After exploratory analysis and feature selection, the final modeling dataset contained **11 features**.

---

# Data Preprocessing

The preprocessing pipeline included:

* Missing value imputation using Median
* RobustScaler for feature scaling
* Validation of missing values
* Validation of duplicate records

RobustScaler was selected because several purchase-related variables were highly skewed and contained outliers.

---

# Baseline Model

The baseline segmentation model used:

* K-Means Clustering
* Elbow Method
* Silhouette Score
* Business interpretation of clusters

The final baseline model used **4 customer segments**.

---

# Autoencoder Model

A compact PyTorch Autoencoder was developed to learn a lower-dimensional customer representation.

Architecture:

```
11
 ↓
8
 ↓
4 (Latent Space)
 ↓
8
 ↓
11
```

The encoder compressed the original customer features into a 4-dimensional latent representation before clustering.

---

# Model Comparison

Two clustering approaches were evaluated.

## Baseline

* Original engineered features
* K-Means

## Proposed Model

* Autoencoder latent features
* K-Means

The comparison focused on business interpretability rather than only statistical metrics.

---

# Key Findings

Baseline K-Means successfully identified:

* Budget Customers
* Premium Customers
* Regular Customers
* Dissatisfied Customers

The Autoencoder-based approach identified:

* Mass-Market Customers
* Medium-Value Customers
* High-Value Customers
* A very small VIP customer segment with exceptionally high spending

The learned latent representation provided more differentiated purchasing behavior, particularly by isolating a distinct VIP segment.

---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* PyTorch
* Joblib
* Jupyter Notebook

---

# Project Structure

```
Customer-Segmentation-Autoencoder
│
├── data
│   ├── raw
│   └── processed
│
├── notebooks
│   ├── 01_data_understanding.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_eda_feature_selection.ipynb
│   ├── 04_preprocessing.ipynb
│   ├── 05_baseline_kmeans.ipynb
│   ├── 06_autoencoder.ipynb
│   ├── 07_latent_space_clustering.ipynb
│   └── 08_model_comparison_and_business_insights.ipynb
│
├── models
│   ├── baseline_kmeans.pkl
│   └── encoder.pt
│
├── images
├── requirements.txt
└── README.md
```

---

# Results

* Engineered customer-level behavioral features from multiple relational datasets.
* Built an end-to-end customer segmentation pipeline.
* Established a baseline K-Means clustering solution.
* Developed a PyTorch Autoencoder for nonlinear feature representation.
* Compared baseline and latent-space clustering results.
* Identified actionable customer segments for business decision-making.

---

# Future Improvements

Possible extensions include:

* Hyperparameter optimization
* Alternative clustering algorithms (Gaussian Mixture Models, HDBSCAN)
* Cluster stability analysis
* Interactive customer segmentation dashboard
* Automated deployment using FastAPI or Streamlit

---

# Author

**Amol Dangat**

Data Scientist | Machine Learning | Deep Learning | NLP | Generative AI

LinkedIn: *Add your LinkedIn profile*

GitHub: *Add your GitHub profile*
