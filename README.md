[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Build Status](https://img.shields.io/badge/PINN-yes-green)
![Build Status](https://img.shields.io/badge/FDM-yes-blue)
![Contributions](https://img.shields.io/badge/contributions-welcome-gold)
![GitHub issues](https://img.shields.io/github/issues/DennisWayo/PINN-FDM-FracEnergyBalance)
![GitHub forks](https://img.shields.io/github/forks/DennisWayo/PINN-FDM-FracEnergyBalance)
![GitHub stars](https://img.shields.io/github/stars/DennisWayo/PINN-FDM-FracEnergyBalance)


## Physics-Informed Neural Network (PINN) for Error-Corrected Finite Difference Energy Balance in 1D Hydraulic Fracture Propagation

This repository contains the implementation of a **Physics-Informed Neural Network (PINN)-Enhanced Finite Difference Method (FDM)** for modeling **energy balance in hydraulic fracture propagation**. The proposed framework corrects numerical errors in real-time while preserving computational efficiency.

This work introduces a **1D PINN-FDM approach**, with future extensions to **2D and 3D cases**. The model integrates **energy balance equations** into the loss function, ensuring physical consistency.


### Features
- **Finite Difference Method (FDM):** Implements numerical approximations for energy balance.
- **Physics-Informed Neural Network (PINN):** Integrates physical constraints into neural network training.
- **Error Correction:** Learns numerical errors and enhances simulation accuracy.
- **Computational Efficiency:** Reduces truncation errors while maintaining computational feasibility.
- **Scalability:** The framework is designed for potential extensions to **2D and 3D fracture modeling**.


### Methodology
1. **Synthetic Data Generation:** 
   - Fracture length: L $\in$ [0.1, 10] meters
   - Fracture width:  W $\in$ [0.01, 1] meters
   - Pressure gradient: P $\in$ [1, 50] MPa/m
   - Fluid viscosity: $\mu$ $\in$ [0.001, 0.1] Pa·s

2. **Finite Difference Modeling:**
   - Central Difference Approximation (CDA)
   - Stability Constraints (CFL Conditions)

3. **PINN Model Architecture:**
   - **Input:** (L, W, P, $\mu$)
   - **5 Hidden Layers:** 512 neurons each
   - **Activation:** Swish
   - **Regularization:** Dropout (10% per layer)
   - **Loss Function:** 
     
   L = $L_{MSE}$ + $lambda_1 L_{Physics}$ + $lambda_2 L_{Weighted}$
     

4. **Training Process:**
   - Optimizer: **Adam**
   - Learning Rate: **$\alpha_0 = 0.0003 e^{-0.9t}$**
   - Convergence Tracking: **Animated training visualization**
  

### 📈 Results
- **MSE Reduction:** 264064.79 (CD) → **18.93 (PINN)**
- **Generalization Error Reduction:** **90.21%**
- **Improved Stability:** Reduced oscillations at fracture tips

![pinn_emulation](https://github.com/user-attachments/assets/7e57081e-b747-4e18-a13e-0787b3b2f80e)


### Running the Code
To train the **1D models**, execute:

```bash
python code/1D_FracEnergy.ipynb
```
For visualization and evaluation, use the **Google Colab platform**.

### Citation
If you use this work, please cite:

```
@article{your_paper_reference,
  title={Physics-Informed Neural Network (PINN) for Error-Corrected Finite Difference Energy Balance in 1D Hydraulic Fracture Propagation},
  author={xx},
  journal={xx},
  year={2025},
  doi={xx}
}
```

### Future Work
- Extension to **2D and 3D models**.
- Adaptive PINN training for complex **geomechanical applications**.

### Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request.

### Contact
For questions, reach out via email(iwayoden@gmail.com) or GitHub discussions.

