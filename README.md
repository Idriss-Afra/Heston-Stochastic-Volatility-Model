# Heston Stochastic Volatility Model

A quantitative finance repository focused on implementing the **Heston stochastic volatility model** for equity derivatives.

This project develops the **Heston (1993) framework**, calibrates its parameters to the market implied volatility surface, and applies the model to the pricing of **equity variance** and **volatility swaps**.

---

## Repository Structure

```text
Heston-Stochastic-Volatility-Model/
├── Heston Stochastic Volatility Model.ipynb
├── MarketData/
│   ├── CAC40_MarketData_12022025.csv
│   └── EURIBOR6M_ZCRates_12022025.csv
```

---

## Project Overview

This notebook focuses on the **Heston stochastic volatility model** for equity derivatives.

It starts from the standard **risk-neutral dynamics** of the Heston model, where the underlying price follows a diffusion with **stochastic variance** governed by a mean-reverting square-root process. On this basis, the notebook derives the **semi-analytical pricing formula** for European vanilla options through the model’s **characteristic function** and a **Fourier inversion approach**.

The model is then calibrated to the **market implied volatility surface** by optimizing the five Heston parameters — **κ**, **θ**, **V₀**, **ρ**, and **σ**. The objective is written in **implied volatility** rather than in price, so that every quote contributes on a comparable scale across maturities and strikes. The calibration relies on **SciPy’s least squares** with its **Trust Region Reflective** algorithm, run from several starting points covering the usual equity regimes, and handles the **Feller condition** through a reparameterisation that turns it into a simple box bound rather than a non-linear constraint.

On the **CAC40 index options volatility** surface of **12 February 2025**, we use **66 quotes across six listed expiries** from **one month to thirteen months**. The calibration reaches an implied volatility **RMSE of 13.2 basis points**, with per-expiry errors ranging from **7.4** to **21.6 basis points**.

Once calibrated, the framework is applied to the pricing of **equity variance swaps** and **equity volatility swaps**, producing a full **term structure** of fair strikes and of the **volatility convexity adjustment** across the calibrated expiries.

---

## Market Data

The `MarketData/` folder includes the market inputs required for the calibration and pricing workflow.

- `CAC40_MarketData_12022025.csv` — market option data, with the implied forwards and implied volatilities computed in the companion [Equity Implied Forward & Volatility Surface](https://github.com/Idriss-Afra/Equity-Implied-Volatility-Surface) repository
- `EURIBOR6M_ZCRates_12022025.csv` — zero-coupon rates used for discounting and forward-related calculations

Users can replace the sample input files with their own market data, provided that the CSV files keep the same structure as the ones included in `MarketData/`.  
To run the notebook correctly, the current column layout and overall file format must be respected.

---

## Example Output

**CAC40 Heston Calibrated Smiles**:

<img width="1542" height="593" alt="image" src="https://github.com/user-attachments/assets/1dfd9d4c-9e18-49c5-a58f-6bd2e8879462" />

**CAC40 Heston Fair Strikes**:

<img width="600" height="350" alt="image" src="https://github.com/user-attachments/assets/1f2b7114-bbe6-4ff7-890f-5f1966b00a73" />

---

## Best use case

Use this notebook when working with **equity option market data** and calibrating the **Heston model** to an **implied volatility surface**, as well as pricing **equity variance swaps** and **equity volatility swaps**.

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
