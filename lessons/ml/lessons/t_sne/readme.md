## **t-SNE (t-Distributed Stochastic Neighbor Embedding)**

---

### **Definition**

> **t-SNE** is a **non-linear, unsupervised** dimensionality reduction technique primarily used for **visualizing high-dimensional data** in **2D or 3D** by preserving local relationships (i.e., neighborhood structure).

---

### **Core Objectives**

* Convert **high-dimensional data** into **low-dimensional embeddings**
* Preserve **local structure** (data points that are close stay close)
* Reveal patterns like **clusters**, **manifolds**, or **outliers**

---

### **Key Concepts**

| Concept                    | Description                                                   |
| -------------------------- | ------------------------------------------------------------- |
| **High-dimensional space** | Original feature space (e.g., 1000 dimensions)                |
| **Low-dimensional space**  | Output space for visualization (e.g., 2D)                     |
| **Pairwise similarity**    | Probability of similarity between pairs of points             |
| **KL divergence**          | Measures difference between high-dim and low-dim similarities |
| **Student-t distribution** | Used in low-dimensional space to handle "crowding problem"    |

---

### **How t-SNE Works (Conceptual Steps)**

1. **Compute Pairwise Similarities in High-Dim Space**

   * Convert distances between points to **conditional probabilities** (Gaussian kernel)
   * \$P\_{j|i}\$: probability that point *i* chooses *j* as its neighbor

2. **Compute Pairwise Similarities in Low-Dim Space**

   * Use **Student t-distribution** (with 1 degree of freedom)
   * Heavier tails help spread out points

3. **Minimize KL Divergence**

   * Measure how much the low-dimensional distribution deviates from high-dimensional
   * Use gradient descent to minimize the difference

---

### **Important Parameters**

| Parameter          | Description                                                               |
| ------------------ | ------------------------------------------------------------------------- |
| **perplexity**     | Controls the balance between local and global aspects (recommended: 5–50) |
| **learning\_rate** | Influences convergence and cluster spread                                 |
| **n\_iter**        | Number of optimization iterations (usually >1000)                         |
| **n\_components**  | Output dimension (usually 2 or 3)                                         |
| **init**           | Initialization method (`random` or `pca`)                                 |
| **metric**         | Distance measure (`euclidean`, `cosine`, etc.)                            |

---

### **Advantages**

* Captures **non-linear** structures in data
* Reveals **clusters**, **substructures**, and **anomalies**
* Ideal for **visualization of high-dimensional data**

---

### **Limitations**

| Limitation                    | Notes                                                     |
| ----------------------------- | --------------------------------------------------------- |
| **Computationally expensive** | Slower for large datasets                                 |
| **Not scalable**              | Not ideal for datasets >10,000 rows without optimizations |
| **Non-parametric**            | Cannot transform new data without retraining              |
| **Only for visualization**    | Transformed dimensions not interpretable                  |
| **Sensitive to parameters**   | Requires careful tuning of perplexity and learning rate   |

---

### **Applications**

* **Data exploration** (e.g., clustering visualization)
* **Image recognition** (e.g., MNIST, CIFAR embeddings)
* **Word embeddings** (e.g., Word2Vec, BERT)
* **Genomics**, **biology**, **neuroscience**
* **Anomaly detection** (through outlier visualization)

---

### **t-SNE vs PCA vs UMAP**

| Property          | **t-SNE**       | **PCA**         | **UMAP**          |
| ----------------- | --------------- | --------------- | ----------------- |
| Type              | Non-linear      | Linear          | Non-linear        |
| Supervised        | No              | No              | Optional          |
| Preserves         | Local structure | Global variance | Local & global    |
| Speed             | Slow            | Fast            | Faster than t-SNE |
| New point mapping | ❌               | ✅               | ✅                 |
| Visualization     | Excellent       | Limited         | Excellent         |

---
