## **Optimizers** in Deep Learning

---

### **Definition**

An **optimizer** is an algorithm used to update the weights and biases of a neural network to minimize the **loss function**. It determines how the model learns from data by applying **gradient descent** and its advanced variants.

---

### **Optimization Objective**

$$
\theta \leftarrow \theta - \eta \cdot \nabla_\theta J(\theta)
$$

| Symbol                       | Meaning                                      |
| ---------------------------- | -------------------------------------------- |
| \$\theta\$                   | Model parameters (weights and biases)        |
| \$\eta\$                     | Learning rate                                |
| \$\nabla\_\theta J(\theta)\$ | Gradient of loss function w\.r.t. parameters |

---

### **Core Objectives of an Optimizer**

| Objective                        | Description                                            |
| -------------------------------- | ------------------------------------------------------ |
| **Minimize Loss**                | Reduce prediction error by tuning parameters           |
| **Speed Up Convergence**         | Achieve optimal parameters faster                      |
| **Handle Complex Loss Surfaces** | Navigate plateaus, saddle points, and local minima     |
| **Stable Training**              | Prevent oscillation, and vanishing/exploding gradients |

---

### **Key Concepts in Optimization**

| Concept                    | Description                                                        |
| -------------------------- | ------------------------------------------------------------------ |
| **Learning Rate (η)**      | Step size for updating parameters                                  |
| **Gradient**               | Derivative of the loss function w\.r.t each parameter              |
| **Momentum**               | Adds inertia to updates, smoothing learning                        |
| **Adaptive Learning Rate** | Per-parameter learning rate adjustment                             |
| **Weight Decay**           | Penalizes large weights to prevent overfitting (L2 regularization) |

---

### **Types of Optimizers**

| Optimizer          | Formula / Idea                                               | Highlights                                     | Use Cases / Notes                              |
| ------------------ | ------------------------------------------------------------ | ---------------------------------------------- | ---------------------------------------------- |
| **SGD**            | \$w := w - \eta \cdot \nabla L(w)\$                          | Baseline method; simple                        | Effective but slow; sensitive to learning rate |
| **SGD + Momentum** | \$v := \gamma v + \eta \cdot \nabla L(w); \quad w := w - v\$ | Adds velocity to reduce oscillations           | Faster convergence, avoids poor local minima   |
| **NAG**            | Looks ahead before computing gradient                        | Improves over Momentum                         | More responsive                                |
| **Adagrad**        | Divides LR by square root of gradient sum                    | Per-parameter LR; great for sparse data        | LR shrinks over time                           |
| **RMSProp**        | Uses EMA of squared gradients                                | Fixes Adagrad's LR decay; stable               | Effective in RNNs                              |
| **Adam**           | Combines Momentum + RMSProp                                  | Adaptive and fast; most widely used            | Default for many deep learning tasks           |
| **AdaDelta**       | Adagrad variant with no LR needed                            | Adaptive; more robust than Adagrad             | Outdated by Adam                               |
| **Nadam**          | Adam + Nesterov momentum                                     | Slight improvement over Adam                   | More stable for sequences                      |
| **FTRL**           | Follow-The-Regularized-Leader                                | Online learning with sparse features           | Ads, recommendation systems                    |
| **LAMB**           | Layer-wise Adaptive Moments                                  | Designed for large batch training (e.g., BERT) | High memory cost                               |
| **Lion**           | Sign-based momentum optimizer                                | Lightweight and efficient                      | Large LLMs, scalable deep models               |

---

### **Comparison Summary**

| Optimizer    | Adaptive LR | Momentum      | Computation | Best For                    | Weaknesses                      |
| ------------ | ----------- | ------------- | ----------- | --------------------------- | ------------------------------- |
| **SGD**      | ✘           | ✘             | Low         | Small/simple models         | Slow convergence                |
| **SGD+M**    | ✘           | ✔             | Low         | Deep networks               | Still needs tuning              |
| **NAG**      | ✘           | ✔ (lookahead) | Moderate    | Deep, responsive training   | Slightly complex                |
| **Adagrad**  | ✔           | ✘             | Moderate    | Sparse features (e.g. NLP)  | Rapid LR decay                  |
| **RMSProp**  | ✔           | ✘             | Moderate    | RNNs, non-stationary data   | Requires tuning of decay rate   |
| **Adam**     | ✔           | ✔             | Moderate    | General purpose             | Generalization issues sometimes |
| **Nadam**    | ✔           | ✔ (NAG)       | High        | Sequence tasks (RNNs)       | Slower than Adam                |
| **AdaDelta** | ✔           | ✘             | Moderate    | Old Adagrad replacement     | Outdated                        |
| **LAMB**     | ✔           | ✔             | High        | Large-batch training (LLMs) | Complex and memory intensive    |
| **Lion**     | ✔           | ✔             | Low         | Efficient training at scale | Newer, less widely benchmarked  |

---

### **Popular Use Cases**

| Task Type                         | Recommended Optimizer    |
| --------------------------------- | ------------------------ |
| Simple models or regression       | SGD or SGD with Momentum |
| CNNs (e.g., image classification) | Adam or RMSProp          |
| RNNs / LSTMs                      | RMSProp, Adam, or Nadam  |
| Large Language Models (LLMs)      | Adam, Lion, or LAMB      |
| Sparse feature models (e.g., NLP) | Adagrad, FTRL            |

---

### **Tips for Choosing Optimizers**

- Use **Adam** as the go-to for most use cases.
- Try **SGD + Momentum** for better generalization or fine-tuning.
- Use **RMSProp** for RNNs or time-series models.
- Choose **Lion** or **LAMB** for transformer or large-batch training.
- Always tune **learning rate**—it’s the most sensitive hyperparameter.

---
