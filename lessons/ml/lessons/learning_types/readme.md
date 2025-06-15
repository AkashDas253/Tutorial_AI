## **Learning Paradigms** in Machine Learning

---

### **1. Batch Learning (Offline Learning)**

| Aspect          | Description                                                        |
| --------------- | ------------------------------------------------------------------ |
| **Definition**  | The model is trained on the entire dataset at once.                |
| **Data Access** | Full dataset must be available beforehand.                         |
| **Use Case**    | Static environments where data doesn’t change often.               |
| **Pros**        | Efficient training; globally optimized models.                     |
| **Cons**        | Requires large memory; can't adapt to new data without retraining. |

---

### **2. Online Learning**

| Aspect          | Description                                                               |
| --------------- | ------------------------------------------------------------------------- |
| **Definition**  | The model learns incrementally from a stream of data samples.             |
| **Data Access** | Data arrives in a sequence (one-by-one or in small batches).              |
| **Use Case**    | Real-time systems, financial markets, recommendation systems.             |
| **Pros**        | Adapts to changes quickly; memory efficient.                              |
| **Cons**        | Can be unstable if learning rate and updates are not controlled properly. |

---

### **3. Active Learning**

| Aspect          | Description                                                                |
| --------------- | -------------------------------------------------------------------------- |
| **Definition**  | The model actively selects the most informative data points to be labeled. |
| **Data Access** | Small labeled dataset + large pool of unlabeled data.                      |
| **Use Case**    | Domains with expensive labeling (e.g., medical imaging).                   |
| **Pros**        | Reduces labeling cost; increases efficiency.                               |
| **Cons**        | Requires human-in-the-loop setup.                                          |

---

### **4. Transfer Learning**

| Aspect          | Description                                                            |
| --------------- | ---------------------------------------------------------------------- |
| **Definition**  | Knowledge from one task/domain is reused in a related task/domain.     |
| **Data Access** | Pretrained model + new target dataset.                                 |
| **Use Case**    | When labeled data is scarce in target domain (e.g., fine-tuning BERT). |
| **Pros**        | Reduces training time and data requirements.                           |
| **Cons**        | Risk of negative transfer if domains are too different.                |

---

### **5. Few-Shot / Zero-Shot Learning**

| Paradigm          | Description                                                        |
| ----------------- | ------------------------------------------------------------------ |
| **Few-Shot**      | Learns to generalize from only a few examples per class.           |
| **Zero-Shot**     | Learns to perform tasks without having seen any examples for them. |
| **Use Cases**     | Low-resource languages, rare disease detection, general LLMs.      |
| **Common Models** | GPT, CLIP, T5, meta-learning-based architectures.                  |

---
