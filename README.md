# 🏙️ Predicting Slum Areas using Deep Learning Techniques  

This repository contains the implementation of my **Bachelor Thesis Project (BTP)**:  
**“Predicting Slum Area using Deep Learning Techniques”** conducted at the **Center of Excellence in Artificial Intelligence, IIT Kharagpur**.

---

## 📌 Project Overview  

Urbanization has led to the proliferation of informal settlements (slums), posing challenges for **urban planning** and **policy-making**. This project leverages **satellite remote sensing imagery** combined with **deep learning techniques** to automatically detect and segment slum areas.  

We focus on using **U-Net variants**, **HRNet**, and **Attention U-Net** architectures for **semantic segmentation** of high-resolution satellite images.  

---

## 🚀 Features  
- Data collected from **Google Earth Pro** (12 slum regions in Mumbai).  
- Manual annotation performed using **MakeSense.AI**, exported in **COCO JSON format**.  
- Implemented and compared:  
  - U-Net from scratch  
  - U-Net with ResNet50 Encoder (transfer learning from ImageNet)  
  - Attention U-Net  
  - HRNet (High-Resolution Network)  
- Evaluated multiple **loss functions** (Focal Loss, BCE, MSE, Hinge Loss) and optimizers (Adam, RMSProp, SGD).  
- Achieved **F1 Score ≈ 78%** and **Accuracy ≈ 93%**, outperforming prior baselines.  

---

## 📂 Dataset  

- **Source:** Google Earth Pro (12 slum areas in Mumbai: Dharavi, Bandra, Andheri, Kurla, etc.).  
- **Annotations:** Created with **MakeSense.AI** → COCO JSON format.  
- **Masks:** Generated via **PyCOCO API** and **OpenCV**.  
- **Format:**  
  - `images/` – Satellite images  
  - `masks/` – Corresponding binary masks (slum = 1, non-slum = 0)  

---

## 🏗️ Methodology  

1. **Data Collection & Preprocessing**  
   - High-resolution (1920×1080) satellite imagery  
   - Manual annotations → COCO JSON → mask generation  

2. **Model Architectures**  
   - **U-Net (baseline)**  
   - **U-Net + ResNet50 encoder** (transfer learning)  
   - **Attention U-Net** (attention gates for feature refinement)  
   - **HRNet** (maintains high-resolution features for segmentation)  

3. **Training**  
   - Input size: 256×256  
   - Batch size: 16  
   - Epochs: 15  
   - Optimizer: Adam  
   - Loss: Focal Loss  

4. **Evaluation Metrics**  
   - Accuracy  
   - Precision, Recall, F1-score  
   - IoU (Intersection over Union)  

---

## 📊 Results  

| Model                  | F1 Score | IoU   | Accuracy |
|-------------------------|----------|-------|----------|
| U-Net (scratch)         | 0.74     | 0.62  | 85%      |
| U-Net + ResNet50        | **0.79** | 0.67  | **93%**  |
| Attention U-Net         | 0.77     | 0.65  | 92%      |
| HRNet                   | 0.75     | 0.63  | 91%      |

✅ **Best model:** U-Net with ResNet50 encoder + Adam optimizer + Focal Loss  

---

## 🛠️ Tech Stack  

- **Languages:** Python  
- **Libraries:** TensorFlow, Keras, PyTorch, OpenCV, NumPy, Pandas  
- **Tools:** Google Earth Pro, MakeSense.AI, PyCOCO API, Jupyter Notebook  

---
