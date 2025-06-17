## **Decision Tree**
---

### **What is a Decision Tree?**

A **Decision Tree** is a flowchart-like tree structure where:

* **Internal nodes** represent tests on features.
* **Branches** represent outcomes of the test.
* **Leaf nodes** represent final decisions (class labels or values).

Used for both **classification** and **regression**.

---

### **Key Concepts**

| Concept               | Description                                                          |
| --------------------- | -------------------------------------------------------------------- |
| **Root Node**         | Starting point; contains all the data.                               |
| **Splitting**         | Dividing a node into sub-nodes based on feature values.              |
| **Information Gain**  | Reduction in impurity from a split (e.g., entropy or Gini decrease). |
| **Stopping Criteria** | No more gain, max depth reached, or too few samples to continue.     |
| **Pruning**           | Removing parts of the tree to reduce overfitting.                    |

---

### **Common Impurity Measures**

| Measure        | Formula                                                          |
| -------------- | ---------------------------------------------------------------- |
| **Entropy**    | \$Entropy(S) = - \sum p\_i \log\_2(p\_i)\$                       |
| **Gini Index** | \$Gini(S) = 1 - \sum p\_i^2\$                                    |
| **Variance**   | For regression: \$Var(S) = \frac{1}{n} \sum (y\_i - \bar{y})^2\$ |

---

### **Decision Tree Building (Pseudocode)**

```pseudocode
function build_tree(data, features):
    if all data in one class:
        return Leaf(class_label)

    if features is empty:
        return Leaf(majority_class)

    best_feature = select_best_feature(data, features)

    tree = Node(feature = best_feature)

    for value in unique_values(data[best_feature]):
        subset = filter(data, best_feature == value)

        if subset is empty:
            tree.add_branch(value, Leaf(majority_class))
        else:
            subtree = build_tree(subset, features - {best_feature})
            tree.add_branch(value, subtree)

    return tree
```

---

### **Feature Selection Using Information Gain (Pseudocode)**

```pseudocode
function select_best_feature(data, features):
    base_entropy = calculate_entropy(data)
    best_gain = 0
    best_feature = None

    for feature in features:
        values = unique_values(data[feature])
        feature_entropy = 0

        for value in values:
            subset = filter(data, feature == value)
            weight = len(subset) / len(data)
            feature_entropy += weight * calculate_entropy(subset)

        info_gain = base_entropy - feature_entropy

        if info_gain > best_gain:
            best_gain = info_gain
            best_feature = feature

    return best_feature
```

---

### **Prediction (Pseudocode)**

```pseudocode
function predict(tree, instance):
    if tree is Leaf:
        return tree.class_label

    feature_value = instance[tree.feature]
    branch = tree.get_branch(feature_value)

    if branch is None:
        return default_class

    return predict(branch, instance)
```

---

### **Advantages**

* Easy to understand and interpret.
* Handles both numerical and categorical data.
* Requires little data preprocessing.

---

### **Disadvantages**

* Prone to overfitting.
* Unstable to small variations in data.
* Greedy splitting may not yield the global optimum.

---
