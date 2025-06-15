## **Architectures in Artificial Intelligence (AI)**

AI **architectures** define the structural and functional design of intelligent systems. These architectures govern how AI components such as knowledge, learning, reasoning, and perception interact.

---

### **I. Symbolic AI (Good Old-Fashioned AI – GOFAI)**

| Feature                      | Description                            |
| ---------------------------- | -------------------------------------- |
| **Knowledge-driven**         | Uses explicit symbols and logic rules  |
| **Deterministic behavior**   | Output is logically deduced from input |
| **Human-readable reasoning** | Easy to trace decisions                |

#### Popular Architectures:

* **Production Systems** – Rules (`IF-THEN`) and facts
* **Semantic Networks** – Nodes and relationships
* **Frame-Based Systems** – Data structures for stereotypical situations
* **Logic-Based Systems** – Propositional / first-order logic

---

### **II. Subsymbolic AI (Connectionist Approach)**

| Feature                   | Description                            |
| ------------------------- | -------------------------------------- |
| **Data-driven**           | Learns from examples rather than rules |
| **Statistical or neural** | Mimics brain structure using layers    |
| **Opaque reasoning**      | Difficult to interpret                 |

#### Common Architectures:

* **Artificial Neural Networks (ANNs)** – Basic multilayer perceptrons
* **Convolutional Neural Networks (CNNs)** – Spatial hierarchies in vision
* **Recurrent Neural Networks (RNNs)** – Sequence modeling
* **Transformers** – Attention-based, parallel processing (e.g., GPT, BERT)
* **Autoencoders** – Dimensionality reduction or denoising
* **GANs (Generative Adversarial Networks)** – Competing networks for data generation

---

### **III. Hybrid AI Architectures**

| Feature                                  | Description                                 |
| ---------------------------------------- | ------------------------------------------- |
| **Combines symbolic and subsymbolic AI** | Aims for transparency + adaptability        |
| **Reasoning + Learning**                 | Use rules + ML for robust, interpretable AI |

#### Examples:

* **Neurosymbolic Architectures** – Combine neural perception with logic reasoning
* **Neuro-Fuzzy Systems** – Neural networks with fuzzy inference (e.g., ANFIS)
* **Transformer + Knowledge Graph** – Used in biomedical and finance AI

---

### **IV. Cognitive Architectures**

| Feature                         | Description                                   |
| ------------------------------- | --------------------------------------------- |
| **Inspired by human cognition** | Mimic memory, attention, learning, etc.       |
| **Modular systems**             | Include reasoning, learning, language, vision |

#### Major Architectures:

* **SOAR** – General cognitive modeling (goal-directed behavior)
* **ACT-R (Adaptive Control of Thought-Rational)** – Modular, symbolic/subsymbolic
* **CLARION** – Combines explicit and implicit processes
* **Sigma** – Graphical models + cognitive processing

---

### **V. Agent-Based Architectures**

| Feature                              | Description                      |
| ------------------------------------ | -------------------------------- |
| **Autonomous entities**              | Act in environment, pursue goals |
| **Perception-Reasoning-Action loop** | Sense, plan, and act accordingly |

#### Architectures:

* **Reactive Agent Architecture** – Responds directly to stimuli (e.g., Subsumption)
* **Deliberative Agent Architecture** – Builds internal world model (BDI: Belief-Desire-Intention)
* **Hybrid Agent Architecture** – Combines reactive and deliberative layers

---

### **VI. Modular AI Systems Architecture**

Used in practical, real-world AI system design.

| Module               | Role                                |
| -------------------- | ----------------------------------- |
| **Input**            | Sensors, data APIs                  |
| **Perception**       | NLP, Vision, Audio Processing       |
| **Knowledge Base**   | Ontologies, facts, world models     |
| **Reasoning Engine** | Logical or probabilistic inference  |
| **Learning Module**  | ML/DL for model updating            |
| **Planning Module**  | Pathfinding, decision logic         |
| **Action Module**    | Robotics, recommendations, response |
| **Interface Layer**  | UI, APIs, human interaction         |

---

### **VII. Cloud + Edge AI Architectures**

Used in deployment of AI models at scale.

| Type                   | Description                                    |
| ---------------------- | ---------------------------------------------- |
| **Cloud AI**           | Centralized model processing (e.g., AWS, GCP)  |
| **Edge AI**            | Run AI models on devices (IoT, mobile, drones) |
| **Federated Learning** | Distributed training without sharing data      |

---

### **VIII. Explainable AI (XAI) Architectures**

| Goal                 | Make black-box AI models interpretable       |
| -------------------- | -------------------------------------------- |
| **Model-Agnostic**   | LIME, SHAP, anchors for any ML model         |
| **Model-Specific**   | Tree regularization, attention visualization |
| **Surrogate Models** | Simplified interpretable versions of models  |

---

### **IX. Reinforcement Learning Architectures**

| Component          | Role                            |
| ------------------ | ------------------------------- |
| **Agent**          | Learns and acts                 |
| **Environment**    | Provides feedback               |
| **Policy Network** | Decides action from state       |
| **Value Function** | Predicts expected reward        |
| **Replay Memory**  | Stores experiences for learning |
| **Examples**       | DQN, PPO, A3C, AlphaZero        |

---

### **Summary Table**

| Architecture Type          | Examples / Usage                         |
| -------------------------- | ---------------------------------------- |
| **Symbolic AI**            | Expert systems, logic solvers            |
| **Subsymbolic AI**         | Neural networks, deep learning           |
| **Hybrid AI**              | IBM Project Debater, neuro-symbolic AI   |
| **Cognitive AI**           | ACT-R, SOAR                              |
| **Agent-Based**            | Robotic control, game AI                 |
| **Modular Systems**        | Industrial and real-time AI applications |
| **Cloud/Edge AI**          | Scalable AI deployment                   |
| **Explainable AI**         | Regulatory and safety-critical domains   |
| **Reinforcement Learning** | Game AI, robotics, finance               |

---
