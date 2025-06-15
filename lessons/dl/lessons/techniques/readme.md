## **Core Techniques in Deep Learning**

---

### **1. Data Techniques**

| Technique             | Description                                                                |
| --------------------- | -------------------------------------------------------------------------- |
| **Data Augmentation** | Expands dataset size using transformations (e.g., flips, crops, rotations) |
| **Normalization**     | Scales inputs to have zero mean and unit variance (or \[0,1] scaling)      |
| **Standardization**   | Adjusts distributions per feature; improves convergence                    |
| **Class Balancing**   | Oversampling (e.g., SMOTE), undersampling, or weighted loss                |

---

### **2. Training Techniques**

| Technique                    | Description                                                        |
| ---------------------------- | ------------------------------------------------------------------ |
| **Dropout**                  | Randomly disables neurons to prevent co-adaptation and overfitting |
| **Batch Normalization**      | Normalizes activations per batch to stabilize learning             |
| **Layer Normalization**      | Normalizes across features per sample (used in RNNs, Transformers) |
| **Early Stopping**           | Halts training if validation loss stops improving                  |
| **Gradient Clipping**        | Limits gradient magnitude to prevent exploding gradients           |
| **Learning Rate Scheduling** | Dynamically adjusts learning rate (step decay, cosine annealing)   |
| **Transfer Learning**        | Adapts pretrained models (e.g., ResNet, BERT) to new tasks         |
| **Fine-Tuning**              | Unfreezing layers of a pretrained model and retraining selectively |
| **Curriculum Learning**      | Trains model progressively on harder samples                       |

---

### **3. Optimization Techniques**

| Technique                  | Description                                                 |
| -------------------------- | ----------------------------------------------------------- |
| **Optimizers**             | Algorithms to update weights (SGD, Adam, RMSProp, etc.)     |
| **Weight Initialization**  | Strategies like Xavier or He for better convergence         |
| **Momentum**               | Speeds up learning by leveraging past gradients             |
| **Adaptive LR Methods**    | Adjust learning rate per parameter (Adam, Adagrad, RMSProp) |
| **Regularization (L1/L2)** | Penalizes large weights to control model complexity         |
| **Label Smoothing**        | Prevents overconfidence by softening targets                |

---

### **4. Model-Level Techniques**

| Technique                      | Description                                                         |
| ------------------------------ | ------------------------------------------------------------------- |
| **Skip Connections**           | Adds shortcuts between layers (e.g., ResNet) to ease training       |
| **Attention Mechanisms**       | Focuses on relevant input parts dynamically (e.g., in Transformers) |
| **Residual Learning**          | Helps deep models learn identity mappings                           |
| **Dense Connections**          | Connects each layer to every other (e.g., DenseNet)                 |
| **Multi-Branch Architectures** | Parallel sub-models (e.g., Inception networks)                      |
| **Recurrent Mechanisms**       | Maintains temporal state (e.g., RNN, LSTM, GRU)                     |

---

### **5. Regularization Techniques**

| Technique             | Description                                            |
| --------------------- | ------------------------------------------------------ |
| **L1 Regularization** | Promotes sparsity (adds absolute value penalty)        |
| **L2 Regularization** | Prevents large weights (adds squared penalty)          |
| **Dropout**           | Randomly disables neurons during training              |
| **Data Augmentation** | Helps generalize by increasing training data diversity |
| **Early Stopping**    | Prevents overfitting by monitoring validation loss     |

---

### **6. Loss Function Engineering**

| Technique                      | Description                                                                |
| ------------------------------ | -------------------------------------------------------------------------- |
| **Cross-Entropy**              | For classification tasks                                                   |
| **Focal Loss**                 | For handling class imbalance                                               |
| **Dice Loss / IoU Loss**       | For segmentation tasks                                                     |
| **CTC Loss**                   | For sequence alignment without alignment labels (e.g., speech recognition) |
| **Triplet / Contrastive Loss** | For similarity learning and embeddings                                     |

---

### **7. Advanced Learning Techniques**

| Technique                    | Description                                                         |
| ---------------------------- | ------------------------------------------------------------------- |
| **Self-Supervised Learning** | Learns useful features without explicit labels (e.g., SimCLR, BYOL) |
| **Contrastive Learning**     | Learns embeddings by bringing similar samples closer                |
| **Knowledge Distillation**   | Trains smaller "student" model to mimic a larger "teacher" model    |
| **Multi-Task Learning**      | Trains a model on multiple related tasks simultaneously             |
| **Semi-Supervised Learning** | Leverages small labeled + large unlabeled data                      |
| **Adversarial Training**     | Improves robustness by exposing model to perturbed inputs           |

---

### **8. Deployment-Oriented Techniques**

| Technique              | Description                                                     |
| ---------------------- | --------------------------------------------------------------- |
| **Model Quantization** | Reduces precision (e.g., FP32 → INT8) for deployment efficiency |
| **Pruning**            | Removes unnecessary neurons/connections                         |
| **Distillation**       | Compresses large models into smaller, faster ones               |
| **ONNX Export**        | Converts models to a portable and interoperable format          |
| **Edge Deployment**    | Optimizes models for mobile, browser, IoT deployment            |

---
