## **Architecture Components** in Deep Learning

---

### **1. Neuron (Artificial Neuron)**

| Component               | Description                                                   |
| ----------------------- | ------------------------------------------------------------- |
| **Input**               | Receives weighted signals from previous neurons or input data |
| **Weights**             | Scalars applied to inputs to adjust their influence           |
| **Bias**                | A constant term added to the weighted sum to shift the output |
| **Activation Function** | Applies non-linearity to the output of the neuron             |
| **Output**              | Transmitted to the next layer or as final output              |

---

### **2. Layers**

| Layer Type          | Description                                                                |
| ------------------- | -------------------------------------------------------------------------- |
| **Input Layer**     | Receives raw input data (features)                                         |
| **Hidden Layer(s)** | Intermediate layers performing transformations using weights & activations |
| **Output Layer**    | Produces the final prediction or output                                    |

---

### **3. Weights and Biases**

| Parameter          | Description                                                          |
| ------------------ | -------------------------------------------------------------------- |
| **Weights**        | Learnable parameters that determine signal strength between neurons  |
| **Biases**         | Offsets added to neurons to allow better fit of the model            |
| **Initialization** | Proper initialization (e.g., Xavier, He) helps in faster convergence |

---

### **4. Activation Functions**

| Function            | Description                                                     |
| ------------------- | --------------------------------------------------------------- |
| **ReLU**            | Outputs max(0, x); fast and effective for deep nets             |
| **Sigmoid**         | Outputs values in (0, 1); useful for binary classification      |
| **Tanh**            | Outputs values in (–1, 1); centered and smoother than sigmoid   |
| **Softmax**         | Converts logits to probabilities for multi-class classification |
| **Leaky ReLU, ELU** | Variants of ReLU to handle "dying ReLU" problem                 |

---

### **5. Loss Function**

| Purpose             | Description                                         |
| ------------------- | --------------------------------------------------- |
| **Measures error**  | Quantifies how far predictions are from true values |
| **Guides training** | Drives weight updates via backpropagation           |
| **Examples**        | Cross-Entropy, MSE, Hinge Loss                      |

---

### **6. Optimizer**

| Optimizer            | Description                                     |
| -------------------- | ----------------------------------------------- |
| **Gradient Descent** | Updates weights based on loss gradients         |
| **SGD**              | Basic version with single/batch updates         |
| **Adam**             | Combines momentum and RMSProp; most widely used |
| **Other Examples**   | Adagrad, RMSProp, Nadam, FTRL                   |

---

### **7. Forward Propagation**

| Stage                    | Description                                       |
| ------------------------ | ------------------------------------------------- |
| **Input → Output**       | Passes data through layers sequentially           |
| **Computes activations** | Applies weights, biases, and activation functions |

---

### **8. Backward Propagation (Backpropagation)**

| Purpose                | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| **Computes gradients** | Derivatives of loss w\.r.t. weights and biases           |
| **Chain rule usage**   | Uses calculus to propagate error backward through layers |
| **Enables learning**   | Updates parameters to reduce error over iterations       |

---

### **9. Epoch, Batch, Iteration**

| Term          | Description                                              |
| ------------- | -------------------------------------------------------- |
| **Epoch**     | One full pass through the entire training dataset        |
| **Batch**     | A subset of data used to train the model at one time     |
| **Iteration** | One update step = 1 forward + 1 backward pass on a batch |

---

### **10. Regularization Techniques**

| Technique                | Purpose and Description                                          |
| ------------------------ | ---------------------------------------------------------------- |
| **Dropout**              | Randomly disables neurons during training to prevent overfitting |
| **L1/L2 Regularization** | Adds penalty to large weights to control model complexity        |
| **Batch Normalization**  | Normalizes activations to stabilize and accelerate training      |

---
