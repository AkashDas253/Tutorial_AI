## **Deep Learning (DL)**

---

### **Definition**

Deep Learning is a subfield of Machine Learning that uses **artificial neural networks** with multiple layers (deep architectures) to model complex patterns in data.

---

### **Core Characteristics**

| Concept                     | Description                                                           |
| --------------------------- | --------------------------------------------------------------------- |
| **Neural Networks**         | Composed of layers of interconnected nodes (neurons)                  |
| **Deep Architectures**      | Multiple hidden layers between input and output                       |
| **Representation Learning** | Learns hierarchical features directly from raw data                   |
| **End-to-End Learning**     | Automatically maps input to output without manual feature engineering |

---

### **Types of Neural Networks**

| Network Type                              | Use Cases                                          |
| ----------------------------------------- | -------------------------------------------------- |
| **Feedforward NN (FNN)**                  | Basic regression/classification                    |
| **Convolutional NN (CNN)**                | Image and video processing                         |
| **Recurrent NN (RNN)**                    | Sequence modeling (text, time series)              |
| **LSTM / GRU**                            | Long-term sequence dependencies                    |
| **Transformer**                           | NLP and vision tasks (e.g., BERT, GPT, ViT)        |
| **GAN (Generative Adversarial Networks)** | Image generation, super-resolution                 |
| **Autoencoders**                          | Dimensionality reduction, anomaly detection        |
| **Graph NN (GNN)**                        | Graph-structured data (social networks, molecules) |

---

### **Architecture Components**

| Component                | Description                                                     |
| ------------------------ | --------------------------------------------------------------- |
| **Neuron**               | Basic unit that receives input, applies weights, and activation |
| **Layer**                | A collection of neurons: Input, Hidden, Output                  |
| **Weights & Biases**     | Learnable parameters in the network                             |
| **Activation Functions** | Introduce non-linearity                                         |
| **Loss Function**        | Measures prediction error (e.g., MSE, Cross-Entropy)            |
| **Optimizer**            | Updates weights to minimize loss (e.g., SGD, Adam)              |

---

### **Popular Activation Functions**

| Function             | Purpose                                       |
| -------------------- | --------------------------------------------- |
| **ReLU**             | Fast convergence, handles vanishing gradients |
| **Sigmoid**          | Outputs probability-like values               |
| **Tanh**             | Centered around zero                          |
| **Softmax**          | Normalizes outputs for classification         |
| **Leaky ReLU / ELU** | Solve dead neuron problem                     |

---

### **Popular Optimizers**

| Optimizer              | Characteristics                            |
| ---------------------- | ------------------------------------------ |
| **SGD**                | Simple gradient descent                    |
| **Momentum**           | Adds memory of past gradients              |
| **RMSProp**            | Scales learning rate with gradient history |
| **Adam**               | Combines Momentum + RMSProp (most used)    |
| **Adagrad / Adadelta** | Adaptive learning rate methods             |

---

### **Loss Functions**

| Task               | Loss Function Examples                |
| ------------------ | ------------------------------------- |
| **Classification** | Cross-Entropy, Hinge Loss             |
| **Regression**     | MSE, MAE, Huber Loss                  |
| **Reconstruction** | Binary/Categorical Cross-Entropy, MSE |

---

### **Common Techniques**

* **Dropout**: Regularization by randomly disabling neurons
* **Batch Normalization**: Stabilizes and speeds up training
* **Weight Initialization**: Xavier, He, etc.
* **Learning Rate Scheduling**: Reduces LR over time
* **Early Stopping**: Prevents overfitting
* **Data Augmentation**: Increases training data variety

---

### **Training Process**

1. Initialize weights and biases
2. Forward propagation
3. Compute loss
4. Backpropagation (calculate gradients)
5. Update weights using optimizer
6. Repeat until convergence (epochs)

---

### **Tools & Libraries**

| Framework        | Description                             |
| ---------------- | --------------------------------------- |
| **TensorFlow**   | End-to-end deep learning by Google      |
| **Keras**        | High-level API for TensorFlow           |
| **PyTorch**      | Dynamic deep learning by Meta           |
| **ONNX**         | Interchange format for DL models        |
| **Hugging Face** | Transformers and pre-trained NLP models |
| **FastAI**       | High-level library built on PyTorch     |

---

### **Applications**

* **Computer Vision**: Object detection, image classification, segmentation
* **Natural Language Processing**: Translation, summarization, sentiment analysis
* **Speech**: Recognition, synthesis
* **Generative Models**: Image/art generation, music, design
* **Healthcare**: Disease detection, genomics
* **Autonomous Systems**: Drones, robots, self-driving cars

---

### **Challenges**

* Requires large labeled datasets
* High computational cost (GPUs/TPUs)
* Overfitting on small data
* Explainability/interpretability
* Ethical concerns (bias, misuse)

---

### **Recent Trends in DL**

* **Transformers in vision (ViT, DETR)**
* **Foundation Models & LLMs (GPT, BERT, PaLM)**
* **Multimodal Learning (CLIP, Flamingo)**
* **Self-Supervised Learning (SimCLR, BYOL)**
* **Diffusion Models (Stable Diffusion, DALL·E 3)**
* **Neural Architecture Search (NAS)**
* **Federated + Privacy-Preserving DL**

---
