## **ADASYN (Adaptive Synthetic Sampling)**

---

### **Definition**

> **ADASYN** (Adaptive Synthetic Sampling) is an advanced oversampling method that builds on SMOTE. It adaptively generates **synthetic minority class samples**, **more densely** in regions where the **minority class is under-represented or harder to learn**.

---

### **Purpose**

* Improve learning of **difficult decision boundaries**.
* Handle **class imbalance** by **focusing on complex regions**.
* Generate more **informative synthetic samples** than uniform oversampling (like SMOTE).

---

### **Core Idea**

ADASYN focuses on **adaptive generation**:

> **The harder a minority sample is to classify**, the **more synthetic samples** are generated around it.

Hard-to-learn areas are identified by:

* Computing the **ratio of majority class neighbors** for each minority sample.
* Assigning **more weight** to samples with more majority class neighbors.

---

### **How ADASYN Works**

| Step                                              | Description                                     |
| ------------------------------------------------- | ----------------------------------------------- |
| Identify all minority class samples               | As base points for synthesis                    |
| For each, find *k*-nearest neighbors              | Across both classes                             |
| Compute the **ratio** of majority class neighbors | Determines sample difficulty                    |
| Assign a **weight** for synthetic generation      | Higher for harder points                        |
| Generate new points                               | Using interpolation like SMOTE but **weighted** |

---

### **Key Differences: ADASYN vs SMOTE**

| Feature              | SMOTE                                      | ADASYN                                    |
| -------------------- | ------------------------------------------ | ----------------------------------------- |
| Sampling strategy    | Uniform across minority class              | Adaptive (focus on harder-to-learn areas) |
| Emphasis             | Equal for all minority points              | Higher for borderline/difficult samples   |
| Risk                 | May introduce noise in outlier regions     | More sensitive to noise and outliers      |
| Control of imbalance | Does not directly adjust decision boundary | Shifts decision boundary adaptively       |

---

### **Benefits**

* **Improves classification performance** in complex regions.
* Enhances learning for **borderline and rare cases**.
* Offers a more **targeted and efficient** alternative to SMOTE.

---

### **Limitations**

| Limitation             | Description                                       |
| ---------------------- | ------------------------------------------------- |
| **Noise Sensitivity**  | May amplify noise if minority points are outliers |
| **Computational Cost** | Slightly higher due to adaptive weighting         |
| **Less predictable**   | Generated distribution depends on sample density  |

---

### **When to Use ADASYN**

* In **highly imbalanced datasets** where the minority class is not uniformly distributed.
* When **borderline and complex samples** need more emphasis.
* In cases where **model recall** on the minority class is critical.

---

### **Best Practices**

* **Preprocess data** (normalize/scale) to improve nearest neighbor accuracy.
* Avoid applying on noisy datasets without filtering or cleaning.
* Can be **combined with under-sampling** for hybrid balancing.
* Validate performance with **F1-score, recall, and AUC**, not accuracy alone.

---
