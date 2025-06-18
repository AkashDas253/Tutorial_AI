## **SMOTE (Synthetic Minority Over-sampling Technique)**

---

### **Definition**

SMOTE is a **data-level technique** used to address **class imbalance** in classification tasks. Instead of duplicating existing minority class instances, it generates **synthetic examples** by interpolating between minority class samples.

---

### **Purpose**

* Balance the class distribution in training data.
* Improve the classifier’s ability to learn minority class patterns.
* Reduce overfitting caused by simple oversampling.

---

### **Core Idea**

For a given sample in the minority class:

* Identify its nearest neighbors within the same class.
* Select one or more of these neighbors.
* Generate a new data point **between the sample and its neighbor** by linear interpolation in the feature space.

This creates **plausible new samples** that enrich the minority class distribution.

---

### **How SMOTE Works**

| Step                           | Description                                          |
| ------------------------------ | ---------------------------------------------------- |
| Choose a minority class sample | Base point for interpolation                         |
| Find its *k* nearest neighbors | Among other minority samples                         |
| Randomly select one neighbor   | For synthetic generation                             |
| Create synthetic sample        | By interpolating between the sample and its neighbor |

The interpolation formula is:

```
synthetic = sample + random_factor × (neighbor - sample)
```

where `random_factor` is a value between 0 and 1.

---

### **Variants of SMOTE**

| Variant              | Purpose                                                              |
| -------------------- | -------------------------------------------------------------------- |
| **Borderline-SMOTE** | Focuses on samples near decision boundary (more informative)         |
| **SMOTE-NC**         | Handles numeric and categorical features together                    |
| **ADASYN**           | Generates more data in regions with higher classification difficulty |
| **Safe-Level-SMOTE** | Avoids generating synthetic samples in noisy or unsafe regions       |
| **KMeans-SMOTE**     | Uses clustering to balance local and global distribution             |

---

### **Benefits**

* Mitigates class imbalance without replicating existing samples.
* Expands the decision region of the minority class.
* Can significantly boost performance for recall- and F1-sensitive tasks.

---

### **Limitations**

| Issue                   | Description                                                                |
| ----------------------- | -------------------------------------------------------------------------- |
| Overlapping Classes     | May generate synthetic points in the majority class region                 |
| Curse of Dimensionality | Distance-based interpolation may become less meaningful in high dimensions |
| Noise Sensitivity       | May create unhelpful samples near outliers or noisy data points            |

---

### **Best Use Cases**

* Binary or multi-class classification with **high class imbalance**.
* Situations where **minority class recall** is more important than accuracy.
* Problems where collecting more real-world data is difficult or expensive.

---

### **Best Practices**

* Apply SMOTE only to the **training set**, not to the test set.
* **Preprocess data** (e.g., normalization) before applying SMOTE.
* Combine SMOTE with **under-sampling** of the majority class for better results.
* Tune parameters such as number of neighbors and amount of synthesis carefully.

---
