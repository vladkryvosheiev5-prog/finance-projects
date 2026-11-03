# Cost of Capital Analysis: Coca-Cola (KO) vs. Amazon (AMZN)

A finance project for ECON 372 that estimates equity beta, cost of equity, cost of debt and WACC for two very different companies, then compares what the results say about risk, capital structure and growth.

## Project Goals

- Apply portfolio risk concepts (variance, correlation, diversification) to real firms
- Estimate equity betas using regression analysis
- Compute cost of equity using the Capital Asset Pricing Model (CAPM)
- Estimate cost of debt from financial statements
- Calculate the Weighted Average Cost of Capital (WACC)
- Compare the two firms' risk and capital structure

## Files

| File | Description |
|---|---|
| `Finance_Assignment_Workbook.xlsx` | Excel workbook with all calculations as live formulas |
| `Finance_Assignment_Report` | Short report interpreting the results |

**Workbook sheets:** Summary, Data, Returns, Regression, CAPM, Cost of Debt, WACC.

## Method

1. **Data:** 61 month-end adjusted closing prices (Oct 2021 – Oct 2026) for KO, AMZN and the S&P 500 (^GSPC), giving 60 monthly returns over five years.
2. **Beta:** Regress each stock's monthly return on the S&P 500's monthly return: `R(i) = α + β·R(m) + ε`.
3. **Cost of equity (CAPM):** `r(e) = r(f) + β × (market risk premium)`.
4. **Cost of debt:** `r(d) = interest expense ÷ average total debt` (FY2025 10-K figures), then adjusted for taxes: `r(d)(1 − Tc)`.
5. **WACC:** `(E/V)·r(e) + (D/V)·r(d)(1 − Tc)`, using market value of equity and book value of debt.

## Key Results

| | KO | AMZN |
|---|---|---|
| Beta (β) | 0.281 | 1.495 |
| R² | 7.0% | 45.9% |
| Annualized volatility | 16.4% | 34.0% |
| Cost of equity | 6.45% | 13.12% |
| Pre-tax cost of debt | 3.67% | 3.85% |
| After-tax cost of debt | 2.91% | 3.09% |
| Debt weight (D/V) | 9.9% | 2.4% |
| **WACC** | **6.10%** | **12.88%** |

## Main Takeaways

- **AMZN has much higher systematic risk.** Its beta is about 1.5, so it amplifies market moves, while KO (beta of about 0.28) is a defensive stock. This drives a cost of equity roughly twice as high.
- **KO's low WACC comes from cheap equity, not heavy debt.** KO uses more leverage than AMZN, but its WACC is low mainly because its equity risk is low. AMZN's WACC is almost equal to its cost of equity because debt is a tiny share of its capital.
- **Diversification link:** Only about 7% of KO's variance is systematic, so roughly 93% is diversifiable firm-specific risk. For AMZN, about 46% of variance is systematic. CAPM prices only the risk that diversification cannot remove.

## Assumptions

- Risk-free rate of 4.9% (approximate 10-year U.S. Treasury yield in early November 2026) and a market risk premium of 5.5%. Both are editable input cells in the workbook.
- KO tax rate uses the company's underlying effective rate (20.7%); AMZN uses provision ÷ pre-tax income (19.6%).
- Equity values use recent share prices and shares outstanding from the latest 10-Q filings; debt uses FY2025 book values as a proxy for market value.

## Limitations

- The five-year window is short, so KO's beta has a wide confidence interval (0.011 to 0.552).
- The S&P 500 index excludes dividends.
- AMZN's cost of debt is approximate: debt covers long-term debt only, while interest expense includes finance-lease interest.
- Neither firm's current yield to maturity was used.
- Price data comes from Digrin's monthly price history (Yahoo Finance-based). The source shows the same KO price for Nov and Dec 2022, which was kept as published.
