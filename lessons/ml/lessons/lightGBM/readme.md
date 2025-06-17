## **LightGBM**

---

### **What is LightGBM?**

**LightGBM** (Light Gradient Boosting Machine) is a **gradient boosting framework** that builds decision trees **sequentially** to minimize a loss function.

It is optimized for **speed and memory efficiency**, especially for large datasets and high-dimensional data.

---

### **Core Concepts**

| Concept                         | Description                                                                     |
| ------------------------------- | ------------------------------------------------------------------------------- |
| **Gradient Boosting**           | Ensemble method that adds models sequentially to reduce prediction error.       |
| **Leaf-wise Tree Growth**       | Grows the leaf with the maximum loss reduction first, unlike level-wise growth. |
| **Histogram-based Splitting**   | Converts features into bins to speed up training and reduce memory usage.       |
| **Categorical Feature Support** | Native support for categorical features without preprocessing.                  |

---

### **Key Components in LightGBM**

| Component          | Description                                                     |
| ------------------ | --------------------------------------------------------------- |
| **Boosting type**  | Gradient boosting decision tree (GBDT), DART, or GOSS.          |
| **Loss function**  | Used to guide the optimization (e.g., log loss, MSE).           |
| **Split finding**  | Uses histogram-based algorithm for fast best-split computation. |
| **Regularization** | Parameters like `lambda_l1`, `lambda_l2` control overfitting.   |

---

### **LightGBM Training (Pseudocode)**

```pseudocode
function train_lightgbm(data, labels, num_rounds):
    model = []

    F_0 = initialize_prediction(labels)

    for t in 1 to num_rounds:
        gradients = compute_gradient(labels, F_0)
        hessians = compute_hessian(labels, F_0)

        tree = build_tree(data, gradients, hessians)
        model.append(tree)

        predictions = predict_tree(tree, data)
        F_0 = F_0 + learning_rate * predictions

    return model
```

---

### **Leaf-wise Tree Growth (Pseudocode)**

```pseudocode
function build_tree(data, gradients, hessians):
    root = create_node(data)

    while num_leaves < max_leaves:
        node = find_node_with_max_gain()
        if node is not splittable:
            break

        split = best_split(node, gradients, hessians)
        node.left = create_node(split.left_data)
        node.right = create_node(split.right_data)

    return root
```

---

### **Gradient and Hessian Calculation**

* For classification:

  * Gradient = derivative of loss w\.r.t. prediction
  * Hessian = second derivative of loss w\.r.t. prediction

---

### **Advantages**

* Extremely fast training with large datasets.
* Lower memory usage via histogram binning.
* Supports categorical features natively.
* Typically better accuracy than traditional GBDT.

---

### **Disadvantages**

* Sensitive to hyperparameters.
* Leaf-wise growth may lead to overfitting.
* More complex to tune than simpler models.

---

### **Common Parameters**

| Parameter          | Description                                     |
| ------------------ | ----------------------------------------------- |
| `num_leaves`       | Controls complexity; more leaves = more complex |
| `max_depth`        | Max depth per tree                              |
| `learning_rate`    | Shrinks contribution of each tree               |
| `min_data_in_leaf` | Prevents small leaf nodes (overfitting control) |
| `feature_fraction` | Fraction of features to use in each iteration   |
| `bagging_fraction` | Fraction of data to use (like bootstrap)        |
| `lambda_l1/l2`     | L1/L2 regularization terms                      |

---
