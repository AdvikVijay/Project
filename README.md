# ML-Assisted Voltage Ride-Through System for Industrial VSDs

A simulation-based machine learning project to enhance the stability and resilience of Variable Speed Drives (VSDs) in industrial grids using predictive control and intelligent compensation.

## 🛠 Project Overview

Voltage sags and swells in industrial power systems can disrupt the performance of Variable Speed Drives (VSDs). This project integrates power electronics simulation with machine learning to develop an intelligent Voltage Ride-Through (VRT) device that dynamically compensates voltage variations.

### 🔧 Technologies Used

- **Simulation:** MATLAB/Simulink (VRT system modeling)
- **Machine Learning:** Python, scikit-learn, pandas, matplotlib
- **Control Logic:** PID controller, Adaptive ML-based tuning
- **Version Control & Docs:** Git, Jupyter Notebook, LaTeX

---

## 📈 Objectives

- Simulate a complete VRT system using a SEPIC converter and three-phase inverter for voltage compensation.
- Collect time-series data from simulations (voltage, torque, current, etc.).
- Train regression models to predict optimal compensation voltage values.
- Deploy ML-assisted PID tuning to stabilize DC link voltage under varying grid conditions.
- Visualize performance metrics and validate model accuracy.

---

## 🧠 Machine Learning Implementation

- **Input Features:** Phase voltages (Va, Vb, Vc), rectifier outputs, previous compensation voltages
- **Target:** Optimal compensation voltage to maintain DC link at 378V
- **Models Tested:** Linear Regression, Support Vector Regression (SVR), Random Forest Regressor
- **Performance Metrics:** RMSE, R² Score, Compensation Accuracy

---

## 🔬 Simulation Architecture
3-Phase Grid Input
        ↓
Diode Bridge Rectifier
        ↓
SEPIC Converter ← PID (ML-tuned)
        ↓
DC Link Capacitor
        ↓
3-Phase PWM Inverter
        ↓
3-Phase Induction Motor
---

## 📊 Results

- **Voltage Regulation:** Maintained DC link within ±2% of 378V under up to 25% grid fluctuation
- **PID Tuning:** Reduced response time and overshoot compared to manually tuned controller
- **Model Accuracy:** SVR achieved R² score of 0.93 in predicting optimal compensation voltages
- **Visualizations:** Real-time plots of rotor speed, torque, and voltage behavior under faults

---

## 🚀 How to Run

1. Clone the repository
2. Open and simulate the `VRT_model.slx` in MATLAB/Simulink
3. Run `data_extraction.py` to generate datasets from simulation outputs
4. Train models using `ml_model_training.ipynb`
5. View results and visualizations in the notebook

---

## 📁 Repository Structure
├── Simulink/
│   └── VRT_model.slx
├── data/
│   └── simulation_outputs.csv
├── scripts/
│   ├── data_extraction.py
│   ├── ml_model_training.ipynb
│   └── pid_optimizer.py
├── results/
│   └── visualizations/
├── README.md
└── report/
└── final_thesis.pdf
---

## 🤖 Future Scope

- Integration with **Reinforcement Learning** for dynamic gain adjustment
- Real-time control on **microcontroller (ESP32/RPi)** with ML model deployment
- Expansion to **renewable power sources (PV/Fuel Cell)** for smart grid integration

---

## 📜 License

This project is licensed under the MIT License. See `LICENSE` for more details.
