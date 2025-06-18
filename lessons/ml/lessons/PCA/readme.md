## **Principal Component Analysis (PCA)**

---

### **Definition**

> **Principal Component Analysis (PCA)** is an **unsupervised linear transformation technique** used to reduce the **dimensionality** of data by transforming it into a new set of variables (called **principal components**) that are uncorrelated and ordered by the amount of variance they capture from the original dataset.

---

### **Core Objectives**

* Capture **maximum variance** in fewer dimensions
* Identify and eliminate **redundant** or **correlated** features
* Simplify data without much loss of important information
* Create **orthogonal** (uncorrelated) axes for better separation
* Improve **visualization**, **storage**, and **processing efficiency**

---

### **Key Concepts**

| Concept                 | Description                                                             |
| ----------------------- | ----------------------------------------------------------------------- |
| **Principal Component** | A new variable formed as a linear combination of the original variables |
| **Variance**            | The spread or informational content of the data along a direction       |
| **Orthogonality**       | Principal components are orthogonal (statistically uncorrelated)        |
| **Eigenvectors**        | Directions of maximum variance (principal axes)                         |
| **Eigenvalues**         | Magnitude of variance captured along each principal axis                |

---

### **How PCA Works (Conceptual Steps)**

1. **Standardization**

   * Center the data (zero mean) and scale if needed (unit variance)
   * Ensures all features contribute equally

2. **Covariance Matrix Computation**

   * Measures relationships (covariance) between all pairs of features
   * Reveals feature dependencies and correlations

3. **Eigen Decomposition**

   * Compute **eigenvalues** and **eigenvectors** of the covariance matrix
   * Eigenvectors define directions (principal components), eigenvalues define strength (variance)

4. **Sort Components**

   * Rank principal components in descending order of their eigenvalues
   * First component captures the most variance, followed by the second, etc.

5. **Projection**

   * Project original data onto top `k` principal components
   * Results in a new dataset with `k` dimensions

---

### **Properties of PCA**

| Property                  | Description                                                    |
| ------------------------- | -------------------------------------------------------------- |
| **Linear**                | PCA captures linear relationships only                         |
| **Unsupervised**          | No label information is used                                   |
| **Orthogonal Components** | Each principal component is uncorrelated with others           |
| **Maximizes Variance**    | Each component captures the next highest variance left in data |

---

### **Choosing the Number of Components**

* Use **explained variance ratio** (percentage of total variance each component captures)
* Plot **cumulative variance** and apply **elbow rule**
* Select minimum number of components that explain sufficient variance (e.g., 95%)

---

### **Advantages**

* Reduces dimensionality with **minimal information loss**
* Removes **multicollinearity**
* Improves **training speed** and **storage efficiency**
* Enables **visualization** in 2D/3D
* Makes noisy datasets more manageable

---

### **Limitations**

| Limitation                   | Description                                                           |
| ---------------------------- | --------------------------------------------------------------------- |
| **Linear only**              | Cannot capture nonlinear relationships                                |
| **Loss of Interpretability** | New features are combinations of original ones                        |
| **Scaling Sensitive**        | Highly affected by the scale of input data                            |
| **Variance ≠ Importance**    | High variance does not always imply high relevance to target variable |

---

### **Applications**

* **Preprocessing** before supervised learning
* **Noise reduction** and data compression
* **Visual exploration** of high-dimensional data
* **Image processing** (e.g., face recognition)
* **Finance** (e.g., portfolio diversification analysis)
* **Genomics** and **biology** (e.g., gene expression)

---
