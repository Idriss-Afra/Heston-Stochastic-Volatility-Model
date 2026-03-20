# Heston Stochastic Volatility Model

A quantitative finance repository focused on implementing the **Heston stochastic volatility model** for equity derivatives.

This project develops the **Heston (1993) framework**, calibrates its parameters to market option prices, and applies the model to the pricing of **equity variance** and **volatility swaps**.

---

## Repository Structure

```text
Heston-Stochastic-Volatility-Model/
├── Heston Stochastic Volatility Model.ipynb
```

---

## Project Overview

This notebook focuses on the **Heston stochastic volatility model** for equity derivatives.

It starts from the standard **risk-neutral dynamics** of the Heston model, where the underlying price follows a diffusion with **stochastic variance** governed by a mean-reverting square-root process. On this basis, the notebook derives the **semi-analytical pricing formula** for European vanilla options through the model’s **characteristic function** and a **Fourier inversion approach**.

The model is then calibrated to market option prices by optimizing the five Heston parameters — **κ**, **θ**, **V₀**, **ρ**, and **σ** — through a weighted pricing-error objective. The calibration procedure relies on **SciPy’s differential evolution** algorithm, includes a **Feller constraint** to promote strictly positive variance dynamics, and uses several runtime controls to improve numerical efficiency and robustness.

Once calibrated, the framework is applied to the pricing of **equity variance swaps** and **equity volatility swaps**.

---

## Example Output

**CAC40 10-Month Listed Options**:

<img width="500" height="600" alt="image" src="https://github.com/user-attachments/assets/b40a087f-7a65-431a-a8b3-728f190517e7" />


---

## Best use case

Use this notebook when working with **equity option market data** and calibrating the **Heston model** to **vanilla option prices**, as well as pricing **equity variance swaps** and **equity volatility swaps**.

---

## How to Use

Clone the repository:

```bash
git clone https://github.com/Idriss-Afra/Heston-Stochastic-Volatility-Model.git
cd Heston-Stochastic-Volatility-Model
jupyter notebook
```

Then open:

* `Heston Stochastic Volatility Model.ipynb`

---

## Author

**Idriss Afra**
