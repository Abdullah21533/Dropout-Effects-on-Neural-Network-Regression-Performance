# 📘 Dropout Effects on Neural Network Regression Performance

This repository presents a clean, structured implementation of a comparative study between two feedforward neural network models — one with dropout regularization and one without — trained on synthetic regression data. The goal is to demonstrate the effect of dropout on overfitting and generalization in a regression setting.

---

## 🔍 Project Summary

While dropout is a well-known regularization technique in classification, its application in regression tasks is less explored. This project aims to evaluate how dropout impacts model performance using a small, noisy dataset.

Two models are trained and evaluated:

- 🔹 **Baseline Model**: Two fully connected layers without dropout  
- 🔸 **Dropout Model**: Same architecture with `Dropout(0.2)` after each hidden layer

---

## 🧠 Key Features

- Synthetic 1D regression dataset
- Feedforward neural network implementation using TensorFlow/Keras
- Comparison of training vs. validation MSE
- Visual analysis including:
  - 📊 Data distribution
  - 📉 Loss curves
  - 🔍 Predicted vs. true outputs

---

## 🧪 Dataset Overview

| Set     | Size | Description                          |
|---------|------|--------------------------------------|
| Train   | 20   | Synthetic X values from -1 to 1 with corresponding noisy targets |
| Test    | 20   | Independent synthetic evaluation data in same range |

---

## ⚙️ Model Architectures

### 🟦 Baseline Model (No Dropout)
- Dense(128, activation='relu')
- Dense(128, activation='relu')
- Dense(1, activation='linear')

### 🟧 Dropout Model
- Dense(128, activation='relu')
- Dropout(0.2)
- Dense(128, activation='relu')
- Dropout(0.2)
- Dense(1, activation='linear')

> Optimizer: `Adam` (learning rate = 0.01)  
> Loss Function: `Mean Squared Error (MSE)`  
> Epochs: 500

---

## 📈 Results Snapshot

| Model           | Train MSE | Test MSE | Overfitting |
|----------------|-----------|----------|-------------|
| No Dropout     | Lower     | Higher   | ⚠️ Likely   |
| With Dropout   | Slightly Higher | Lower | ✅ Reduced |

> ✅ Dropout helps improve generalization on unseen data, especially in small-data scenarios.

---

## 📊 Visualizations

- 🔴 **Data Distribution Plot**: Shows the synthetic train/test sets
- 📉 **Training vs. Validation Loss**: Over 500 epochs
- 🔍 **Model Predictions**: True values vs. predicted values for both models

---

## 🛠️ Technologies Used

- Python 3.x  
- TensorFlow / Keras  
- NumPy  
- Matplotlib  

---

## 📁 Project Structure
📦 dropout-effects-regression/
├── dropout_comparison_clean.py
├── figures/
│ ├── data_distribution.png
│ ├── prediction_comparison.png
│ └── training_loss_curves.png
├── README.md
└── .gitignore
