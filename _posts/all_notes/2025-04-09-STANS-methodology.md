---
layout: post
title:  "STANS Margin Methodology"
date:   2025-04-09 09:29:20 +0700
categories: post
topic: finance
---

# STANS - System for Theoretical Analysis and Numerical Simulations

OCC's STANS margine methodology evaluates overall portfolio risk by calculating Estimated Shortfall under 10,000 price and volatility shocks for all cleared products and collateral in a portfolio, with various addp-on charges for additional factors such as concentration and liquidity risk. The STANS scenarios are calculated by hte OCC using a Monte Carlo simulation and they include a showck to the underlying price and set of 9 pivot points representing volatility shocks based on expiry and option delta. Once the shocked prices are calculated under each scenario, the results are aggregated using historical, perfect and zero correlations and the Estimated Shortfall calculated. Once the risk is calculated using these results, a number of add-on charges are also calculated to capture concentration, dependency and vega risk.

> **OCC is the first derivatives clearinghouse in the world to use a large-scale Monte Carlo-based risk management methodology.**  

The STANS methodology is used to measure the exposure of portfolios of options, futures and cash instruments cleared and carried by OCC on behalf of its <span style="color: purple;">***clearing member firms ("CMs")***</span>. STANS allows clearing institutions to measure, monitor and manage the level of risk exposure of their members' portfolios.

### Who Are Clearing Members (CMs)?

CMs are entities that have been approved by the OCC (or another relevant clearing organization) to clear and settle trades on behalf of their own clients. This approval is based on strict financial and operational criteria, as well as a commitment to meet margin and risk management requirements.

When clients execute trades, they typically do so through a brokerage or another financial institution. These firms, acting as CMs, then present these trades to the OCC for clearing and settlement. By doing so, they effectively stand between the end clients and the clearinghouse, which helps distribute and mitigate risk across the financial system.

## General Features

[OCC STANS Documentation Link](https://www.theocc.com/risk-management/margin-methodology)

OCC applies margin requirements on a daily basis to each account maintained at OCC by its CMs. Intraday calls for additional margin may be made on accounts incurring significant losses.

Under the STANS methodology, which went into effect in August 2006, the daily margin calculation for each account is based on <span style="color: purple;">***full portfolio Monte Carlo simulations***</span> and - as set out in more detail below - is constructed conservatively to ensure a very high level of assurance that the overall value of cleared products in the account, plus collateral posted to meet margin requirements, will not be appreciably negative at a two-day horizon.

Until February 2010, securities posted as collateral were not included in the Monte Carlo simulations, but were subjected to traditional "haircuts." Since then, the <span style="color: purple;">***"collateral in margins" scheme***</span> has taken effect, whereby some collateral securities - specifically equity securities - have ***instead been included in the Monte Carlo simulations***. Thus, the margin calculations now reflect the scope for price movements in these forms of collateral to exacerbate or mitigate losses on the cleared products on the account.

The <span style="color: purple;">***Monte Carlo simulations***</span> are based on econometric models of the joint behavior of the risk factors affecting values of CM accounts at OCC. ***The majority of risk factors pertain to the prices and option-implied volatilities of individual equity securities***. The modeling of each risk factor allows for volatility clustering and fat-tailed innovations. The joint behavior is addressed by combining the marginal behaviors of individual risk factors by means of a copula function that takes account of correlations and allows for tail-dependence.

The Monte Carlo simulations use, for the volatility of each risk factor, the greater of the short-term level predicted by the model and an estimate of its longer-run level.

***The base component of the margin requirement for each account is obtained from the risk measure known as <span style="color: purple;">99% Expected Shortfall.</span>*** That is to say, the account has a base margin excess (deficit) if its positions in cleared products, plus all existing collateral - whether of types included in the Monte Carlo simulation or of types subjected to traditional "haircuts" - would have a positive (negative) net worth after incurring a loss equal to the average of all losses beyond the 99% VaR point.

> The term "VaR point" refers to the specific loss threshold defined by the Value at Risk (VaR) measure at a chosen confidence level—in this case, 99%. 

>VaR is a statistical risk measure that estimates the maximum expected loss a portfolio could suffer over a given time horizon, at a certain confidence level. For example, a 99% VaR indicates that, under normal market conditions, the portfolio is not expected to lose more than the VaR amount on 99% of trading days (or over the chosen period).

>The VaR point is the specific loss amount at the 99% confidence level. It defines a threshold such that there is only a 1% chance that the loss will exceed this value. In other words, if you arranged all possible loss outcomes from the worst to the best, the VaR point is the cutoff below which the worst 1% of losses lie.

The base component is ***adjusted by the addition of a stress test component***. The stress test component is obtained from consideration of the increases in <span style="color: purple;">***Expected Shortfall***</span> that would arise from market movements that are especially large and/or in which various kinds of risk factor exhibit perfect or zero correlations in place of their correlations estimated from historical data, or from extreme adverse idiosyncratic movements in individual risk factors to which the account is particularly exposed.

> <span style="color: purple;">***Expected Shortfall (also known as Conditional Value at Risk, or CVaR)***</span> is a risk measure used in finance to assess the potential losses of a portfolio under extreme market conditions. Instead of just looking at a threshold loss level (as in Value at Risk, or VaR), Expected Shortfall provides the average loss that occurs in the worst-case scenarios—specifically, in the tail of the loss distribution beyond a certain confidence level (for example, beyond the 99% VaR).
>> How It Works:\
Imagine you take all possible outcomes of a portfolio’s returns and focus on the worst 1% (if using 99% VaR as the cutoff). The VaR point tells you the loss threshold below which these worst-case outcomes occur. Expected Shortfall then calculates the average of these extreme losses. This offers a more complete picture of tail risk because it takes into account not just the cutoff value, but the severity of losses beyond that threshold./ 

>> Why It Matters: \
By using Expected Shortfall, risk managers get a better understanding of the “tail risk” – the expected losses when the market behaves worse than the typical scenarios captured by VaR. This helps institutions prepare for rare but potentially catastrophic events.

> <span style="color: purple;">***Purpose of the Stress Test Component***</span>\
The stress test component is designed to adjust the base margin requirement upward to account for extreme market scenarios that historical data might not fully capture. Even if a portfolio appears well-protected under typical conditions (as measured by the base Expected Shortfall), there might be events with extraordinary market movements that could significantly increase losses.

>> <span style="color: purple;">***How the Stress Test is Applied:***</span>

>>>Consideration of Large Market Movements:
The method examines what would happen if market movements were much larger than those observed in historical data. This helps in preparing for sudden, sharp declines or rises that could push losses beyond the levels predicted by standard models.

>>> <span style="color: purple;">***Alteration of Risk Factor Correlations:***</span>

>>>In historical analyses, correlations between different risk factors (like equity prices, interest rates, or commodity prices) are typically estimated from past data. During extreme events, however, these correlations can change dramatically—sometimes moving to perfect correlation (all risk factors move in the same direction) or zero correlation (they move independently). The stress test component models these alternative scenarios to understand their impact on the portfolio's risk exposure.

>>><span style="color: purple;">***Extreme Adverse Idiosyncratic Movements:***</span>

>>>For risk factors to which a portfolio is especially sensitive, the stress test considers what would happen if there were extreme adverse movements—essentially, sudden shocks to a specific instrument or market. These scenarios test the portfolio's exposure to unexpected events that affect only one or a few key risk factors.

> <span style="color: purple;">***Integration with Expected Shortfall:***</span>

>In practice, the stress test calculates how much higher the Expected Shortfall would be under these extreme scenarios compared to the base measure derived from historical data. The additional margin required is then set based on this increase. This adjustment ensures that the margin requirement covers not only normal market variations but also the possibility of extreme, less likely events.


## Intraday Withdrawal and Deposits of Collateral

A CM may make intraday withdrawals of excess collateral on an account, and/or deposit fresh collateral assets in place of others.

For collateral types that are subject to a traditional "haircut," the impact of a withdrawal or deposit upon the margin excess incorporates the "haircut."

For collateral types that are subject to "collateral in margins" treatment, the impact of a withdrawal or deposit is based upon a "portfolio specific haircut" (PSH) that is communicated to the applicable CM concerned on a daily basis. The PSH represents the sensitivity of the risk profile of that particular account to its position in the relevant security. In other words, the PSH applicable to any given movement of collateral is designed to provide an estimate of the resulting change in margin requirements if the entire margin calculation was recalculated following the movement.

> What is a Haircut?
>>Definition:
A haircut is a risk management tool used to adjust the value of an asset when it is used as collateral. It represents a percentage deduction from the asset’s market value. The purpose of the haircut is to cover potential decreases in the asset’s value due to market fluctuations, ensuring that the collateral remains sufficient under stressed market conditions.

>>How It Works:
For example, if an asset has a market value of $1,000 and a 20% haircut is applied, only $800 of that asset’s value is considered for collateral purposes. This discounted value protects the clearinghouse in case the asset’s price falls significantly.

> Incorporating Haircuts into Collateral Adjustments

>> Withdrawal Scenario:

>> If a CM withdraws collateral that is subject to a haircut, the withdrawal’s effect on the margin excess is calculated based on the asset’s discounted value. This means the reduction in collateral—and consequently the decrease in margin excess—is not the full market value of the asset, but the market value less the haircut.

>> Deposit Scenario:

>> Similarly, when a CM deposits new collateral that must undergo a haircut, the deposit increases the margin excess by the asset’s value after the haircut has been applied. Even though the asset might be worth a certain amount on the market, its effective contribution to the margin is reduced by the haircut percentage.

> Portfolio Specific Haircut (PSH):

>The PSH is a tailored percentage rate calculated daily and communicated to each clearing member (CM). Rather than applying a one-size-fits-all discount, the PSH reflects the sensitivity of the account’s risk profile to movements in that particular collateral or security.

> What does this mean for PHS?

> In practice, the PSH is used to approximate how the margin requirement would adjust if the account's entire margin calculation were performed after a deposit or withdrawal. It acts as a sensitivity factor:

>> Withdrawal Impact: A withdrawal reduces collateral, so the PSH helps estimate how much the margin requirement increases as a result of that specific reduction in risk coverage.

>> Deposit Impact: Conversely, when new collateral is deposited, the PSH estimates how the margin requirement would decrease, reflecting the new collateral’s contribution to covering potential risks.


## Base Haircut

The base component corresponds to the Expected Shortfall (ES) of the portfolio computed at a 99% confidence level using historical estimates of correlations between risk factors:

$Base=ES_{0.99}^H$

## Stress Test

The stress test component is whichever is the greater of two sub-components called <span style="color: purple;">***Dependence</span> and <span style="color: purple;">Concentration.***</span>

The ***<span style="color: purple;"> Dependence </span>*** sub-component can be thought of as *a proportion of the extra risk that would arise if we go further out into the tail of the P&L distribution and consider the effects of replacing historical estimates of dependence between single-stock returns with either perfect correlation or zero correlation*. ES is computed at a 99.5% confidence levels for each of the <span style="color: purple;">***(H)istoric, (P)erfect and (I) ndependent correlation assumptions***</span>. The Dependence sub-component equals a *proportion of the difference between the maximum of the three computations and the base risk requirement*:

$Dependence=0.25*[max(ES_{0.995}^H,ES_{0.995}^P,ES_{0.995}^Z)-ES_{0.99}^H]$

where the H, P, and Z superscripts refer to the correlation structure used.

---

The ***<span style="color: purple;">Concentration </span>*** sub-component can be thought of as a proportion of the extra risk that would arise from extreme adverse idiosyncratic[^1] moves in ***<span style="color: purple;">two risk-factors</span>*** to which the portfolio is especially exposed[^2] , coupled with marginally less severe experience in the remainder of the portfolio. ES is computed at a 99.5% confidence level for each of the two single-factor sub-portfolios having the greatest exposure at that level, and those two results are added to the ES of the residual portfolio computed at a 99% confidence level. The Concentration component is a proportion of the amount by which this sum exceeds the base component:

$Concentration = 0.25 * (^2cCES_{0.995}^H + ^2RES_{0.99}^H - ES_{0.99}^H)$

where $^2cCES_{0.995}^H $ is the sum of the $ES$ of the two single-factor sub-portfolios reporting the greatest exposure at a 99.5% confidence level; and $^2RES_{0.99}^H$ is the $ES$ of the residual portfolio[^3] at a 99% confidence interval.

In order to maintain a conservative approach, all calculations of ES are computed using techniques from ***<span style="color: purple;">Extreme Value Theory</span>***, and the results are increased to take account of an estimate of the sampling error than arises in the ***<span style="color: purple;">Monte Carlo</span>*** sample.

[^1]: The term <span style="color: purple;">“idiosyncratic”</span> in this context refers to risks or movements that are unique to specific risk factors or individual elements of the portfolio, rather than risks that affect the entire market or portfolio uniformly. In other words, idiosyncratic risk arises from very specific circumstances or characteristics tied to particular assets or exposures. When we talk about "extreme adverse idiosyncratic moves," we are referring to significant negative shifts in those individual risk factors that are unique to parts of the portfolio the company is especially exposed to.\
In the Concentration sub-component, this idiosyncratic term captures the extra risk that comes not from broad, market-wide events, but from unusual, severe events that impact specific risk factors. Essentially, it measures how much additional risk could materialize if these individually vulnerable components experienced extreme negative outcomes, while the rest of the portfolio might only experience less severe disruptions.

[^2]: The <span style="color: purple;">single-factor sub-portfolios</span> consist of all positions (options, stock loans, futures etc.) corresponding to one single risk factor. Not all risk factors are considered when selecting these risk factors: for instance positions pertaining to indices are excluded. This reflects the capture only of idiosyncratic risks in this test. If a portfolio contains exposure to less than two sources of idiosyncratic risk, then the formula is adapted in the obvious way.

[^3]: In this context, the portfolio is divided into segments. The two single-factor sub-portfolios with the greatest exposures (evaluated at a 99.5% confidence level) are identified and separated. The "<span style="color: purple;">residual portfolio</span>" is what remains after removing these two highly concentrated risk areas.