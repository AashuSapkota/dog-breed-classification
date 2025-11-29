Here is a clean, well-structured **README.md** based on your proposal — formatted for GitHub, concise but complete:

---

# Hierarchical Deep Learning Framework for Multi-Granularity Dog Breed Classification

This project implements a **hierarchical dog-breed classification system** that predicts both:

* **Fine-grained classes** — 120 dog breeds
* **Coarse classes** — 7 major AKC breed groups

Using a **single input image**, the model performs both tasks simultaneously using transfer learning and state-of-the-art CNN architectures.

---

## 📌 Problem Overview

Real-world animal recognition tasks (veterinary diagnostics, shelters, pet identification systems) often require **multiple levels of granularity**:

* Sometimes it is sufficient to know the *group* (e.g., “Terrier”).
* In other situations, identifying the *exact breed* (e.g., “Scottish Terrier”) is essential.

This project compares three leading CNN architectures — **MobileNetV2**, **ResNet50**, and **EfficientNetB0** — to evaluate their effectiveness in learning both coarse and fine-grained canine features under a unified hierarchical framework.

---

## 📂 Dataset

This work uses the **Kaggle Dog Breed Identification Dataset**, containing:

* **10,222** labeled training images
* **10,357** unlabeled test images
* All images are RGB JPEGs with varying resolutions
* **120 fine-grained breeds** based on Kaggle labels
* **7 AKC-defined breed groups**, mapped from the fine-grained labels:

  * **Sporting** (Retrievers, Spaniels, …)
  * **Hound** (Beagle, Greyhound, …)
  * **Working** (Boxer, Rottweiler, …)
  * **Terrier** (Bull Terrier, Scottish Terrier, …)
  * **Toy** (Chihuahua, Pug, …)
  * **Non-Sporting** (Bulldog, Poodle, …)
  * **Herding** (German Shepherd, Collie, …)

These group labels follow official AKC taxonomy — no external data required.

---

## 🧠 Methodology

### **1. Architecture Comparison**

Three CNN models are evaluated:

* **MobileNetV2** – lightweight, efficient baseline using depthwise separable convolutions
* **ResNet50** – deep residual network with skip connections
* **EfficientNetB0** – uses compound scaling for optimal accuracy vs. efficiency

### **2. Hierarchical Classification Setup**

Each model is trained for **dual-output prediction**:

1. **Fine-Grained Level:** 120 dog breeds
2. **Coarse Level:** 7 AKC breed groups

All models use:

* **Transfer learning** from ImageNet
* **TensorFlow 2.x / Keras**
* **GPU-accelerated training (Google Colab)**

---

## 📊 Evaluation Metrics

### **Classification Performance**

* Accuracy, precision, recall, F1-score
* Per-class accuracy
* Confusion matrices
* Top-5 accuracy for fine-grained predictions
* Hierarchical consistency (coarse + fine predictions alignment)

### **Architecture Efficiency**

* Training time
* Inference time
* Model size & number of parameters
* Memory usage
* Accuracy vs. computational cost trade-offs

### **Error Analysis**

* Confusions within same group
* Misclassifications across different groups
* Breed pairs commonly confused due to visual similarity

---

## 🗓️ Work Plan

| **Week** | **Activities**                                                                                            |
| -------- | --------------------------------------------------------------------------------------------------------- |
| **1**    | Build breed-to-group mappings; implement ResNet50 and EfficientNetB0; design dual-output pipeline.        |
| **2**    | Train MobileNetV2 on both classification levels; run evaluation and learning curve analysis.              |
| **3**    | Train ResNet50 & EfficientNetB0; compare architectures on both granularity levels.                        |
| **4**    | Perform hierarchical consistency checks; visualize errors; finalize comparisons and prepare final report. |

---
