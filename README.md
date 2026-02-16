#  Handwritten Signature Generation using Vanilla GAN
## Group-1 Project Team
- Team Members:  Likitha , MD Lathif , Sruthika , Navadeep , Hari Priya , SK Sameer

---
##  Overview

This project generates synthetic handwritten signatures using a Vanilla GAN to overcome data scarcity in signature verification systems.
The system learns the distribution of real signatures and produces realistic artificial signatures for augmentation.

---

##  Project Objectives

- Learn the distribution of real handwritten signatures  
- Generate realistic synthetic signature images  
- Augment genuine datasets without manual collection  
- Improve robustness of signature verification systems  
- Provide a reusable GAN-based augmentation framework  

---
##  Training Workflow

1. Load genuine signature dataset  
2. Preprocess images (resize, normalize)  
3. Initialize Generator and Discriminator  
4. Train GAN using adversarial learning  
5. Generate synthetic signature samples  
6. Save trained generator model  

---

##  Project Folder Structure

```
Handwritten-Signature-GAN/
│
├── checkpoints/              # Saved trained models
├── data/                     # Dataset folder
│   └── cedar/
│       ├── genuine/
│       └── forgery/
│
├── samples/                  # Generated sample images
│   └── generic/
│
├── scripts/                  # Dataset preparation scripts
│   └── prepare_cedar.py
│
├── src/                      # Core source code
│   ├── api.py
│   ├── app.py
│   ├── data_loader_signatures.py
│   ├── discriminator_vanilla_gan.py
│   ├── generator_vanilla_gan.py
│   ├── vanilla_gan_model.py
│   ├── preprocess_signatures.py
│   ├── signature_pairs_dataset.py
│   ├── signature_verifier_train.py
│   ├── signature_verifier_eval.py
│   ├── train_gan_generic.py
│   ├── train_gan_user_specific.py
│   └── siamese_model.py
│
├── utils/
│   ├── metrics.py
│   └── visualizer.py
│
├── requirements.txt
├── .gitignore
└── README.md
```

---


#  Module-Wise Description

## 🔹 Module 1 — Data Pipeline & Preprocessing  
**Sruthika**

- Convert images to grayscale  
- Remove noise  
- Crop blank areas  
- Resize to fixed size (64×64 / 128×128)  
- Normalize pixel values to [-1, 1]  

---

## 🔹 Module 2 — Model Design  
**MD Lathif**

### Generator
- Input: Random noise vector  
- Fully connected layers  
- ReLU activation  
- Tanh output layer  

### Discriminator
- Binary classifier  
- LeakyReLU activation  
- Distinguishes real vs fake signatures  

**Uses:**
- Binary Cross Entropy Loss  
- Adam Optimizer  

---

## 🔹 Module 3 — Training Pipeline  
**Navadeep**

- Adversarial learning process  
- Discriminator trained first  
- Generator trained to fool Discriminator  
- Learns stroke patterns and variations  

---

## 🔹 Module 4 — Evaluation & QA  
**Hari Priya**

- Visual inspection of generated signatures  
- Detect mode collapse  
- Check stroke continuity  
- Evaluate diversity  

---

## 🔹 Module 5 — Deployment Layer  
**Balusupalli Likitha**

- Load trained Generator model  
- Generate required number of signatures  
- Display and download generated images  
- Provide practical real-world usability  

---

## 🔹 Module 6 — Monitoring & Update Pipeline  
**SK Sameer**

- Real-time loss monitoring  
- Diversity checks  
- Model version tracking  
- Adaptive tuning  

---

#  Dataset

## CEDAR Handwritten Signature Dataset  

**Kaggle Link:**  
https://www.kaggle.com/datasets/shreelakshmigp/cedardataset  

- Contains genuine and forged signatures  
- Used for GAN training and augmentation  

---

#  Technologies Used

- Python  
- PyTorch  
- OpenCV  
- NumPy  
- Vanilla GAN  

---

#  Results

- Successfully generated synthetic handwritten signatures  
- Improved dataset diversity  
- Reduced overfitting  
- Provided augmentation support for verification systems  

---

#  Conclusion

This project demonstrates how a simple Vanilla GAN can effectively generate synthetic handwritten signatures to solve real-world data scarcity problems in biometric systems.

It provides:

- A simple and explainable GAN implementation  
- A practical deployment model  
- A strong academic foundation in generative modeling  

---


---
