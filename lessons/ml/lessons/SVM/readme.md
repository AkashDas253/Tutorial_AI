## **Support Vector Machine (SVM)**

---

### **What is SVM?**

A **Support Vector Machine** is a **supervised learning algorithm** used for:

* **Binary classification** (also extended to multi-class).
* **Regression** (SVR – Support Vector Regression).
* **Outlier detection** (One-Class SVM).

It finds a **hyperplane** that best separates data into two classes with **maximum margin**.

---

### **Core Concepts**

| Concept                          | Description                                                                                         |
| -------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Hyperplane**                   | A decision boundary dividing the feature space.                                                     |
| **Margin**                       | Distance between the hyperplane and the nearest data points.                                        |
| **Support Vectors**              | Points that lie closest to the hyperplane and influence its position.                               |
| **Maximum Margin**               | SVM seeks the hyperplane with the largest margin.                                                   |
| **Kernel Trick**                 | Transforms non-linearly separable data into a higher dimension where linear separation is possible. |
| **Slack Variable (Soft Margin)** | Allows misclassification for better generalization on noisy data.                                   |

---

### **Types of SVM**

| Type                | Purpose                                |
| ------------------- | -------------------------------------- |
| **Hard Margin SVM** | No misclassification; for clean data.  |
| **Soft Margin SVM** | Allows some error; handles noise.      |
| **Kernel SVM**      | Handles non-linear data using kernels. |

---

### **Objective Function**

For linear separable data:
Minimize:

$$
\frac{1}{2} \|w\|^2
$$

Subject to:

$$
y_i(w \cdot x_i + b) \geq 1
$$

For soft margin (C = penalty parameter):
Minimize:

$$
\frac{1}{2} \|w\|^2 + C \sum_{i=1}^n \xi_i
$$

Subject to:

$$
y_i(w \cdot x_i + b) \geq 1 - \xi_i,\quad \xi_i \geq 0
$$

---

### **Common Kernels**

| Kernel             | Formula                                     |
| ------------------ | ------------------------------------------- |
| **Linear**         | \$K(x, x') = x \cdot x'\$                   |
| **Polynomial**     | \$K(x, x') = (x \cdot x' + c)^d\$           |
| **RBF (Gaussian)** | \$K(x, x') = \exp(-\gamma \|x - x'\|^2)\$   |
| **Sigmoid**        | \$K(x, x') = \tanh(\alpha x \cdot x' + c)\$ |

---

### **Training SVM (Pseudocode)**

```pseudocode
function train_svm(data, labels, C, kernel):
    initialize α_i = 0 for all i
    initialize b = 0

    repeat until convergence:
        for i from 1 to N:
            calculate E_i = f(x_i) - y_i
            if violates KKT conditions:
                select j ≠ i
                calculate E_j = f(x_j) - y_j

                save old α_i and α_j
                compute bounds L and H

                compute η = 2 * K(x_i, x_j) - K(x_i, x_i) - K(x_j, x_j)
                if η >= 0: continue

                update α_j and clip to [L, H]
                update α_i accordingly

                update b using α_i, α_j, and errors

    return α, b
```

> This is a simplified **Sequential Minimal Optimization (SMO)** approach.

---

### **Prediction (Pseudocode)**

```pseudocode
function predict(x, support_vectors, α, b, kernel):
    sum = 0
    for each support_vector (x_i, y_i):
        sum += α_i * y_i * kernel(x_i, x)
    return sign(sum + b)
```

---

### **Advantages**

* Effective in high-dimensional spaces.
* Works well with clear margin of separation.
* Memory efficient (only support vectors stored).
* Flexible via kernel functions.

---

### **Disadvantages**

* Computationally intensive for large datasets.
* Hard to choose the right kernel.
* Not easily interpretable.
* Sensitive to outliers (especially hard margin).

---
