# Learning Phase Transitions in the 2D Ising Model Using Machine Learning

This project simulates the 2D Ising model using the Metropolis Monte Carlo algorithm and applies machine learning (both unsupervised and supervised) to detect and learn phase transitions in statistical physics systems.

## Project Structure

ising_phase_transition_ml/
├── data/                        # Contains generated spin configurations (.npy)
├── simulation/
│   ├── init.py              # Makes simulation/ a Python module
│   └── ising_metropolis.py      # Monte Carlo simulation of 2D Ising model
├── ml_models/
│   ├── unsupervised.py          # PCA, t-SNE, k-Means clustering
│   └── supervised.py            # CNN-based temperature classifier
├── visualizations/
│   └── analysis.ipynb           # Visualize dimensionality reduction
├── main.py                      # Runs simulation and unsupervised ML
└── README.md                    # Project overview



## Dataset

- The dataset is generated dynamically by running `main.py`.
- Files are saved as `.npy` arrays of shape `(N, N)` where each value is either `+1` or `-1` (spin).
- File naming format: `T{temperature}_step{step}.npy`, e.g., `T2.30_step12.npy`

---

## Dependencies

Install all required packages with:

```bash
pip install numpy matplotlib scikit-learn torch



⸻

🚀 How to Run

🔹 Step 1: Generate Spin Data

From the project root directory:

python main.py

This will:
	•	Run Monte Carlo simulations at various temperatures
	•	Save spin configurations in data/
	•	Run unsupervised PCA + t-SNE + k-Means clustering

🔹 Step 2: Visualize Results

Open the notebook:

jupyter notebook visualizations/analysis.ipynb

This shows:
	•	PCA and t-SNE plots of phase-separated configurations
	•	Color-coded by temperature

🔹 Step 3: (Optional) Train Supervised Classifier

python -m ml_models.supervised

This will:
	•	Train a CNN to classify configurations based on temperature
	•	Use torch and cross-entropy loss on synthetic labels

⸻

Techniques Used

Physics Side:
	•	2D Ising Model (L x L lattice)
	•	Metropolis-Hastings Monte Carlo
	•	Statistical mechanics concepts like magnetization, energy

ML Side:
	•	Unsupervised: PCA, t-SNE, k-Means clustering
	•	Supervised: Convolutional Neural Network (CNN)
	•	Dimensionality Reduction and Clustering to detect phase transition around critical temperature (~2.27)

⸻

 Notes
	•	Make sure all .py folders have an __init__.py file so they’re recognized as modules.
	•	If you encounter a path error, verify that you are running main.py from the root of the project.
	•	The critical behavior of the Ising model is best captured near T ≈ 2.27 (in units of J/kB).

⸻

Author
Atharv Maleyvar