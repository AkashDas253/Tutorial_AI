## **Evaluation Metrics in Machine Learning**

---

### **Purpose of Evaluation Metrics**

> Evaluation metrics quantify how well a machine learning model performs. They guide model selection, tuning, and validation and vary based on the **type of task** (classification, regression, ranking, etc.).

---

## **1. Classification Metrics**

---

### **A. Basic Metrics (Binary/Multiclass)**

| Metric        | Description                                                            |
| ------------- | ---------------------------------------------------------------------- |
| **Accuracy**  | Proportion of correct predictions: \$(TP + TN) / (TP + TN + FP + FN)\$ |
| **Precision** | Correct positive predictions: \$TP / (TP + FP)\$                       |
| **Recall**    | Coverage of actual positives: \$TP / (TP + FN)\$                       |
| **F1-Score**  | Harmonic mean of precision and recall: \$2 \* (P \* R)/(P + R)\$       |
| **Support**   | Number of actual instances per class                                   |

---

### **B. Advanced Metrics**

| Metric                                     | Description                                                        |
| ------------------------------------------ | ------------------------------------------------------------------ |
| **Confusion Matrix**                       | Table of true vs. predicted values (TP, TN, FP, FN)                |
| **ROC Curve**                              | Plot of TPR vs. FPR for various thresholds                         |
| **AUC-ROC Score**                          | Area under ROC; measures overall classification ability            |
| **PR Curve**                               | Precision vs. Recall; better for imbalanced datasets               |
| **Log Loss (Cross-Entropy)**               | Penalizes incorrect probability predictions more than correct ones |
| **Cohen’s Kappa**                          | Agreement between predicted and actual labels beyond chance        |
| **Matthews Correlation Coefficient (MCC)** | Balanced metric for imbalanced datasets                            |

---

### **C. Multiclass Extensions**

| Metric           | Type               | Description                                    |
| ---------------- | ------------------ | ---------------------------------------------- |
| **Macro Avg**    | Unweighted mean    | Average metric over all classes                |
| **Micro Avg**    | Global count       | Aggregates TP, FP, FN before computing metrics |
| **Weighted Avg** | Class-proportional | Weighs each class’s metric by its frequency    |

---

## **2. Regression Metrics**

---

| Metric                                      | Description                                                       |                                       |    |
| ------------------------------------------- | ----------------------------------------------------------------- | ------------------------------------- | -- |
| **MAE (Mean Absolute Error)**               | Average absolute error: \$\frac{1}{n}\sum                         | y\_i - \hat{y}\_i                     | \$ |
| **MSE (Mean Squared Error)**                | Penalizes large errors: \$\frac{1}{n}\sum (y\_i - \hat{y}\_i)^2\$ |                                       |    |
| **RMSE (Root MSE)**                         | Square root of MSE (same unit as target)                          |                                       |    |
| **R² Score (Coefficient of Determination)** | Proportion of variance explained by model                         |                                       |    |
| **Adjusted R²**                             | Corrects R² for number of predictors used                         |                                       |    |
| **MAPE (Mean Absolute Percentage Error)**   | Average % error: \$\frac{1}{n}\sum \left                          | \frac{y\_i - \hat{y}\_i}{y\_i} \right | \$ |
| **Huber Loss**                              | Combination of MAE and MSE (robust to outliers)                   |                                       |    |

---

## **3. Clustering Metrics (Unsupervised)**

---

| Metric                                  | Description                                                        |
| --------------------------------------- | ------------------------------------------------------------------ |
| **Silhouette Score**                    | Measures cohesion vs. separation ($\[-1, 1]\$)                     |
| **Davies-Bouldin Index**                | Ratio of intra-cluster to inter-cluster distance (lower is better) |
| **Calinski-Harabasz Index**             | Variance ratio score                                               |
| **Adjusted Rand Index (ARI)**           | Compares predicted and true clusters accounting for chance         |
| **Normalized Mutual Information (NMI)** | Mutual info between clusters normalized                            |

---

## **4. Ranking / Recommendation Metrics**

---

| Metric                                           | Description                                     |
| ------------------------------------------------ | ----------------------------------------------- |
| **Precision\@K**                                 | Proportion of relevant items in top K results   |
| **Recall\@K**                                    | Proportion of relevant items retrieved in top K |
| **MAP (Mean Average Precision)**                 | Mean of average precisions across queries       |
| **MRR (Mean Reciprocal Rank)**                   | Average of reciprocal ranks of correct items    |
| **NDCG (Normalized Discounted Cumulative Gain)** | Rank-weighted relevance metric                  |

---

## **5. Time Series Forecasting Metrics**

---

| Metric                                | Description                                        |
| ------------------------------------- | -------------------------------------------------- |
| **MAE, MSE, RMSE**                    | Same as regression metrics                         |
| **SMAPE (Symmetric MAPE)**            | Handles zero divisions better                      |
| **MASE (Mean Absolute Scaled Error)** | Scaled version of MAE (relative to naive forecast) |
| **Tracking Signal**                   | Measures bias in forecasts                         |

---

## **6. Model Selection Metrics**

| Use                         | Metrics                                                        |
| --------------------------- | -------------------------------------------------------------- |
| **Overfitting Detection**   | Train/Test scores, Gap in metrics, Learning curves             |
| **Cross-Validation Scores** | Mean ± std. dev of k-fold scores                               |
| **Bias-Variance Tradeoff**  | Visual or metric-based comparison of train vs validation error |

---
