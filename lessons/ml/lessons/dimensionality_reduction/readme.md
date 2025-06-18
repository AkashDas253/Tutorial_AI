## **Dimensionality Reduction in Machine Learning**

---

### **Definition**

> **Dimensionality reduction** is the process of reducing the number of input variables (features) in a dataset while preserving as much relevant information as possible. It simplifies models, reduces overfitting, and improves computation efficiency.

---

### **Goals of Dimensionality Reduction**

* Improve **model performance** and **training speed**
* Reduce **overfitting** by eliminating noise
* Enable **data visualization** in 2D/3D
* Lower **storage and memory** requirements
* Handle **multicollinearity** among features

---

### **Types of Dimensionality Reduction**

#### **1. Feature Selection** (keep subset of original features)

| Method               | Description                                               |
| -------------------- | --------------------------------------------------------- |
| **Filter Methods**   | Use statistical measures (e.g., chi-square, correlation)  |
| **Wrapper Methods**  | Use models to evaluate feature subsets (e.g., RFE)        |
| **Embedded Methods** | Feature selection built into model training (e.g., LASSO) |

---

#### **2. Feature Extraction** (create new features)

| Method                                 | Description                                                         |
| -------------------------------------- | ------------------------------------------------------------------- |
| **Principal Component Analysis (PCA)** | Linear combinations of features to capture maximum variance         |
| **Linear Discriminant Analysis (LDA)** | Supervised technique for maximizing class separation                |
| **t-SNE**                              | Non-linear embedding preserving local relationships (visualization) |
| **UMAP**                               | Similar to t-SNE but faster and preserves global structure          |
| **Autoencoders**                       | Neural networks that learn compressed representations               |
| **Truncated SVD**                      | PCA-like for sparse matrices (e.g., text/LSA)                       |
| **Factor Analysis**                    | Models observed variables as linear combinations of latent factors  |

---

### **Comparison of Common Techniques**

| Method      | Type       | Supervised | Linear | Use Case                         |
| ----------- | ---------- | ---------- | ------ | -------------------------------- |
| PCA         | Extraction | ❌          | ✅      | General data compression         |
| LDA         | Extraction | ✅          | ✅      | Classification with labels       |
| t-SNE       | Extraction | ❌          | ❌      | Visualization (2D/3D plots)      |
| UMAP        | Extraction | ❌          | ❌      | Fast visualization, clustering   |
| Autoencoder | Extraction | ❌          | ❌      | Deep learning-based compression  |
| SVD         | Extraction | ❌          | ✅      | Text and sparse matrix reduction |

---

### **Principal Component Analysis (PCA)** — Key Concept

* Projects data onto **orthogonal axes** (principal components)
* Each component captures **maximum remaining variance**
* Components are **ranked by importance**
* Unsupervised and **rotation-invariant**

---

### **Workflow for Dimensionality Reduction**

1. **Preprocessing**

   * Standardize or normalize data
   * Remove nulls/outliers

2. **Select Method**

   * PCA for numerical/linear data
   * LDA for supervised classification
   * t-SNE/UMAP for visualization

3. **Fit & Transform**

   * Apply the technique
   * Choose top `k` components (based on explained variance or elbow method)

4. **Post-analysis**

   * Visualize in 2D/3D
   * Use reduced data for modeling or clustering

---

### **Applications**

* **Preprocessing** for ML models (especially high-dimensional)
* **Visualization** of complex datasets
* **Noise reduction** and smoothing
* **Text mining** (e.g., topic modeling with SVD)
* **Image compression** and denoising

---

### **Challenges**

| Issue                   | Notes                                                 |
| ----------------------- | ----------------------------------------------------- |
| **Information Loss**    | Risk of losing predictive signals                     |
| **Interpretability**    | Transformed features are harder to understand         |
| **Computational Cost**  | Some methods are intensive for large datasets (t-SNE) |
| **Scaling Sensitivity** | PCA, LDA need standardized data                       |

---
