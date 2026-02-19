
# Black-Scholes Visual Explainer
<img width="2968" height="1621" alt="Screenshot 2026-02-12 201557" src="https://github.com/user-attachments/assets/fa1dbf50-9bb3-4b78-9df6-2373ba9f27e7" />

<img width="2987" height="1670" alt="Screenshot 2026-02-12 201604" src="https://github.com/user-attachments/assets/79c37454-ca0b-4602-8ed9-9a3faf2ef24b" />

## Developer: Anurag Pratap Singh


An interactive visualization tool for the Black-Scholes option pricing model, built using Streamlit and Plotly. This project demonstrates option pricing, sensitivity analysis (Greeks), and 3D surface visualization.

## Features

- **Black-Scholes formula** for European Call and Put options
- **Greeks**: Delta, Gamma, Vega, Theta, Rho
- **Interactive sliders** for:
  - Stock price (S)
  - Strike price (K)
  - Volatility (σ)
  - Time to maturity (T)
  - Risk-free rate (r)
- **Real-time updating** of option price and Greeks
- **3D surface plot**: Stock Price vs Volatility vs Option Price
- **2D plot**: Delta vs Stock Price
- **Smooth animated transitions**
- **Professional dark theme** with sidebar controls, large price display, and colored Greek indicators

## Mathematical Formulas

Let $S$ = Stock price, $K$ = Strike price, $T$ = Time to maturity, $r$ = Risk-free rate, $\sigma$ = Volatility.

- $d_1 = \frac{\ln(S/K) + (r + 0.5\sigma^2)T}{\sigma\sqrt{T}}$
- $d_2 = d_1 - \sigma\sqrt{T}$

**Call Price:**
$$C = S N(d_1) - K e^{-rT} N(d_2)$$

**Put Price:**
$$P = K e^{-rT} N(-d_2) - S N(-d_1)$$

Where $N(x)$ is the cumulative distribution function of the standard normal distribution.

### Greeks

- **Delta:** $\frac{\partial C}{\partial S} = N(d_1)$ (Call), $N(d_1)-1$ (Put)
- **Gamma:** $\frac{\partial^2 C}{\partial S^2} = \frac{N'(d_1)}{S\sigma\sqrt{T}}$
- **Vega:** $\frac{\partial C}{\partial \sigma} = S N'(d_1) \sqrt{T}$
- **Theta:** $\frac{\partial C}{\partial T}$ (see code for full formula)
- **Rho:** $\frac{\partial C}{\partial r}$ (see code for full formula)

## Usage

1. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```
2. Run the app:
   ```bash
   streamlit run app.py
   ```

## File Structure
- `app.py` — Streamlit app UI and visualization
- `black_scholes.py` — Pricing and Greeks functions
- `requirements.txt` — Dependencies
- `README.md` — This file

## What I Learned

- Black-Scholes mathematical formulation
- Option Greeks and sensitivity analysis
- Financial derivatives pricing
- Interactive visualization using Streamlit & Plotly


---


**Enjoy exploring the Black-Scholes model interactively!**

---

## 🚀 Future Improvements

- **Monte Carlo Simulation Comparison**  
  Implement a Monte Carlo-based option pricing model to compare results with the analytical Black-Scholes formula and analyze pricing differences under stochastic simulations.

- **Implied Volatility Calculator**  
  Add a numerical solver (e.g., Newton-Raphson method) to compute implied volatility from market option prices.

- **Theoretical vs Market Price Comparison**  
  Integrate real market option data and compare theoretical Black-Scholes prices with actual market prices to analyze mispricing opportunities.

- **Dividend Yield Parameter (q)**  
  Extend the Black-Scholes model to include continuous dividend yield and adjust pricing formulas accordingly.

---

**Made by Anurag**
