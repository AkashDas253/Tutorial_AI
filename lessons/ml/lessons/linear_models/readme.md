## **Linear Models**

---

### **What Are Linear Models?**

Linear models assume a **linear relationship** between the **input features** and the **target output**. The output is computed as a **weighted sum of inputs**, optionally passed through an activation or transformation function.

Used for:

* **Regression** (predict continuous values)
* **Classification** (predict discrete classes)

---

### **Types of Linear Models**

| Type                     | Output Type  | Model Form                                       | Activation Function |
| ------------------------ | ------------ | ------------------------------------------------ | ------------------- |
| **Linear Regression**    | Continuous   | \$y = w\_0 + w\_1x\_1 + \dots + w\_nx\_n\$       | None                |
| **Logistic Regression**  | Binary class | \$P(y=1) = \sigma(w \cdot x)\$                   | Sigmoid             |
| **Multinomial Logistic** | Multi-class  | Softmax(\$w\_1 \cdot x\$, ..., \$w\_k \cdot x\$) | Softmax             |
| **Ridge Regression**     | Continuous   | Linear regression + L2 penalty                   | None                |
| **Lasso Regression**     | Continuous   | Linear regression + L1 penalty                   | None                |
| **Elastic Net**          | Continuous   | Linear regression + L1+L2 penalty                | None                |
| **Linear SVM**           | Binary class | Decision hyperplane: \$w \cdot x + b\$           | Sign function       |

---

### **Linear Regression**

#### Model

$$
\hat{y} = w_0 + w_1x_1 + w_2x_2 + \dots + w_nx_n = w \cdot x
$$

#### Loss (Mean Squared Error)

$$
J(w) = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2
$$

#### Training (Gradient Descent)

```pseudocode
function train_linear_regression(X, y, learning_rate, epochs):
    initialize weights w randomly
    for epoch in 1 to epochs:
        predictions = X · w
        errors = predictions - y
        gradient = (2 / len(X)) * (X.T · errors)
        w = w - learning_rate * gradient
    return w
```

---

### **Logistic Regression**

#### Model

$$
P(y=1|x) = \frac{1}{1 + e^{-w \cdot x}} = \sigma(w \cdot x)
$$

#### Loss (Log Loss)

$$
J(w) = - \frac{1}{n} \sum_{i=1}^{n} \left[y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)\right]
$$

#### Training (Gradient Descent)

```pseudocode
function train_logistic_regression(X, y, learning_rate, epochs):
    initialize weights w randomly
    for epoch in 1 to epochs:
        z = X · w
        predictions = sigmoid(z)
        gradient = (1 / len(X)) * (X.T · (predictions - y))
        w = w - learning_rate * gradient
    return w
```

---

### **Regularized Linear Models**

| Model           | Penalty Term                                        | Effect                       |
| --------------- | --------------------------------------------------- | ---------------------------- |
| **Ridge**       | \$J(w) + \lambda \|w\|^2\$                          | Shrinks weights (L2 norm)    |
| **Lasso**       | \$J(w) + \lambda \|w\|\_1\$                         | Drives some weights to zero  |
| **Elastic Net** | \$J(w) + \lambda\_1 \|w\|\_1 + \lambda\_2 \|w\|^2\$ | Combines L1 and L2 penalties |

---

### **Multinomial Logistic Regression (Softmax)**

Used for **multi-class classification** (more than 2 classes).

#### Model

$$
P(y = k | x) = \frac{e^{w_k \cdot x}}{\sum_{j=1}^K e^{w_j \cdot x}}
$$

#### Loss (Cross-Entropy)

$$
J(W) = - \sum_{i=1}^{n} \sum_{k=1}^{K} y_{i,k} \log(\hat{y}_{i,k})
$$

---

### **Linear SVM**

A linear classifier that maximizes the margin between two classes.

#### Decision Rule:

$$
\text{Predict } y = \text{sign}(w \cdot x + b)
$$

#### Hinge Loss:

$$
J(w) = \sum_{i=1}^{n} \max(0, 1 - y_i (w \cdot x_i + b)) + \lambda \|w\|^2
$$

---

### **Advantages**

* Easy to implement and fast to train.
* Requires little tuning.
* Good for linearly separable or nearly linear data.
* Coefficients offer interpretability.

---

### **Disadvantages**

* Assumes linear relationship between features and target.
* Poor performance on complex, non-linear problems.
* Sensitive to multicollinearity and outliers.
* May underfit if the true relationship is not linear.

---
