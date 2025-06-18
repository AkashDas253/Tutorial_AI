## **Linear Discriminant Analysis (LDA)**

---

### **Definition**

> **Linear Discriminant Analysis (LDA)** is a **supervised linear dimensionality reduction** and classification technique. It projects data into a lower-dimensional space in a way that **maximizes class separability**.

---

### **Core Objectives**

* Reduce dimensions while **preserving class-discriminative information**
* Find a **linear combination** of features that separates classes
* Improve classification performance and visualization

---

### **Key Differences from PCA**

| Feature              | **PCA**                           | **LDA**                                      |
| -------------------- | --------------------------------- | -------------------------------------------- |
| **Type**             | Unsupervised                      | Supervised                                   |
| **Goal**             | Maximize variance                 | Maximize class separation                    |
| **Uses label info?** | No                                | Yes                                          |
| **Projection basis** | Eigenvectors of covariance matrix | Eigenvectors of between/within-class scatter |

---

### **Concepts in LDA**

| Term                           | Description                                                                         |            |    |            |                                 |
| ------------------------------ | ----------------------------------------------------------------------------------- | ---------- | -- | ---------- | ------------------------------- |
| **Class Mean**                 | Mean vector for each class                                                          |            |    |            |                                 |
| **Within-Class Scatter (Sw)**  | Measures scatter (variance) within each class                                       |            |    |            |                                 |
| **Between-Class Scatter (Sb)** | Measures scatter between class means                                                |            |    |            |                                 |
| **Discriminant Axes**          | Directions that maximize the ratio of **between-class** to **within-class** scatter |            |    |            |                                 |
| **Fisher Criterion**           | Objective to maximize \$\frac{                                                      | W^T S\_b W | }{ | W^T S\_w W | }\$ for projection matrix \$W\$ |

---

### **Steps in LDA (Conceptually)**

1. **Compute class-wise statistics**

   * Class means and overall mean

2. **Calculate scatter matrices**

   * Within-class scatter (\$S\_w\$)
   * Between-class scatter (\$S\_b\$)

3. **Solve generalized eigenvalue problem**

   * Find eigenvectors/values of \$S\_w^{-1} S\_b\$

4. **Sort eigenvectors**

   * Pick top `k` eigenvectors with largest eigenvalues

5. **Project data**

   * New space is formed by projecting data onto top eigenvectors

---

### **Dimensionality Limit**

* LDA can produce at most **(C - 1)** components, where `C` is the number of classes
* Example: 3-class classification → maximum 2-dimensional projection

---

### **Advantages**

* Enhances **class separation** for supervised learning
* Works well for **linearly separable** classes
* Can improve **classification accuracy**
* Often used as a **preprocessing step** before classifiers

---

### **Limitations**

| Limitation                   | Description                                   |
| ---------------------------- | --------------------------------------------- |
| **Assumes normality**        | Assumes features are normally distributed     |
| **Assumes equal covariance** | Assumes same covariance for all classes       |
| **Linear boundaries only**   | Doesn’t model complex non-linear separation   |
| **Sensitive to outliers**    | Strongly affected by class-specific anomalies |

---

### **Applications**

* **Face recognition** (e.g., Fisherfaces)
* **Bioinformatics** (e.g., gene classification)
* **Speech recognition**
* **Text classification**
* **Medical diagnosis**

---

### **LDA vs QDA**

| Feature               | **LDA**             | **QDA (Quadratic Discriminant Analysis)** |
| --------------------- | ------------------- | ----------------------------------------- |
| Covariance Assumption | Same across classes | Different for each class                  |
| Decision Boundaries   | Linear              | Quadratic                                 |
| Complexity            | Lower               | Higher                                    |

---
