## **Feature Engineering**

---

### **1. Feature Creation**

| Technique               | Description                                                     |
| ----------------------- | --------------------------------------------------------------- |
| **Polynomial Features** | Generate interaction terms and higher-order terms               |
| **Binning/Bucketing**   | Group continuous values into intervals (e.g., age ranges)       |
| **Datetime Features**   | Extract parts like day, month, weekday, hour, etc.              |
| **Text Features**       | Word counts, TF-IDF, sentiment scores, word embeddings          |
| **Image Features**      | Mean pixel value, color histograms, pretrained CNN features     |
| **Domain-Specific**     | Custom transformations relevant to specific industry or dataset |

---

### **2. Feature Transformation**

| Technique                 | Description                                                      |
| ------------------------- | ---------------------------------------------------------------- |
| **Scaling**               | Normalize features (e.g., Min-Max, Z-score) to standardize units |
| **Normalization**         | Convert vectors to unit norm (L1 or L2)                          |
| **Log Transform**         | Reduce skewness and handle exponential distributions             |
| **Box-Cox / Yeo-Johnson** | Power transforms for making data more Gaussian-like              |
| **Discretization**        | Convert continuous variables into discrete bins                  |

---

### **3. Feature Encoding**

| Technique              | Description                                   |
| ---------------------- | --------------------------------------------- |
| **Label Encoding**     | Assign integer values to categorical labels   |
| **One-Hot Encoding**   | Create binary columns for each category       |
| **Ordinal Encoding**   | Map categories to integers preserving order   |
| **Target Encoding**    | Replace category with mean of target variable |
| **Frequency Encoding** | Replace category with its occurrence count    |
| **Binary Encoding**    | Converts categories into binary numbers       |

---

### **4. Feature Selection**

| Technique                 | Description                                                     |
| ------------------------- | --------------------------------------------------------------- |
| **Filter Methods**        | Use statistical tests like Chi-square, ANOVA, correlation       |
| **Wrapper Methods**       | Recursive Feature Elimination (RFE), Forward/Backward Selection |
| **Embedded Methods**      | Lasso, Ridge, Tree-based feature importance                     |
| **Variance Thresholding** | Remove features with low variance                               |
| **Mutual Information**    | Measure dependency between feature and target                   |

---

### **5. Dimensionality Reduction**

| Technique                              | Description                                                         |
| -------------------------------------- | ------------------------------------------------------------------- |
| **PCA (Principal Component Analysis)** | Project data to orthogonal directions of max variance               |
| **t-SNE / UMAP**                       | Non-linear reduction for visualization                              |
| **Autoencoders**                       | Neural network for encoding features into compressed representation |
| **LDA (Linear Discriminant Analysis)** | Maximizes class separability in projections                         |

---

### **6. Handling Missing Data**

| Technique                  | Description                                                  |
| -------------------------- | ------------------------------------------------------------ |
| **Imputation**             | Fill missing values (mean, median, mode, KNN, interpolation) |
| **Flag Variables**         | Create binary columns indicating missingness                 |
| **Model-Based Imputation** | Predict missing values using ML models                       |

---

### **7. Outlier Handling**

| Technique                 | Description                        |
| ------------------------- | ---------------------------------- |
| **Winsorization**         | Cap extreme values                 |
| **Z-Score / IQR Methods** | Detect and remove/extreme outliers |
| **Clipping**              | Limit values to a fixed range      |

---

### **8. Automation Tools**

| Tool/Library       | Description                                           |
| ------------------ | ----------------------------------------------------- |
| **FeatureTools**   | Automated feature generation (deep feature synthesis) |
| **Scikit-learn**   | Provides transformers, pipelines, and selectors       |
| **tsfresh**        | Feature extraction from time-series data              |
| **Pandas + NumPy** | Widely used for manual feature engineering            |

---
