# MSCS_634_Lab_4: Regression & Regularization Using the Diabetes Dataset**

## **Student**

Ajal RC

## **Course**

MSCS 634 — Big Data and Data Mining

## **Lab Title**

Lab 4 — Regression and Regularization Techniques Using the Diabetes Dataset

---

# **1. Purpose of the Lab**

The purpose of this lab was to develop and compare multiple regression models using the Diabetes dataset from scikit-learn. The lab explored how different regression approaches—Simple Linear Regression, Multiple Linear Regression, Ridge Regression, and Lasso Regression—perform when predicting a continuous outcome (disease progression).

The assignment emphasized:

* Understanding how regression works
* Evaluating model performance with error metrics
* Observing how regularization affects overfitting
* Building a foundation for machine learning predictive modeling

---

# **2. Dataset Overview and Data Preparation**

The Diabetes dataset contains:

* **442 patient records**
* **10 standardized numeric features** (age, BMI, blood pressure, etc.)
* **A continuous target variable** representing disease progression one year after baseline

### **Data Preparation Steps Completed**

1. Loaded the dataset into a pandas DataFrame.
2. Explored data structure using `.shape`, `.head()`, `.describe()`, and `.info()`.
3. Inspected the distribution and scale of features.
4. Verified data quality:

   * No missing values
   * No duplicates
   * Features already standardized
5. Demonstrated cleaning workflow (checking missing values, possible imputation logic, duplicate handling).
6. Performed basic outlier visualization using a boxplot.

Even though the dataset was already clean, the cleaning workflow was included because it was required by the lab instructions.

---

# **3. Summary of Regression Models Implemented**

This lab implemented **four models**:

1. **Simple Linear Regression**

   * Uses only **one feature (BMI)** to predict disease progression.

2. **Multiple Linear Regression**

   * Uses **all ten features**.

3. **Ridge Regression (L2 Regularization)**

   * Reduces overfitting by shrinking coefficients.

4. **Lasso Regression (L1 Regularization)**

   * Performs feature selection by shrinking some coefficients to zero.

Each model was evaluated using the same metrics:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* R-squared (R²)

---

# **4. Model Performance Comparison (Using Actual Results)**

The following table summarizes the model performance based on your exact computed values:

| **Model**                           | **MAE**    | **MSE**      | **RMSE**   | **R²**    |
| ----------------------------------- | ---------- | ------------ | ---------- | --------- |
| Simple Linear Regression (BMI only) | **52.260** | **4061.826** | **63.732** | **0.233** |
| Multiple Linear Regression          | **42.794** | **2900.194** | **53.853** | **0.453** |
| Ridge Regression (alpha = 1.0)      | **46.139** | **3077.416** | **55.474** | **0.419** |
| Lasso Regression (alpha = 0.01)     | **42.832** | **2878.559** | **53.652** | **0.457** |

---

# **5. Key Insights from the Regression Analysis**

### **1. Multiple Regression is significantly better than Simple Regression**

* Simple Regression (BMI only) explained only **23.3%** of the variance (R² = 0.233).
* Multiple Regression improved it to **45.3%** (R² = 0.453).
* This shows that diabetes progression is influenced by **multiple factors**, not just BMI.

### **2. Lasso Regression performed the best overall**

* It achieved the **highest R² = 0.457**.
* Lasso’s ability to drop irrelevant features may have reduced noise in the dataset.

### **3. Ridge Regression improved stability but not accuracy**

* Ridge produced R² = 0.419.
* It was better than Simple Regression but weaker than Multiple and Lasso models.
* Ridge is better when features are strongly correlated; here, it provided modest improvement.

### **4. Regularization helps control overfitting**

* Ridge and Lasso prevent the model from giving extreme weights to certain features.
* They improve generalization, especially on small datasets like this one.

---

# **6. Challenges Faced and Decisions Made**

### **1. Dataset already cleaned**

Because the dataset contained:

* No missing values
* No duplicates
* No formatting issues

The cleaning step required adjusting the narrative to demonstrate:

* How we check for missing values
* How imputation would be performed
* How duplicates would be removed
* Why cleaning still matters in real-world datasets

### **2. Choosing model parameters (alpha values)**

* Higher alpha values in Ridge and Lasso caused underfitting.
* Very small alpha values reduced the effect of regularization.
* Final chosen values (Ridge = 1.0, Lasso = 0.01) achieved the most stable and interpretable results.

### **3. Screenshot limitations**

Some outputs (tables, predictions, and printed results) were too long to fit into static screenshots.
A note was included explaining that full output is visible by scrolling in the Jupyter Notebook environment.

---

# **7. Notes About Screenshots**

* Running the Notebook reveals full scrollable outputs
* All visualizations appear completely when executed

---

# **8. References**

Han, J., Pei, J., & Kamber, M. (2012). *Data Mining: Concepts and Techniques* (3rd ed.). Morgan Kaufmann.

Géron, A. (2023). *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow* (3rd ed.). O’Reilly Media.

Pedregosa, F., Varoquaux, G., Gramfort, A., et al. (2011). *Scikit-learn: Machine Learning in Python*. *Journal of Machine Learning Research*, 12, 2825–2830.

Scikit-learn Developers. (2024). Scikit-learn documentation. [https://scikit-learn.org](https://scikit-learn.org)

