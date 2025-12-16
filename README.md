# Body Fat Percentage Prediction

This project focuses on predicting **body fat percentage** using anthropometric and demographic features.  
Due to the relatively small dataset size (~250 samples), special attention is given to **data preprocessing, augmentation, and model robustness**.

---

## 📌 Problem Definition

Body fat percentage is a critical indicator of health and fitness.  
The goal of this project is to build a **regression model** that can accurately estimate body fat percentage based on physical measurements.

---

## 📊 Dataset Overview

- Approx. **250 samples**
- Numerical features such as:
  - Age
  - Weight
  - Height
  - Body measurements (e.g., waist, hip, chest, etc.)
- Target variable:
  - **Body Fat Percentage**

---

## ⚙️ Preprocessing Steps

1. **Train–Test Split**
   - Data is split before any transformation to avoid data leakage.

2. **Feature Scaling**
   - `MinMaxScaler` is applied to numerical features.
   - Scaling is fitted **only on the training set**.

3. **Data Augmentation**
   - Gaussian noise is added to **scaled training data only**.
   - Purpose:
     - Improve generalization
     - Reduce overfitting on small datasets
   - Test set remains untouched.

---

## 🧪 Data Augmentation Strategy

Gaussian noise augmentation is applied as follows:

- Noise is sampled from a normal distribution
- Small noise levels are used to preserve physical meaning
- Augmentation is applied **after scaling**, **before model training**

This approach helps stabilize linear and kernel-based models.

---

## 🤖 Models Used

The following regression models are evaluated:

- **Linear Regression** (baseline)
- **Ridge Regression**
- **Lasso Regression**
- **ElasticNet**
  
---

## 🔍 Hyperparameter Optimization

- **RandomizedSearchCV**
- 5-fold cross-validation
- Scoring metric:
  - **R² score**
- Augmentation and scaling are applied consistently during tuning.

---

## 📈 Evaluation Metrics

Models are evaluated using:

- **R² Score** – overall explanatory power
- **MAE (Mean Absolute Error)** – interpretability in real units

Additionally:
- **Prediction vs Real scatter plots** are used for visual evaluation.

---

## 📉 Visualization

- Real vs Predicted scatter plots
  
---

## 🧠 Key Insights

- Data augmentation provides **small but consistent improvements** for:
  - Ridge
  - ElasticNet
  - Lasso
  - Linear Regression
- Over-aggressive noise harms performance.
- Proper preprocessing order is crucial for valid results.

---

## 🛠 Technologies Used

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib / Seaborn
- Scipy
  
---
