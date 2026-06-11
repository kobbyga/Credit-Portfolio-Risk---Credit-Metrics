# Interpretation of Results
 
### Base Case (1-Year Horizon)
 
The one year loss distribution produced by the Monte Carlo simulation exhibits the shape that credit risk theory predicts for a speculative grade portfolio: a large probability mass near zero, reflecting the high likelihood that all obligors survive the period without migrating to default, and a pronounced right tail driven by the possibility of downgrades and clustered default events. The resulting VaR and ES estimates are economically plausible given the credit quality of the names and the scale of the exposures.
 
### Two-Year Horizon Extension
 
Extending the simulation horizon to two years produces materially higher VaR and ES estimates. This is consistent with the theoretical expectation that credit risk compounds over time: migration probabilities widen, the cumulative probability of reaching default increases, and the tail of the distribution becomes heavier as adverse rating paths become more likely. The increase in tail risk between the one and two year horizons is not merely additive; it reflects the non linear accumulation of migration and default risk.
 
### Simulation Stability
 
The stability analysis confirms that the tail risk estimates are not artefacts of simulation noise. Repeating the full Monte Carlo 100 times yields very tight distributions for both VaR and ES, with coefficients of variation of only 2.3% and 4.0% respectively. The 99% confidence intervals are narrow, and boxplot diagnostics show no instability or outliers. This provides strong evidence that the simulation is well specified and that the reported VaR and ES figures are statistically reliable, not sensitive to random seed or trial count.
 
### Stress Testing
 
The stress scenarios behave exactly as the model mechanics and credit risk theory would predict:
 
- **PD shock (historical maxima):** Default becomes the dominant loss driver, producing the largest increases in both VaR and ES of any individual stress scenario. This confirms the model's sensitivity to the default probability input, which is the primary driver of tail losses.
- **Yield curve stress:** Raising discount rates increases the present value of losses across all migration states without altering credit quality. The result is a moderate but meaningful increase in tail risk, reflecting the mark-to-market channel of interest rate stress on a credit portfolio.
- **Credit spread widening:** Proportional widening of spreads generates systematic mark-to-market losses across all rating states, shifting the entire loss distribution to the right. The tail increase is significant but less extreme than the PD shock, as spread widening affects all scenarios rather than concentrating losses in the worst outcomes.
- **Correlation stress:** Increased asset correlation leaves moderate losses largely unchanged but significantly amplifies extreme losses. This is precisely the mechanism that makes correlation a systemic risk driver as it reduces the diversification benefit of the portfolio and causes obligors to deteriorate together in the tail.
- **Combined stress:** Simultaneously stressing PDs, spreads, discount rates, and correlations produces the most severe outcomes, with 99% VaR and ES exceeding $13M and converging closely together. The near equality of VaR and ES under combined stress indicates that the worst 1% of scenarios are uniformly catastrophic, with little variation in severity within the tail.
Overall, the results across all scenarios are coherent, theoretically sound, and consistent with real world credit risk behaviour. The model responds to each stress in the correct direction and with plausible magnitude, and the stability analysis confirms the outputs are robust. The absence of anomalies or counterintuitive patterns across base case, horizon extension, and all five stress scenarios provides confidence that the CreditMetrics implementation is functioning as intended.
 
---
