## **Model Evaluation Metrics**

---

### **1. Regression Metrics**

| Metric                                      | Formula                                          | Interpretation                                  |    |                            |
| ------------------------------------------- | ------------------------------------------------ | ----------------------------------------------- | -- | -------------------------- |
| **Mean Absolute Error (MAE)**               | \$\frac{1}{n}\sum                                | y\_i - \hat{y}\_i                               | \$ | Average of absolute errors |
| **Mean Squared Error (MSE)**                | \$\frac{1}{n}\sum (y\_i - \hat{y}\_i)^2\$        | Penalizes larger errors more than MAE           |    |                            |
| **Root Mean Squared Error (RMSE)**          | \$\sqrt{\frac{1}{n}\sum (y\_i - \hat{y}\_i)^2}\$ | Square root of MSE, same units as target        |    |                            |
| **R² Score (Coefficient of Determination)** | \$1 - \frac{SS\_{res}}{SS\_{tot}}\$              | Proportion of variance explained (1 is perfect) |    |                            |
| **Adjusted R²**                             | \$1 - (1 - R^2)\frac{n-1}{n-p-1}\$               | Adjusts R² for number of predictors             |    |                            |

---

### **2. Classification Metrics**

| Metric                   | Formula / Description                                                                     | Use Case                                             |
| ------------------------ | ----------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| **Accuracy**             | \$\frac{TP + TN}{TP + TN + FP + FN}\$                                                     | Overall correctness                                  |
| **Precision**            | \$\frac{TP}{TP + FP}\$                                                                    | How many predicted positives are correct             |
| **Recall (Sensitivity)** | \$\frac{TP}{TP + FN}\$                                                                    | How many actual positives are captured               |
| **F1 Score**             | \$2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}\$ | Harmonic mean of precision and recall                |
| **Specificity**          | \$\frac{TN}{TN + FP}\$                                                                    | True negative rate                                   |
| **Balanced Accuracy**    | \$\frac{Sensitivity + Specificity}{2}\$                                                   | Good for imbalanced data                             |
| **AUC-ROC**              | Area under ROC curve                                                                      | Measures classifier’s ability to distinguish classes |
| **Log Loss**             | \$-\frac{1}{n}\sum\[y \log(\hat{y}) + (1 - y)\log(1 - \hat{y})]\$                         | Penalizes wrong confident predictions                |

---

### **3. Confusion Matrix (Binary)**

|                     | Predicted Positive  | Predicted Negative  |
| ------------------- | ------------------- | ------------------- |
| **Actual Positive** | True Positive (TP)  | False Negative (FN) |
| **Actual Negative** | False Positive (FP) | True Negative (TN)  |

---

### **4. Clustering Metrics**

| Metric                                  | Description                                         | Use Case                     |
| --------------------------------------- | --------------------------------------------------- | ---------------------------- |
| **Silhouette Score**                    | Measures cohesion vs separation (\$-1\$ to \$1\$)   | Cluster quality              |
| **Davies-Bouldin Index**                | Ratio of within-cluster to between-cluster distance | Lower is better              |
| **Adjusted Rand Index (ARI)**           | Compares clustering to true labels                  | Clustering with ground truth |
| **Normalized Mutual Information (NMI)** | Measures mutual dependency                          | Cluster-label alignment      |

---

### **5. Ranking / Recommendation Metrics**

| Metric                                           | Description                                 | Use Case               |
| ------------------------------------------------ | ------------------------------------------- | ---------------------- |
| **Precision\@k**                                 | Fraction of top-k results that are relevant | Recommendation systems |
| **Recall\@k**                                    | Fraction of relevant items in top-k         | Search relevance       |
| **MAP (Mean Average Precision)**                 | Average of precisions across queries        | Information retrieval  |
| **NDCG (Normalized Discounted Cumulative Gain)** | Considers ranking position                  | Ranked results         |

---
