# 📊 Results, Analysis and Interpretability

## 🔹 Model Performance Comparison

| Model                  | Accuracy | Macro F1-Score |
| ---------------------- | -------- | -------------- |
| Model A (Vanilla LSTM) | 0.65     | 0.63           |
| Model B (Stacked LSTM) | 0.81     | 0.81           |
| Model C (CNN-LSTM)     | **0.91** | **0.91**       |

---

## 🔹 Training and Validation Performance


![Validation Accuracy](./images/validation_accuracy.png)

### 📈 Validation Accuracy Comparison


* Model A stabilizes at ~0.69 → **underfitting**
* Model B stabilizes at ~0.88 → **moderate performance**
* Model C reaches ~0.94 quickly → **best convergence**

### 📉 Validation Loss Comparison



* Model A shows high loss (~0.91) → poor learning
* Model B improves (~0.64) → better learning
* Model C achieves lowest loss (~0.21) → efficient learning

---

## 🔹 Results and Analysis

### Model A — Vanilla LSTM

* Struggles with complex temporal dependencies
* High confusion between similar classes (0,1,2 and 3,4)
* Underfits the data

### Model B — Stacked LSTM

* Improved temporal learning
* Better classification across most classes
* Still confusion between class 3 and 4

### Model C — CNN-LSTM

* Best performing model
* Almost perfect classification for most classes
* Minor confusion between class 3 and 4

---

## ⭐ Why Model C Performs Best

* **CNN layers extract local patterns** (peaks, motion changes)
* **Noise reduction** improves signal quality
* **LSTM captures temporal dependencies**
* **Hierarchical learning** (CNN → features, LSTM → sequence)
* Leads to **better generalization and faster convergence**

---

## ⏱️ Inference Latency Analysis

| Model   | Latency (seconds) |
| ------- | ----------------- |
| Model A | 0.100             |
| Model B | **0.072**         |
| Model C | 0.153             |

### 🔹 Observations

* Model B is the **fastest**
* Model C is the **slowest due to higher complexity**
* Model A has moderate latency

### ⚖️ Trade-off

| Model   | Accuracy | Speed  |
| ------- | -------- | ------ |
| Model A | Low      | Medium |
| Model B | Moderate | Fast   |
| Model C | High     | Slow   |

👉 Model C → Best accuracy
👉 Model B → Best for real-time systems

---

## 🔍 Temporal Interpretability using Grad-CAM

### 📊 Grad-CAM Overlay (Signal + Importance)

![GradCAM Overlay](./images/gradcam_overlay.png)

### 🔥 Grad-CAM Heatmaps

![GradCAM Heatmap](./images/gradcam_heatmap.png)

---

## 🔹 Observations

### Activity 1 — Walking (Dynamic)

* High importance on **peaks and fluctuations**
* Focus on **motion cycles and transitions**

### Activity 2 — Sitting (Static)

* Importance concentrated in **stable regions**
* Low variation across time steps

---

## 🧠 Interpretation

* **Dynamic activities** → model focuses on transition points
* **Static activities** → model focuses on steady-state signals

Grad-CAM confirms that:

* Model learns **meaningful temporal features**
* Predictions are **interpretable and reliable**

---

## 🎯 Final Conclusion

The CNN-LSTM model achieves the best performance with **91% accuracy and 0.91 macro F1-score**, demonstrating its ability to capture both spatial and temporal features effectively.

* Model A → Underfits and performs poorly
* Model B → Balanced performance
* Model C → Best accuracy and feature learning

However, Model C comes with higher computational cost and latency.
Thus:

* Use **Model C** for accuracy-critical applications
* Use **Model B** for real-time or resource-constrained systems
---
