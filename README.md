# Continual Learning with Adaptive Pruning: Balancing Efficiency and Memory Retention

This project explores **continual learning** on **Split CIFAR-10** using three different strategies:

1. **Naive Training** (baseline)
2. **Elastic Weight Consolidation (EWC)**
3. **Adaptive Pruning + EWC**

The goal of this project is to study **catastrophic forgetting** in neural networks while balancing two important objectives:

- **Memory Retention** → preserving knowledge from previously learned tasks
- **Efficiency** → reducing model complexity using pruning

---

## 📌 Project Motivation

Traditional deep learning models perform well when trained on a fixed dataset, but they struggle in **continual learning settings**, where tasks arrive sequentially over time.  
When trained on new tasks, models often forget previously learned information — a phenomenon known as **catastrophic forgetting**.

This project investigates whether **adaptive pruning** can be combined with **EWC** to create a model that is both:

- **more efficient (sparser)**
- **better at retaining previous knowledge**

---

## 🎯 Objectives

- Implement a **continual learning pipeline** using **PyTorch** and **Avalanche**
- Compare **Naive** and **EWC** strategies on Split CIFAR-10
- Introduce **Adaptive Pruning** to improve efficiency
- Analyze the trade-off between:
  - **Accuracy**
  - **Loss**
  - **Sparsity**
  - **Memory Retention**

---

## 🛠️ Technologies Used

- **Python**
- **PyTorch**
- **Avalanche**
- **Torchvision**
- **Matplotlib**
- **Pandas**
- **Google Colab / Jupyter Notebook**

---

## 📂 Dataset

### **Split CIFAR-10**
The CIFAR-10 dataset is divided into multiple sequential tasks (experiences), where the model learns classes incrementally instead of all at once.

This setup simulates a **continual learning environment**.

---

## 🧠 Methods Used

### 1. **Naive Training**
A standard continual learning baseline where the model is trained sequentially on tasks **without any forgetting mitigation**.

**Expected behavior:**  
- Learns current task
- Forgets previous tasks quickly

---

### 2. **Elastic Weight Consolidation (EWC)**
EWC reduces catastrophic forgetting by preserving parameters that are important for previously learned tasks.

**Expected behavior:**  
- Better memory retention than Naive
- More stable continual learning performance

---

### 3. **Adaptive Pruning + EWC**
Adaptive pruning progressively removes less important weights from the model after each task while EWC helps preserve important knowledge.

This strategy is used to study whether a model can become:

- **more efficient**
- **more sparse**
- while still maintaining acceptable continual learning performance

**Expected behavior:**  
- Increased sparsity
- Better efficiency
- Slight trade-off in performance depending on pruning strength

---

## 📊 Experiments Performed

The notebook includes the following experiments:

- **Naive Training**
- **Naive Accuracy Graph**
- **EWC Training**
- **EWC Accuracy Graph**
- **EWC Loss Graph**
- **Adaptive Pruning + EWC Training**
- **Adaptive Pruning + EWC Accuracy Graph**
- **Adaptive Pruning + EWC Loss Graph**
- **Sparsity Graph**
- **Final Comparison Graph**

---

## 📈 Evaluation Metrics

The following metrics are used for evaluation:

- **Top-1 Stream Accuracy**
- **Stream Loss**
- **Experience Forgetting**
- **Model Sparsity (%)**

These metrics help measure both:

- **continual learning performance**
- **model efficiency**

---

## 📉 Key Outputs

This project generates:

- Accuracy comparison across tasks
- Loss comparison across tasks
- Sparsity growth over time
- Final comparison of:
  - **Naive**
  - **EWC**
  - **Adaptive Pruning + EWC**

