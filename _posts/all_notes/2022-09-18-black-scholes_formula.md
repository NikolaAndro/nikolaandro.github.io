---
layout: post
title:  "Black-Scholes Formula"
date:   2022-09-18 09:29:20 +0700
categories: post
topic: finance
---

# Black-Scholes Formula

This formula is representing a options trading framework used to evaluate options. 

The parameters that we care about when trying to vealuate the price of the stock option are:

- $S_0$ - stock price
- $X$ - exercise price 
- $r$ - risk-free rate
- $T$ - time to expiration (maturity)
- $\sigma$ - standard deviation of log returns (volatility)


Let us use $Call_{european}$ for **present value** of European call option contract and $Put_{european}$ for **present value** of European put option contract.

 $Call_{european} = S_0 \cdot N(d_1) - X \cdot e^{-rT} \cdot X \cdot N(d_2)$
 
 $Put_{european} =  - e^{-rT} \cdot X \cdot N(-d_2) - S_0 \cdot N(-d_1)$
 
 where,
 
 $d_1 = \frac{ln(\frac{S_0}{X}) + (r + \frac{\sigma^2}{2}) \cdot T}{\sigma \cdot \sqrt{T}}$
 
 $d_2 = \frac{ln(\frac{S_0}{X}) + (r - \frac{\sigma^2}{2}) \cdot T}{\sigma \cdot \sqrt{T}}$

$N(x)$ - Standard normal distribution - probability that a random variable variable is less or equal to x. It will give a value in range (0,1).

# European Call Option

A European call option gives the owner the right to acquire the underlying security at expiry. For an investor to profit from a call option,
the stock's price, at expiry, has to be trading high enough above the strike price to cover the cost of the option [premium](https://www.investopedia.com/terms/o/option-premium.asp).

European call option can only be exercised one time and that is on the day of expiration.

$Call_{european} = S_0 \cdot N(d_1) - X \cdot e^{-rT} \cdot X \cdot N(d_2)$  --> $Call_{european} = WhatYouGet - WhatYouPay$

$S_0 \cdot N(d_1)$   -> What you get

$X \cdot e^{-rT} \cdot X \cdot N(d_2)$ --> What you pay

$X \cdot e^{-rT}$ -> exercise price dsicounted back to today (present value of the exercise price)



The higher volatility $\sigma$ then $d_1$ will go up and $d_2$, so the value of $S_0 \cdot N(d_1)$ will go up and the value of $S_0 \cdot N(d_1)$ will go down.

Hence,the value of the European call option will go up as the volatility goes up and vice versa.




