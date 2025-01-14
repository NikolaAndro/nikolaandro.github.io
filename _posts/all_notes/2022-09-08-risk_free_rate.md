---
layout: post
title:  "Risk-Free Rate"
date:   2022-09-08 09:29:20 +0700
categories: post
topic: finance
---

In this note, I will be posting things as I learn, so there will be no order. 

# Rate of Return

A rate of return (RoR) is the net gain or loss of an investment over a specified time period, expressed as a percentage of the investment’s initial cost.
When calculating the rate of return, you are determining the percentage change from the beginning of the period until the end.

The Formula for Rate of Return (RoR)
The formula to calculate the rate of return (RoR) is:

Rate of return = (Current value - Initial value) / Initial value ) x  100

This simple rate of return is sometimes called the basic [growth rate](https://www.investopedia.com/terms/a/aagr.asp),
or alternatively, [return on investment (ROI)](https://www.investopedia.com/terms/r/returnoninvestment.asp). 
If you also consider the effect of the time value of money and inflation, 
the real rate of return can also be defined as the net amount of [discounted cash flows 
(DCF)](https://www.investopedia.com/terms/d/dcf.asp) received on an investment after adjusting for inflation.

# The Risk-Free Rate

The risk-free rate of return is the theoretical rate of return of an investment with zero risk. 
The risk-free rate represents the interest an investor would expect from an absolutely risk-free 
investment over a specified period of time.


What sort of investment offers zero risk? Typically, U.S. government bonds are considered to be risk-free investments, because the federal government has never defaulted on its debt.

U.S. Treasurys are secured by the federal government, and the probability of a U.S. government default is practically zero. That’s why they are universally considered to be the safest asset that investors can own.

# The Risk-Free Rate and U.S. Treasurys

U.S. Treasury bills, commonly referred to as T-bills, offer the shortest maturity debt securities issued by the federal government. They are the closest investors can get to a zero-risk investment, for two reasons.

First, as noted above, there is a nearly universal belief that the U.S. government will always make good on its debt. Unlike corporate bonds or municipal bonds, T-bills are backed by the full faith and credit of the U.S. government, which has never defaulted.

Secondly, the market for U.S. government debt is the largest and most liquid market anywhere on earth. As of April 2022, SIMFA reports that the market cap for U.S. Treasury-issued securities was $23.3 trillion, with $679 billion being actively traded.

That’s a hefty market, considering it’s almost two-thirds the market capitalization of the S&P 500, which was $38.29 trillion in March 2022. Thanks to the enormous size and trading volume of the treasuries market, investors know there will always be buyers for their T-bills when they need cash.

The yield on a three-month T-bill is regularly quoted as the day’s risk-free rate for U.S investors.

# Nominal Risk-Free Rate vs. Real Risk-Free Rate

There are two ways to talk about the risk-free rate: the nominal risk-free rate and the real risk-free rate. The difference is due to the impact of inflation.

The nominal risk-free rate is typically the current yield of the 3-month T-bill without taking into account the impact of inflation. The real risk-free rate is the yield of the 3-month T-bill minus the impact of inflation.

The real risk-free rate is the yield an investor would need on a prospective investment not to experience inflation risk, providing inflation rates stay the same or decrease.


# How To Calculate The Risk-Free Rate

The formula for the risk-free rate is simple: It’s just the current yield of the three-month T-bill. However, the formula to calculate the real risk-free rate has a few more steps.

First, here’s the formula:

      Real Risk-Free Rate = Risk-Free Rate – Inflation Premium

Say you’d like to invest in a 12-month certificate of deposit (CD) that yields 2.50%. If the current risk-free rate is 2.04%—the yield of a 12-month T-bill—you’re coming out almost half a percentage point ahead of the T-bill with the CD. Great work! Or is it?

Let’s suppose the inflation rate is the same as it was in May 2022: 8.3%. Now, do the math again.

      Real Risk-Free Rate = 2.04% – 8.3%

So the real risk-free rate is -6.26%. By investing in the CD, you’d be falling 6.26% short of keeping pace with current inflation rates.

If your goal is to grow your money and retain purchasing power, you’ll probably want to look for a different investment with higher yields. In an inflationary economy, that typically means a riskier investment.


# The Bottom Line

While the risk-free rate is ultimately a theoretical concept, the ability to calculate and understand the real risk-free rate is helpful for several reasons.

First, you can evaluate whether an investment will help preserve your purchasing power in an inflationary economy. Next, you can evaluate investments of different durations to see if a particular duration will offer you returns that help keep pace with or outpace inflation for the investment term.

It’s never a bad idea to run the numbers to see if a particular low-risk investment makes sense in the current economy. You now have a tool to do just that, and it only takes moments to figure out your risk-free rate of return.


# Risk-Free Rate in Options

The effect of the rfr on option prices is not as clear-cut as one would expect. As the economy expands, rates tend to increase, but so does the expected rate of share price increases, because dividends increase. It is also known that the present value of future cash flows also decreases as rates increase.

These two effects tend to reduce the prices of put options, i.e. the value of put options decreases as the rfr increases. However, it has been shown that the value of call options increase as the rfr increases, as the former effect tends to dominate the latter effect.

Risk-free rates are further used in Black-Scholes option pricing model as well as in Binomial-option pricing model.

