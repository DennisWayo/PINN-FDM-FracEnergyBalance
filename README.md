# PINN-FDM-EnergyBalance
# 📌 1D Physics-Informed Neural Network (PINN) for Error-Corrected Finite Difference Energy Balance in Hydraulic Fracture Propagation

## 📝 Overview
This repository contains the implementation of a **Physics-Informed Neural Network (PINN)-Enhanced Finite Difference Method (FDM)** for modeling **energy balance in hydraulic fracture propagation**. The proposed framework corrects numerical errors in real-time while preserving computational efficiency.

This work introduces a **1D PINN-FDM approach**, with future extensions to **2D and 3D cases**. The model integrates **energy balance equations** into the loss function, ensuring physical consistency.


---

## 🚀 Features
- **Finite Difference Method (FDM):** Implements numerical approximations for energy balance.
- **Physics-Informed Neural Network (PINN):** Integrates physical constraints into neural network training.
- **Error Correction:** Learns numerical errors and enhances simulation accuracy.
- **Computational Efficiency:** Reduces truncation errors while maintaining computational feasibility.
- **Scalability:** The framework is designed for potential extensions to **2D and 3D fracture modeling**.

---

## 📊 Methodology
1. **Synthetic Data Generation:** 
   - Fracture length: \( L \in [0.1, 10] \) meters
   - Fracture width: \( W \in [0.01, 1] \) meters
   - Pressure gradient: \( P \in [1, 50] \) MPa/m
   - Fluid viscosity: \( \mu \in [0.001, 0.1] \) Pa·s

2. **Finite Difference Modeling:**
   - Central Difference Approximation (CDA)
   - Stability Constraints (CFL Conditions)

3. **PINN Model Architecture:**
   - **Input:** \( (L, W, P, \mu) \)
   - **5 Hidden Layers:** 512 neurons each
   - **Activation:** Swish
   - **Regularization:** Dropout (10% per layer)
   - **Loss Function:** 
     \[
     \mathcal{L} = \mathcal{L}_{MSE} + \lambda_1 \mathcal{L}_{Physics} + \lambda_2 \mathcal{L}_{Weighted}
     \]

4. **Training Process:**
   - Optimizer: **Adam**
   - Learning Rate: **\( \alpha_0 = 0.0003 e^{-0.9t} \)**
   - Convergence Tracking: **Animated training visualization**
  
---

## 📈 Results
- **MSE Reduction:** \( 264064.79 \) (CD) → **\( 18.93 \) (PINN)**
- **Generalization Error Reduction:** **90.21%**
- **Improved Stability:** Reduced oscillations at fracture tips

### 🔍 Figures
| Visualization | Description |
|--------------|------------|
| **Comparison Plot** | PINN vs. Central Difference vs. True Energy Balance |
| **Training Loss Plot** | Convergence of PINN Loss Function |
| **3D Surface Plot** | PINN Predictions Over Fracture Length and Epochs |
| **Contour Map** | PINN Learning Progress Visualization |
| **Error Distribution** | Numerical Error Reduction Analysis |

---

## 🔧 Installation
### **Dependencies**
To run the project, install dependencies using:
```bash
pip install -r requirements.txt


