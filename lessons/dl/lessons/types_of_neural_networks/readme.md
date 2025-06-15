## **Types of Neural Networks**

---

### **1. Feedforward Neural Network (FNN)**

| Feature        | Description                                       |
| -------------- | ------------------------------------------------- |
| **Structure**  | Layers arranged sequentially; no cycles or loops. |
| **Flow**       | Data flows from input → hidden layers → output.   |
| **Use Cases**  | Basic classification and regression tasks.        |
| **Limitation** | Cannot handle sequential or temporal data.        |

---

### **2. Convolutional Neural Network (CNN)**

| Feature            | Description                                                   |
| ------------------ | ------------------------------------------------------------- |
| **Special Layers** | Convolutional layers, pooling layers, fully connected layers. |
| **Strength**       | Captures spatial hierarchies in data.                         |
| **Use Cases**      | Image classification, object detection, medical imaging.      |
| **Variants**       | LeNet, AlexNet, VGG, ResNet, EfficientNet.                    |

---

### **3. Recurrent Neural Network (RNN)**

| Feature                | Description                                                       |
| ---------------------- | ----------------------------------------------------------------- |
| **Looped Connections** | Outputs from neurons are fed back into the network.               |
| **Strength**           | Processes sequential data by retaining memory of previous inputs. |
| **Use Cases**          | Time series forecasting, language modeling, speech recognition.   |
| **Limitation**         | Struggles with long-term dependencies (vanishing gradients).      |

---

### **4. Long Short-Term Memory (LSTM) & Gated Recurrent Unit (GRU)**

| Feature                  | Description                                           |
| ------------------------ | ----------------------------------------------------- |
| **Improvement over RNN** | Introduces gates to control information flow.         |
| **Strength**             | Captures long-range dependencies and context.         |
| **Use Cases**            | Text generation, machine translation, video analysis. |

---

### **5. Transformer**

| Feature            | Description                                                              |
| ------------------ | ------------------------------------------------------------------------ |
| **Architecture**   | Based entirely on self-attention mechanisms, no recurrence.              |
| **Strength**       | Highly parallel, scalable, captures long-range dependencies effectively. |
| **Use Cases**      | NLP (e.g., BERT, GPT), vision (e.g., ViT), speech.                       |
| **Popular Models** | BERT, GPT, T5, ViT, LLaMA, PaLM.                                         |

---

### **6. Generative Adversarial Network (GAN)**

| Feature       | Description                                                      |
| ------------- | ---------------------------------------------------------------- |
| **Structure** | Two models: Generator and Discriminator in adversarial training. |
| **Strength**  | Generates highly realistic data (images, audio, text).           |
| **Use Cases** | Image synthesis, deepfakes, super-resolution, style transfer.    |

---

### **7. Autoencoder**

| Feature       | Description                                             |
| ------------- | ------------------------------------------------------- |
| **Structure** | Encoder compresses data, decoder reconstructs it.       |
| **Strength**  | Learns data representations and reconstruction.         |
| **Use Cases** | Dimensionality reduction, anomaly detection, denoising. |

---

### **8. Graph Neural Network (GNN)**

| Feature             | Description                                                 |
| ------------------- | ----------------------------------------------------------- |
| **Works on Graphs** | Nodes represent entities; edges represent relationships.    |
| **Strength**        | Captures dependencies in graph-structured data.             |
| **Use Cases**       | Social networks, recommendation systems, molecular biology. |
| **Variants**        | GCN, GAT, GraphSAGE, PinSAGE.                               |

---

### **9. Radial Basis Function Network (RBFN)**

| Feature       | Description                                          |
| ------------- | ---------------------------------------------------- |
| **Structure** | Uses radial basis functions as activation functions. |
| **Strength**  | Good for function approximation and interpolation.   |
| **Use Cases** | Control systems, regression, time series.            |

---

### **10. Modular Neural Network**

| Feature       | Description                                                      |
| ------------- | ---------------------------------------------------------------- |
| **Structure** | Consists of independent networks (modules) performing sub-tasks. |
| **Strength**  | Enhances interpretability and fault tolerance.                   |
| **Use Cases** | Multi-task learning, robotics, hybrid systems.                   |

---
