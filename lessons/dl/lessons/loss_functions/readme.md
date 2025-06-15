## **Loss Functions** in Deep Learning

---

### **Definition**

A **loss function** (or cost function) measures the difference between the predicted output of a model and the actual target output. It quantifies how well or poorly a model is performing.

---

### **Objectives of a Loss Function**

| Objective               | Description                                                                |
| ----------------------- | -------------------------------------------------------------------------- |
| **Guide Learning**      | Helps model learn by updating weights via backpropagation                  |
| **Quantify Error**      | Measures how far off predictions are from true values                      |
| **Optimization Target** | The function minimized by optimizers during training                       |
| **Problem Specific**    | Different tasks (regression, classification) need different loss functions |

---

### **Loss Function Types by Task**

| Task Type          | Common Loss Functions                                  |
| ------------------ | ------------------------------------------------------ |
| **Regression**     | Mean Squared Error, Mean Absolute Error, Huber Loss    |
| **Classification** | Cross-Entropy, Hinge Loss, Kullback-Leibler Divergence |
| **Ranking**        | Contrastive Loss, Triplet Loss                         |
| **Imbalance**      | Focal Loss, Weighted CE Loss                           |
| **Generative**     | Adversarial Loss, Perceptual Loss, Wasserstein Loss    |

---

### **Common Regression Loss Functions**

| Loss Function     | Formula                                                | Description                                               | Use Cases               |                              |                    |
| ----------------- | ------------------------------------------------------ | --------------------------------------------------------- | ----------------------- | ---------------------------- | ------------------ |
| **MSE (L2 Loss)** | \$ \frac{1}{n} \sum\_{i=1}^{n}(y\_i - \hat{y}\_i)^2 \$ | Penalizes large errors more; smooth gradient              | Linear regression, DNNs |                              |                    |
| **MAE (L1 Loss)** | \$ \frac{1}{n} \sum\_{i=1}^{n}                         | y\_i - \hat{y}\_i                                         | \$                      | Penalizes all errors equally | Robust to outliers |
| **Huber Loss**    | Combines MSE and MAE (uses threshold δ)                | Less sensitive to outliers                                | Regression with noise   |                              |                    |
| **Log-Cosh**      | \$ \sum \log(\cosh(\hat{y} - y)) \$                    | Smooth MAE; behaves like MSE near 0 and like MAE far away | Balanced performance    |                              |                    |

---

### **Common Classification Loss Functions**

| Loss Function             | Formula (Binary Cross-Entropy)                           | Description                                    | Use Cases                     |
| ------------------------- | -------------------------------------------------------- | ---------------------------------------------- | ----------------------------- |
| **Binary Cross-Entropy**  | \$-y \log(\hat{y}) - (1-y)\log(1-\hat{y})\$              | For binary labels (0 or 1)                     | Binary classification         |
| **Categorical CE**        | \$ -\sum\_{i} y\_i \log(\hat{y}\_i) \$                   | Multiclass with one-hot labels                 | Softmax output, image classes |
| **Sparse Categorical CE** | Similar to CCE, but labels are integers                  | Avoids one-hot encoding                        | Faster with many classes      |
| **Hinge Loss**            | \$ \max(0, 1 - y \cdot \hat{y}) \$                       | Used in SVMs; margin-based                     | Binary classification (SVMs)  |
| **KL Divergence**         | \$ \sum y\_i \log\left(\frac{y\_i}{\hat{y}\_i}\right) \$ | Distance between two probability distributions | Probabilistic models          |
| **Focal Loss**            | \$ -(1 - \hat{y})^\gamma y \log(\hat{y}) \$              | Down-weights easy examples                     | Imbalanced datasets           |
| **Label Smoothing CE**    | Slightly flattens one-hot vectors before CE              | Prevents overconfidence                        | Image, NLP classification     |

---

### **Advanced & Specialized Loss Functions**

| Loss Function             | Purpose                                             | Use Cases                           |
| ------------------------- | --------------------------------------------------- | ----------------------------------- |
| **Contrastive Loss**      | Encourages similar inputs to have closer embeddings | Siamese networks, face verification |
| **Triplet Loss**          | Anchor-Positive-Negative distance training          | FaceNet, similarity learning        |
| **Cosine Embedding Loss** | Uses cosine similarity                              | NLP and recommendation systems      |
| **CTC Loss**              | For unaligned sequence learning                     | Speech, handwriting recognition     |
| **Dice Loss**             | Measures overlap of predicted and actual segments   | Semantic segmentation               |
| **IoU Loss**              | Improves intersection-over-union                    | Object detection, segmentation      |
| **Perceptual Loss**       | Uses feature distances from pretrained nets         | Style transfer, super-resolution    |
| **Wasserstein Loss**      | Measures "earth mover’s distance" between dists     | GAN training (WGAN)                 |
| **Adversarial Loss**      | Used in GANs: discriminator vs generator            | Image, text generation              |

---

### **Loss Function Characteristics Comparison**

| Loss Function | Robust to Outliers | Smooth Gradient | Use in Classification | Use in Regression |
| ------------- | ------------------ | --------------- | --------------------- | ----------------- |
| MSE           | ✘                  | ✔               | ✘                     | ✔                 |
| MAE           | ✔                  | ✘ (not smooth)  | ✘                     | ✔                 |
| Huber         | ✔ (tunable)        | ✔               | ✘                     | ✔                 |
| Cross-Entropy | ✘                  | ✔               | ✔                     | ✘                 |
| Hinge         | ✘                  | ✘ (not smooth)  | ✔                     | ✘                 |
| Focal         | ✔                  | ✔               | ✔                     | ✘                 |
| Dice/IoU      | ✔                  | ✘               | ✔                     | ✘                 |

---

### **Tips for Choosing Loss Functions**

* Use **MSE/MAE** for continuous value prediction.
* Use **Cross-Entropy** for classification (binary/multiclass).
* Use **Focal Loss** for class imbalance.
* Use **Contrastive/Triplet** for metric learning.
* Use **Dice/IoU Loss** for segmentation.
* Use **CTC Loss** for unaligned sequence-to-sequence tasks.

---
