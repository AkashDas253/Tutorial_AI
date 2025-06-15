## **Activation Functions**

---

### **Definition**

**Activation functions** are mathematical equations that determine the output of a neural network node (neuron). They introduce non-linearity into the model, allowing the network to learn complex patterns and make accurate predictions.

---

### **Why Are Activation Functions Important?**

| Purpose                     | Description                                                      |
| --------------------------- | ---------------------------------------------------------------- |
| **Non-Linearity**           | Helps neural networks capture complex, non-linear relationships. |
| **Gradient-Based Learning** | Enables use of backpropagation to adjust weights.                |
| **Output Control**          | Maps neuron outputs into a desired range (e.g., probabilities).  |
| **Efficient Training**      | Some functions accelerate convergence and stabilize training.    |

---

### **Categories of Activation Functions**

| Type                  | Examples                  |
| --------------------- | ------------------------- |
| **Linear**            | Identity                  |
| **Non-Linear**        | ReLU, Sigmoid, Tanh, etc. |
| **Piecewise Linear**  | ReLU, Leaky ReLU, PReLU   |
| **Smooth Non-Linear** | Sigmoid, Tanh             |
| **Probabilistic**     | Softmax                   |

---

### **Types of Activation Functions**

| Name           | Formula                                                                     | Range                 | Type          | Key Use Cases                     | Limitations / Notes                          |
| -------------- | --------------------------------------------------------------------------- | --------------------- | ------------- | --------------------------------- | -------------------------------------------- |
| **Identity**   | \$f(x) = x\$                                                                | \$(-\infty, \infty)\$ | Linear        | Regression output                 | No non-linearity; not suitable for deep nets |
| **Sigmoid**    | \$f(x) = \frac{1}{1 + e^{-x}}\$                                             | \$(0, 1)\$            | Smooth        | Binary classification output      | Vanishing gradient; not zero-centered        |
| **Tanh**       | \$f(x) = \tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}\$                     | \$(-1, 1)\$           | Smooth        | RNNs, NLP tasks                   | Vanishing gradient (less than sigmoid)       |
| **ReLU**       | \$f(x) = \max(0, x)\$                                                       | $\[0, \infty)\$       | Piecewise     | Hidden layers (CNNs, MLPs)        | Dying ReLU (neurons stuck at 0)              |
| **Leaky ReLU** | \$f(x) = \max(0.01x, x)\$                                                   | \$(-\infty, \infty)\$ | Piecewise     | ReLU with negative slope          | Needs slope tuning; small negative outputs   |
| **PReLU**      | \$f(x) = \max(ax, x)\$ (where \$a\$ is learnable)                           | \$(-\infty, \infty)\$ | Parametric    | Deep nets, adaptiveness           | Learnable parameter may overfit              |
| **ELU**        | \$f(x) = \begin{cases} x & x > 0 \ \alpha(e^x - 1) & x \leq 0 \end{cases}\$ | \$(-\alpha, \infty)\$ | Smooth        | Zero-centered learning            | More complex; slower computation             |
| **Swish**      | \$f(x) = x \cdot \text{sigmoid}(x)\$                                        | \$(-\infty, \infty)\$ | Smooth        | EfficientNet, modern deep nets    | Non-monotonic; computationally heavier       |
| **Softmax**    | \$f(x\_i) = \frac{e^{x\_i}}{\sum\_{j} e^{x\_j}}\$                           | \$(0, 1)\$            | Probabilistic | Multi-class classification output | Only used in output layer                    |

---

### **Comparison Summary**

| Property              | Sigmoid | Tanh    | ReLU    | Leaky ReLU | PReLU   | ELU     | Swish    | Softmax |
| --------------------- | ------- | ------- | ------- | ---------- | ------- | ------- | -------- | ------- |
| **Range**             | (0, 1)  | (–1, 1) | \[0, ∞) | (–∞, ∞)    | (–∞, ∞) | (–α, ∞) | (–∞, ∞)  | (0, 1)  |
| **Zero-centered**     | ✘       | ✔       | ✘       | ✔          | ✔       | ✔       | ✔        | ✘       |
| **Smooth**            | ✔       | ✔       | ✘       | ✘          | ✘       | ✔       | ✔        | ✔       |
| **Gradient Friendly** | ✘       | ✘       | ✔       | ✔          | ✔       | ✔       | ✔        | ✔       |
| **Popular Use**       | Output  | RNNs    | Hidden  | Hidden     | Hidden  | Hidden  | DeepNets | Output  |

---

### **Best Practices**

* Use **ReLU** for most hidden layers for speed and simplicity.
* Use **Softmax** for **multi-class classification** outputs.
* Use **Sigmoid** for **binary classification** outputs.
* Use **Tanh/ELU/Swish** if ReLU does not perform well or you face dead neurons.
* Use **PReLU/Leaky ReLU** to avoid ReLU’s dying neuron issue.

---
