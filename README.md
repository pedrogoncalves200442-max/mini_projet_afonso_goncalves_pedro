# mini_projet_afonso_goncalves_pedro
Monte Carlo simulation and variance reduction methods for option pricing with Black&amp;Scholes and Heston models

**Author:** Pedro Afonso Gonçalves  
**Program:** M2 Probability and Finance — Sorbonne Université / École Polytechnique

## Overview

This project explores Monte Carlo methods for option pricing under the Black–Scholes model, with a focus on statistical estimation, confidence intervals, and variance reduction techniques. It also introduces the Heston stochastic volatility model and illustrates its impact on implied volatility surfaces.

The objective is to implement the main numerical methods, validate Monte Carlo estimators against analytical pricing formulas where available, and investigate the role of model parameters in option pricing.

## Project Contents

### 1. Black–Scholes Framework

- Risk-neutral dynamics of the underlying asset.
- Exact simulation of the asset price using Brownian motion.
- Analytical pricing formulas for European call and put options.
- Monte Carlo estimation of option prices.
- Asymptotic 95% confidence intervals and convergence analysis.

### 2. Monte Carlo Estimation of the Delta

Implementation of the **pathwise estimator** for the delta of a European call option.

The Monte Carlo estimate is compared with the analytical Black–Scholes delta to assess the accuracy of the numerical method.

### 3. Variance Reduction Techniques

Two variance reduction methods are implemented and compared with standard Monte Carlo simulation.

**Antithetic variates**

- Pairing Gaussian draws \(Z\) and \(-Z\).
- Using the average of the corresponding discounted payoffs.
- Studying the impact on estimator variance and confidence intervals.
- Accounting for the additional payoff evaluations when comparing computational efficiency.

**Control variates**

- Constructing a zero-mean control variate from the discounted underlying asset.
- Exploiting the put–call parity relationship.
- Deriving and implementing the optimal control coefficient.
- Comparing the resulting estimator's variance and confidence intervals with standard Monte Carlo.

The comparison focuses on statistical precision while accounting for computational cost.

### 4. Heston Stochastic Volatility Model

The project then moves beyond the constant-volatility assumption of Black–Scholes and considers the Heston model, in which instantaneous variance follows a mean-reverting stochastic process.

The implementation includes:

- Characteristic function of the log-price under Heston.
- Fourier inversion to calculate European option prices.
- Numerical integration using the trapezoidal rule.
- Implied volatility recovery through numerical root-finding.
- Construction of an implied volatility surface as a function of strike and maturity.

### 5. Sensitivity of the Implied Volatility Surface

The effects of two Heston parameters are investigated numerically:

- **Correlation \(\rho\):** its influence on the direction and magnitude of the implied volatility skew.
- **Volatility of variance \(\eta\):** its influence on the curvature of the implied volatility smile.

These experiments illustrate how stochastic volatility can generate patterns that cannot be captured by the constant-volatility Black–Scholes model.

## Methodology and Tools

The project combines probabilistic results with numerical implementation:

- Monte Carlo simulation and the central limit theorem.
- Brownian motion and risk-neutral pricing.
- Analytical benchmarks and statistical confidence intervals.
- Variance reduction and estimator efficiency.
- Fourier methods and numerical integration.
- Root-finding for implied volatility.

**Technologies:** Python, NumPy, SciPy, Matplotlib, Jupyter Notebook.

## Limitations and Potential Extensions

The Heston parameters are fixed rather than calibrated to market data. The Fourier integral is truncated at a finite upper bound, and the chosen parameters do not satisfy the Feller condition. These choices may affect numerical accuracy in some regions of the implied volatility surface.

Potential extensions include:

- Calibrating Heston parameters to market option prices.
- Simulating the Heston dynamics using suitable discretization schemes.
- Applying Monte Carlo and variance reduction methods to path-dependent options, such as Asian and barrier options.

## References

- Gilles Pagès, *Numerical Probability: An Introduction with Applications to Finance*.
- E. Abi Jaber, course notes on stochastic modelling of derivatives, M2 Probability and Finance.

---

*This project was independently developed as a personal initiative, linked to the subjects of my studies : probability, statistics, and quantitative finance.*
