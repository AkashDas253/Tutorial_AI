## Types of Machine Learning

---

### **1. Supervised Learning**

| Aspect           | Description                                                                   |
| ---------------- | ----------------------------------------------------------------------------- |
| **Definition**   | Learns a mapping from inputs to outputs using labeled data.                   |
| **Data Type**    | Labeled (input-output pairs).                                                 |
| **Goal**         | Predict the output for new inputs.                                            |
| **Common Tasks** | Classification, Regression                                                    |
| **Examples**     | Email spam detection, house price prediction                                  |
| **Algorithms**   | Linear Regression, Logistic Regression, Decision Trees, SVM, KNN, Naive Bayes |

---

### **2. Unsupervised Learning**

| Aspect           | Description                                              |
| ---------------- | -------------------------------------------------------- |
| **Definition**   | Finds hidden patterns or structures in unlabeled data.   |
| **Data Type**    | Unlabeled (only inputs).                                 |
| **Goal**         | Discover structure, groupings, or representations.       |
| **Common Tasks** | Clustering, Dimensionality Reduction                     |
| **Examples**     | Customer segmentation, topic modeling, anomaly detection |
| **Algorithms**   | K-Means, Hierarchical Clustering, DBSCAN, PCA, t-SNE     |

---

### **3. Semi-Supervised Learning**

| Aspect           | Description                                                        |
| ---------------- | ------------------------------------------------------------------ |
| **Definition**   | Uses both labeled and unlabeled data to improve learning accuracy. |
| **Data Type**    | Few labeled + many unlabeled samples.                              |
| **Goal**         | Leverage unlabeled data to boost performance.                      |
| **Common Tasks** | Same as supervised learning                                        |
| **Examples**     | Medical image classification, speech analysis with limited labels  |
| **Techniques**   | Self-training, co-training, graph-based methods                    |

---

### **4. Reinforcement Learning**

| Aspect           | Description                                                           |
| ---------------- | --------------------------------------------------------------------- |
| **Definition**   | An agent learns to make decisions by interacting with an environment. |
| **Data Type**    | Sequential feedback (rewards/punishments).                            |
| **Goal**         | Maximize cumulative reward over time.                                 |
| **Common Tasks** | Sequential decision-making, control systems                           |
| **Examples**     | Game playing (e.g., AlphaGo), robotics, recommendation systems        |
| **Key Elements** | Agent, Environment, Reward, Policy, Value Function                    |
| **Algorithms**   | Q-Learning, SARSA, Deep Q-Networks (DQN), Policy Gradients            |

---

### **5. Self-Supervised Learning**

| Aspect           | Description                                                     |
| ---------------- | --------------------------------------------------------------- |
| **Definition**   | Learns representations from unlabeled data using pretext tasks. |
| **Data Type**    | Unlabeled, labels are generated internally.                     |
| **Goal**         | Enable models to learn useful features without manual labeling. |
| **Common Tasks** | Pretraining for vision/language tasks                           |
| **Examples**     | BERT (NLP), SimCLR (vision), GPT (language modeling)            |
| **Techniques**   | Masked language modeling, contrastive learning                  |

---
