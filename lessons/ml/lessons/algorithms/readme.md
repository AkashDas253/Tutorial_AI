## Machine Learning Algorithms

---

### **1. Regression Algorithms**

| Algorithm                 | Description                                          | Use Cases              |
| ------------------------- | ---------------------------------------------------- | ---------------------- |
| **Linear Regression**     | Models linear relationship between input and output. | House price prediction |
| **Ridge Regression**      | Adds L2 regularization to linear regression.         | Multicollinear data    |
| **Lasso Regression**      | Adds L1 regularization (performs feature selection). | Sparse models          |
| **Polynomial Regression** | Fits nonlinear data using polynomial terms.          | Curve fitting          |

---

### **2. Classification Algorithms**

| Algorithm                                 | Description                                                         | Use Cases                         |
| ----------------------------------------- | ------------------------------------------------------------------- | --------------------------------- |
| **Logistic Regression**                   | Binary classifier; outputs probability.                             | Spam detection                    |
| **K-Nearest Neighbors**                   | Classifies based on majority vote of nearest neighbors.             | Pattern recognition               |
| **Support Vector Machine (SVM)**          | Finds optimal boundary with maximum margin.                         | Image/text classification         |
| **Naive Bayes**                           | Probabilistic classifier using Bayes theorem; assumes independence. | Text classification, spam filters |
| **Decision Trees**                        | Tree-based model using feature splits.                              | Credit scoring                    |
| **Random Forest**                         | Ensemble of decision trees using bagging.                           | Robust classification             |
| **Gradient Boosting (XGBoost, LightGBM)** | Ensemble using boosting; improves weak learners.                    | Tabular classification problems   |

---

### **3. Clustering Algorithms (Unsupervised)**

| Algorithm                        | Description                                                                   | Use Cases             |
| -------------------------------- | ----------------------------------------------------------------------------- | --------------------- |
| **K-Means**                      | Partitions data into K clusters minimizing intra-cluster variance.            | Customer segmentation |
| **Hierarchical Clustering**      | Builds tree-like clusters via agglomeration or division.                      | Taxonomy creation     |
| **DBSCAN**                       | Groups dense regions; identifies outliers.                                    | Anomaly detection     |
| **Gaussian Mixture Model (GMM)** | Probabilistic model assuming data comes from multiple Gaussian distributions. | Soft clustering       |

---

### **4. Dimensionality Reduction Algorithms**

| Algorithm                                               | Description                                           | Use Cases                           |
| ------------------------------------------------------- | ----------------------------------------------------- | ----------------------------------- |
| **PCA (Principal Component Analysis)**                  | Projects data onto directions of maximum variance.    | Visualization, noise reduction      |
| **t-SNE (t-distributed Stochastic Neighbor Embedding)** | Nonlinear dimensionality reduction for visualization. | High-dimensional data visualization |
| **LDA (Linear Discriminant Analysis)**                  | Supervised method maximizing class separability.      | Preprocessing for classification    |
| **Autoencoders**                                        | Neural network-based encoding and decoding.           | Feature extraction                  |

---

### **5. Ensemble Learning Algorithms**

| Algorithm    | Description                                                     | Use Cases                     |
| ------------ | --------------------------------------------------------------- | ----------------------------- |
| **Bagging**  | Trains multiple models on random subsets; averages predictions. | Random Forest                 |
| **Boosting** | Sequentially trains models to correct errors of prior ones.     | Gradient Boosting, AdaBoost   |
| **Stacking** | Combines multiple base models via a meta-model.                 | Model performance improvement |

---

### **6. Neural Network-Based Algorithms**

| Algorithm                              | Description                                             | Use Cases                          |
| -------------------------------------- | ------------------------------------------------------- | ---------------------------------- |
| **MLP (Multi-Layer Perceptron)**       | Fully connected neural network.                         | General-purpose tasks              |
| **CNN (Convolutional Neural Network)** | Extracts features from grid-like data.                  | Image recognition                  |
| **RNN (Recurrent Neural Network)**     | Handles sequential data using memory.                   | Text, speech, time-series          |
| **LSTM/GRU**                           | Advanced RNN variants to handle long-term dependencies. | Language modeling, forecasting     |
| **Transformer**                        | Uses self-attention; state-of-the-art in NLP.           | Machine translation, summarization |

---
