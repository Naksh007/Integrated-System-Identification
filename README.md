# Pendulum Equation Discovery and Classification

**Project objective:** Discover a governing equation for a pendulum from experimental data and apply classification models to assess system stability (Also analyzing Small-Large Angle regimes).

This repository contains:
- A consolidated Jupyter notebook that implements **Ridge** and **Elastic Net** regression to model:
  \[ \ddot{\theta} = f(\theta, \sin\theta, \dot{\theta}, \dot{\theta}^2) \]
  using features: `theta`, `sin(theta)`, `theta_dot`, `theta_dot_squared`.
- Classification models (KNN with LOOCV, Logistic Regression, SVM, and LDA) that predict a binary stability label (generated from `theta` with a clear threshold).
- A Rosenbrock function validation section to test the regression pipeline on a known nonlinear benchmark.
- Saved plots and metrics in `outputs/` (MSE, coefficients, confusion matrices, etc.).
- `requirements.txt` listing the necessary Python packages.

**Notes:**
- The notebook generates a synthetic pendulum dataset if no external dataset is provided. Replace `data/pendulum_data.csv` with your experimental CSV file (columns: `theta`, `theta_dot`, `theta_ddot`) to run on real data.
- The labeling rule for classification is adjustable (currently uses an absolute angle threshold).
- All figures are saved under `outputs/` for easy inclusion in reports or GitHub.

## How to use
1. Install dependencies:
```
pip install -r requirements.txt
```
2. Start Jupyter and open `notebooks/pendulum_analysis.ipynb`:
```
jupyter notebook notebooks/pendulum_analysis.ipynb
```
3. Run cells sequentially. The notebook is documented and saves figures to `outputs/`.

## Files
- `notebooks/pendulum_analysis.ipynb` - main combined notebook
- `data/pendulum_data.csv` - synthetic dataset (created by the notebook if not replaced)
- `outputs/` - saved plots and metrics
- `requirements.txt` - Python dependencies

## Conclusion
- Analysed physics-informed features (`sin(theta)`, `theta`, `theta_dot`, `theta_dot^2`) to govern Pendulum equation using Ridge/ElasticNet regularization.
- Implemented KNN (LOOCV), Logistic Regression, SVM, and LDA for classification (pass/fail and system stability for Small-Large Angle regimes).
- Validated network on the Rosenbrock function to demonstrate robustness of nonlinear fit (examples and MSE reported for synthetic small/large angle regimes).
