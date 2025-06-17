## **Random Forest**

---

### **What is Random Forest?**

**Random Forest** is an **ensemble learning algorithm** that builds multiple **decision trees** and combines their outputs to improve accuracy and reduce overfitting.

* **For classification**: takes the **majority vote**.
* **For regression**: takes the **average** of predictions.

---

### **Core Concepts**

| Concept                             | Description                                                                        |
| ----------------------------------- | ---------------------------------------------------------------------------------- |
| **Ensemble Learning**               | Combines predictions from multiple models.                                         |
| **Bagging (Bootstrap Aggregating)** | Each tree is trained on a random sample (with replacement) from the training data. |
| **Random Feature Selection**        | Each split considers a random subset of features.                                  |
| **Majority Voting**                 | Used to aggregate predictions in classification.                                   |
| **Averaging**                       | Used in regression to average outputs of trees.                                    |

---

### **Random Forest Training (Pseudocode)**

```pseudocode
function train_random_forest(data, labels, num_trees, max_features):
    forest = []

    for i in 1 to num_trees:
        bootstrap_data, bootstrap_labels = sample_with_replacement(data, labels)
        tree = build_tree(bootstrap_data, bootstrap_labels, max_features)
        forest.append(tree)

    return forest
```

> `build_tree()` is a regular decision tree that selects a **random subset of features** at each split.

---

### **Prediction (Pseudocode)**

**Classification:**

```pseudocode
function predict_forest_classification(forest, instance):
    predictions = []

    for tree in forest:
        prediction = predict_tree(tree, instance)
        predictions.append(prediction)

    return majority_vote(predictions)
```

**Regression:**

```pseudocode
function predict_forest_regression(forest, instance):
    predictions = []

    for tree in forest:
        prediction = predict_tree(tree, instance)
        predictions.append(prediction)

    return average(predictions)
```

---

### **Key Parameters**

| Parameter           | Description                                                                |
| ------------------- | -------------------------------------------------------------------------- |
| `num_trees`         | Number of trees to build. More trees = better performance (up to a point). |
| `max_features`      | Number of features to consider at each split.                              |
| `max_depth`         | Maximum depth of individual trees.                                         |
| `min_samples_split` | Minimum samples required to split a node.                                  |

---

### **Advantages**

* Reduces overfitting (compared to a single tree).
* Works well with high-dimensional and missing data.
* Handles both classification and regression.
* Robust to noise and outliers.

---

### **Disadvantages**

* Slower and more memory-intensive than a single tree.
* Less interpretable than individual decision trees.
* Can still overfit if not properly tuned.

---
