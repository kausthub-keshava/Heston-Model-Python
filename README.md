# Heston-Model-Python
Simulating the Heston option pricing model on python.
The Heston model has five independent parameters. The underlying asset price follows a standard lognormal process, and the variance V follows a mean-reverting square root process:

$$dS = rSdt + \sqrt{V}SdW_1 $$
$$dV = -\kappa(V0 - V_{\infty})dt + \omega\sqrt{V}dW_2  $$

where

dW1 is the risk-free interest rate, we have ignored dividends &
dW2 and  are two (correlated) standard Brownian motions.
The five Heston model parameters are:
the initial variance V0
the long-term variance $V_{\infty}$
the speed of mean reversion $\kappa$
the volatility of volatility $\omega$
and the correlation $\rho$
