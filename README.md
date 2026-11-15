# Physics-Informed-Neural-Network-for-Medicine-Clearance-Pharmacokinetics-
# 💊 Medicine Clearance Predictor (Physics-Informed Neural Network)

 AI project that predicts how fast a 500 mg dose of medicine clears from the human bloodstream over 12 hours—without needing massive patient datasets.

## 🌟 What This Project Does
Normally, predicting drug levels in the body requires either complex math equations or hundreds of invasive blood tests. This project uses a **Physics-Informed Neural Network (PINN)** to combine basic machine learning with simple biological rules:

1. **The Starting Rule:** At `Hour 0`, the medicine level in the bloodstream equals the initial dose (`500 mg`).
2. **The Clearance Rule:** The liver and kidneys filter out a steady percentage of the remaining medicine every hour. The higher the drug concentration, the faster it clears.

By training a tiny neural network to obey these two rules, the AI accurately maps out the entire 12-hour recovery curve and identifies when it is safe to take a second dose.

## 🛠️ Tech Stack
* **Python 3.8+**
* **PyTorch** (for building the neural network and automatic rate-of-change tracking)
* **Matplotlib** (for plotting the medicine clearance curve)

## 🚀 How to Run the Project

### 1. Install Dependencies
Open your terminal or command prompt and run:
```bash
pip install torch matplotlib
```

### 2. Run the Script
Execute the Python file:
```bash
python medicine_pinn.py
```

### 3. View the Output
After training for ~5 seconds (2,000 steps), a graph will appear comparing:
* **Black Solid Line:** The true biological clearance curve.
* **Blue Dashed Line:** The AI's predicted clearance curve.
* **Red Dotted Line:** The safe threshold (`100 mg`) indicating when a patient can safely take their next dose (~6.5 hours).

## 🧪 Experiment Ideas
You can easily test different medical scenarios by changing two numbers at the top of `medicine_pinn.py`:
* **Simulate Slower Metabolism:** Change `CLEARANCE_RATE = 0.25` to `0.10` to see how medicine stays in the body longer for patients with slower liver/kidney function.
* **Change Dosage Strength:** Change `INITIAL_DOSE = 500.0` to `1000.0` to simulate an extra-strength dose.


