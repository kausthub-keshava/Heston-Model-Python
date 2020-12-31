# Heston-Model-Python
The Black-Scholes model of option pricing has some well-known deficiencies, the most important of which is the assumption that the volatility of the return on the underlying asset is constant. In reality, the implied volatilities of traded options generally vary, both with strike price and with maturity of the option. The variation with strike price is called the volatility smile, or the volatility skew.

The constant volatility of the Black-Scholes model corresponds to the assumption that the underlying asset follows a lognormal stochastic process. On the other hand, the basic assumption of stochastic volatility models is that the volatility (or possibly, the variance) of the underlying asset is itself a random variable. There are two Brownian motions: one for the underlying, and one for the variance; stochastic volatility models are thus two-factor models. Of course, the two processes are correlated and, at least in the equity world, the correlation is usually taken to be negative: increases/decreases in the asset price tend to be coupled to decreases/increases in the volatility.

Once the variance of the underlying has been made stochastic, closed-form solutions for European call and put options will in general no longer exist. One of the attractive features of the Heston model, however, is that (quasi-) closed-form solutions do exist for European plain vanilla options. This feature, in turn, makes calibration of the model feasible.

The implied volatility of such a European option is then the value of the volatility which would have to be used in the Black-Scholes formula, to get that specific price. By varying the strike price and maturity, one can thus back out the implied volatility surface for the specific set of Heston model parameters under consideration. One finds that the Heston model gives rise to a wide variety of implied volatility surfaces, many of which capture market-observed behavior very well.

The Heston model has five independent parameters. The underlying asset price follows a standard lognormal process, and the variance V follows a mean-reverting square root process:

![equation](https://latex.codecogs.com/gif.latex?dS%20%3D%20rSdt%20&plus;%20%5Csqrt%7BV%7DSdW_1)

![equation](https://latex.codecogs.com/gif.latex?dV%20%3D%20-%5Ckappa%28V0%20-%20V_%7B%5Cinfty%7D%29dt%20&plus;%20%5Comega%5Csqrt%7BV%7DdW_2)

where

![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20dW_1) is the risk-free interest rate, we have ignored dividends &

![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20dW_2) and  are two (correlated) standard Brownian motions.

The five Heston model parameters are:
- the initial variance ![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20V0)
- the long-term variance ![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20V_%7B%5Cinfty%7D)
- the speed of mean reversion ![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20%5Ckappa)
- the volatility of volatility ![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20%5Comega)
- and the correlation ![equation](https://latex.codecogs.com/gif.latex?%5Cinline%20%5Crho). 

We will also require that ![equation](https://latex.codecogs.com/gif.latex?%5Cinline%202%5Ckappa%20%5Ctheta%20%3E%20%5Csigma%5E2) (Feller condition).

The Heston differential equations can be solved by a Monte carlo simulation, or by a Fourier series expansion. 

The Heston model parameters can be determined by calibrating to a market observed implied volatility smile for European options. The calibration routine takes as its starting point the implied volatilities for a set of such options, with varying strikes and/or maturities. The volatilities are converted to option prices, and the parameters of the Heston model are chosen so as to best match this set of market data.

In this project, we use a pre-calibrated Heston model to save ourself from the task of scraping market data!
