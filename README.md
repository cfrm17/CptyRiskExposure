# CCounterparty Risk Exposure

Counterparty risk is the risk that the counterparty to a financial transaction may fail to meet its contractual payments, causing financial loss for the bank. Counterparty risk is represented via exposure profiles and is commonly reduced to the peak value of that profile for simplicity. Below is an example of an exposure profile of counterparty X.

This profile can be interpreted by the following statement: at any point in the future, assuming the counterparty survives up to that point, how much exposure might we have against X within our entire portfolio with them – and this inclusive of any agreement or collateral that either us or the counterparty might hold. In this case, because of netting benefits and exposure reduction due to a CSA, the peak exposure only rises to 62 MM USD. The blue and the green lines reflect Potential Future Exposure (PFE) and Expected Exposure (EE) respectively – we will define these in detail below.

Exposure is always a positive number; this is because in a default situation, any money owed from the counterparty to the bank may be lost, but any money owed from the bank to the counterparty must still be settled.

A key feature of CCR is that is quantifies the loss that could occur given that the counterparty is in default. CVA by contrast is a function of both expected loss and probability of default, and as such large exposures to supposedly robust counterparties may escape attention.

The case of Lehman Brothers is a dramatic example of counterparty risk materializing with dire consequences. This would never have been revealed through CVA until shortly before default as their credit ratings were top notch prior to 2008.

A short calendar call spread is created when long term call options are bought and near term call options with the same strike price are sold. On the market risk side, those two options practically hedge themselves, at least with respect to delta. On the counterparty risk side, we notice a spike in exposure corresponding to the uncovered time frame during which the long position remains.

As opposed to CVA and market risk, counterparty risk is not hedgeable. However, it should be managed via exposure limits. We measure exposure at various reporting levels and set corresponding limits.

CCR relies on exposure profiles. They are the product of pricing all deals into the future under Monte Carlo simulation and aggregating using all relevant netting and collateral agreements. Another important feature that is shared with VaR calculation is the simulation of underlying market factor that is required in order to evaluate those deals; however for CCR the time horizon for simulation is in years rather than days or weeks for VaR.

One key feature is the ability for counterparties to be considered in a state of default at the time of evaluating the portfolio we have against them; this allows positive and negative correlations between exposures and counterparty default to be captured (wrong and right way risk).

In the CCR context, simulation models have the objective to forecast within a reasonable range and horizon market factors such as equity prices, interest and FX rates, CDS curves and so on. In order to capture a realistic view of our exposure going forward, and because CCR is not directly hedgeable, those models are typically calibrated using historical data (~3 years) and are not systematically implied from today’s market prices.

Counterparty risk is much less specific for pricing models than it is for simulating the market prices. The only requirement here is that pricing supports “mark to future” or the path dependent value and events of a trade at any point across the simulation time bucket. This involves storing and accessing reset rates, exercise status, realized stochastic events that will affect our exposure in the future. Also counterparty risk needs to price various derivatives, such as swap, forward, barrier option, etc.. See https://finpricing.com/lib/EqBarrier.html
