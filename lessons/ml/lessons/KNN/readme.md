## **K-Nearest Neighbors (KNN)**

---

### **What is KNN?**

**K-Nearest Neighbors** is a **non-parametric**, **instance-based** supervised learning algorithm used for:

* **Classification**: Assign class by majority vote of nearest neighbors.
* **Regression**: Predict value by averaging the values of nearest neighbors.

---

### **Core Concepts**

| Concept            | Description                                                           |
| ------------------ | --------------------------------------------------------------------- |
| **Instance-based** | Stores all training data; makes predictions at query time.            |
| **Lazy learning**  | No explicit training phase; computation happens during prediction.    |
| **Distance-based** | Neighbors are chosen based on a distance metric (commonly Euclidean). |
| **K value**        | Number of neighbors to consider (user-defined hyperparameter).        |
| **Weighted KNN**   | Closer neighbors can be given more weight than distant ones.          |

---

### **Distance Metrics**

| Metric        | Formula                                               | Usage                        |             |                    |
| ------------- | ----------------------------------------------------- | ---------------------------- | ----------- | ------------------ |
| **Euclidean** | \$\sqrt{\sum (x\_i - y\_i)^2}\$                       | Most common, continuous data |             |                    |
| **Manhattan** | \$\sum                                                | x\_i - y\_i                  | \$          | Grid-based paths   |
| **Minkowski** | \$(\sum                                               | x\_i - y\_i                  | ^p)^{1/p}\$ | Generalized metric |
| **Hamming**   | Number of differing attributes (for categorical data) | Binary/categorical data      |             |                    |

---

### **KNN Classification (Pseudocode)**

```pseudocode
function knn_predict(query_point, training_data, training_labels, k):
    distances = []

    for i in 0 to len(training_data):
        distance = compute_distance(query_point, training_data[i])
        distances.append((distance, training_labels[i]))

    sorted_distances = sort_by_distance(distances)

    top_k = take_first_k(sorted_distances, k)

    votes = count_labels(top_k)

    return label_with_most_votes(votes)
```

---

### **KNN Regression (Pseudocode)**

```pseudocode
function knn_regress(query_point, training_data, training_targets, k):
    distances = []

    for i in 0 to len(training_data):
        distance = compute_distance(query_point, training_data[i])
        distances.append((distance, training_targets[i]))

    sorted_distances = sort_by_distance(distances)

    top_k = take_first_k(sorted_distances, k)

    values = extract_values(top_k)

    return average(values)
```

---

### **Choosing the Right K**

| K Value        | Behavior                                        |
| -------------- | ----------------------------------------------- |
| Small (e.g. 1) | Highly sensitive to noise; overfitting          |
| Large          | More robust to noise; underfitting if too large |

Use **cross-validation** to find optimal K.

---

### **Advantages**

* Simple and intuitive.
* No training phase; just store the data.
* Works for both classification and regression.
* Non-linear decision boundaries possible.

---

### **Disadvantages**

* Computationally expensive for large datasets.
* Requires feature scaling (distance-sensitive).
* Doesn’t work well with irrelevant/noisy features.
* Curse of dimensionality: Distance becomes less meaningful in high dimensions.

---
