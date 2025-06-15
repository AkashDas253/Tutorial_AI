## **Wasserstein GAN (WGAN)**

---

### **Overview**

Wasserstein GAN (WGAN) is a variant of GAN designed to solve stability and convergence issues in traditional GANs. It replaces the **Jensen-Shannon divergence** with the **Wasserstein (Earth Mover’s) distance**, which gives smoother gradients and reduces mode collapse.

Proposed in the paper:
**"Wasserstein GAN" – Arjovsky et al., 2017**

---

### **Core Idea**

* Traditional GANs use a discriminator (binary classifier) → leads to vanishing gradients.
* WGAN replaces it with a **critic** that scores samples (not classifies).
* Optimizes the **Earth Mover (EM) distance** between the real and generated data distributions.

---

### **Earth Mover (Wasserstein-1) Distance**

The Wasserstein-1 distance between distributions \$P\_r\$ (real) and \$P\_g\$ (generated):

$$
W(P_r, P_g) = \inf_{\gamma \in \Pi(P_r, P_g)} \mathbb{E}_{(x, y) \sim \gamma}[\|x - y\|]
$$

In simple terms:
How much "mass" needs to be moved and how far, to turn \$P\_g\$ into \$P\_r\$.

---

### **Modified Objective Function**

#### **Original GAN:**

$$
\min_G \max_D \mathbb{E}_{x \sim P_r}[\log D(x)] + \mathbb{E}_{z \sim P_z}[\log(1 - D(G(z)))]
$$

#### **WGAN:**

$$
\min_G \max_{f \in \mathcal{F}} \mathbb{E}_{x \sim P_r}[f(x)] - \mathbb{E}_{z \sim P_z}[f(G(z))]
$$

Where \$f\$ is a **1-Lipschitz function**, enforced by **weight clipping** or **gradient penalty**.

---

### **Key Components**

| Component                | Description                                                                      |
| ------------------------ | -------------------------------------------------------------------------------- |
| **Critic**               | Replaces the discriminator, gives scalar scores (no sigmoid)                     |
| **Loss Function**        | Measures Wasserstein distance: difference between scores                         |
| **Lipschitz Constraint** | Ensures smooth critic function (enforced via weight clipping / gradient penalty) |

---

### **Training Process**

1. **Sample real** data and generate **fake** data.
2. **Critic outputs real-valued scores** (not probabilities).
3. **Loss**: difference between real and fake average scores.
4. **Train critic multiple times** per generator update (e.g., 5:1).
5. **Clip weights** in original WGAN (or use gradient penalty in WGAN-GP).

---

### **WGAN vs GAN**

| Feature              | GAN                             | WGAN                            |
| -------------------- | ------------------------------- | ------------------------------- |
| Discriminator Output | Probability (0–1)               | Score (real number)             |
| Objective Function   | Cross-Entropy (JS divergence)   | Wasserstein Distance            |
| Stability            | Unstable (mode collapse common) | More stable                     |
| Gradient Behavior    | Can vanish                      | Better gradients                |
| Lipschitz Constraint | No                              | Yes (via weight clipping or GP) |

---

### **Improvement – WGAN-GP**

**WGAN-GP** (Wasserstein GAN with Gradient Penalty) improves WGAN by replacing **weight clipping** with **gradient penalty**:

$$
\lambda \mathbb{E}_{\hat{x} \sim P_{\hat{x}}} \left[(\|\nabla_{\hat{x}} D(\hat{x})\|_2 - 1)^2 \right]
$$

Where \$\hat{x}\$ is sampled from points between real and fake data.

| Benefit of WGAN-GP                          |
| ------------------------------------------- |
| Smooth enforcement of 1-Lipschitz condition |
| Improved training stability                 |
| Avoids weight clipping drawbacks            |

---

### **Best Practices**

* Use **RMSProp** or **Adam** optimizer with small learning rates (e.g., 0.00005).
* **Avoid BatchNorm** in critic.
* **Train critic** multiple times per generator step (usually 5).
* Use **gradient penalty** (WGAN-GP) over weight clipping.

---

### **Applications**

* High-quality image generation
* Stable training on complex data
* Large-scale GANs (e.g., BigGANs use WGAN-based ideas)

---

### **Libraries & Resources**

* `torchgan` or PyTorch implementations
* TensorFlow examples: `tf.keras` WGAN
* NVIDIA’s StyleGAN builds on WGAN-GP foundations

---
