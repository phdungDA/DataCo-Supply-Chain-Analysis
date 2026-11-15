# Verification notes

Statements in `reports/` checked against the data (rebuilt from the Power BI model: 180,519 items, 65,752 orders, 20,652 customers). Use the right-hand column when talking about the project.

| # | Statement in the reports | What the data shows | Safer wording |
|---|---|---|---|
| 1 | "180,000+ orders" | 180,519 order **items** in 65,752 orders | "180,000+ order records (65,752 orders)" |
| 2 | "98,000+ orders were late" (deck, slide 3) | 98,977 late items = 36,048 late orders | "98,977 late order items (36,048 orders)" |
| 3 | "~7,800 cancelled orders" | 7,754 items = 2,855 orders | "7,754 cancelled items" |
| 4 | Late rate ~55% | 54.8% of items (Python); 57.3% of non-cancelled orders (Power BI measure) | State which basis |
| 5 | Strong negative correlation, r = −0.32, between discount rate and profit; at ≥15% "most orders" lose money | The report's own heatmap shows −0.05 (clipped profit); raw −0.02. Loss-making items are 18.5–19% in every discount band; avg profit/item falls $23.9 → $18.4 from 0–5% to >20% | "Discounts only weakly erode margin (r ≈ −0.05)" |
| 6 | Real shipping days: mean ≈ median ≈ 3.4, low CV | Mean 3.50, median 3.0, std 1.62 (CV 46%) | Use 3.5 / 3.0 |
| 7 | Standard Class promises only 1–2 days and is the bottleneck | Standard Class: scheduled 4, real 4.0, late 38.1%. First Class (1 vs 2 days) is 95.3% late, Second Class (2 vs 4) 76.7% | Name First/Second Class |
| 8 | Delays concentrate in geographic hotspots (deck, slide 4, marked as "expected") | 22 of 23 regions are 52.8–58.0% late; markets 54.4–55.2% | "Delays are systemic, not regional" |
| 9 | Late delivery erodes profit (compensation, returns, churn; deck, slide 5) | Avg profit/item $21.62 late vs $22.40 not late; the dataset has no compensation, return or churn fields | Do not claim a cost effect |
| 10 | "VIP At Risk" customers were hit by late or cancelled orders | Late rate 54.4% (At Risk) vs 54.9% (all); cancelled 4.0% vs 4.3% | "Highest-value customers who have not bought recently" |
| 11 | Setting scheduled days to 3–4 cuts late rate from 55% to <15% | What-if on non-Same-Day modes (orders, excl. cancelled): 3 days → 50.1%, 4 days → 34.3%, 5 days → 18.5% | Quote the what-if |
| 12 | TRANSFER carries high cancellation and fraud | Confirmed: all 4,062 suspected-fraud items are TRANSFER; 15.5% of TRANSFER items cancelled (others 0%) | Use as is |
| 13 | RFM segment sizes | Reproduced exactly (At Risk 4,103 / 30.2% of revenue, etc.) | Use as is |
| 14 | Cap discounts at 10–12% | No cliff in the data; effect is gradual and small | Frame as "review discount policy" |
| 15 | "Consumer is over 50% of customers" | 51.8% | Use as is |

Other points to know:
- Profit was winsorised at [−79.70, 151.50] in the notebook (18,942 rows), which hides the largest losses (raw minimum −$4,275).
- 2018 contains January only, so "revenue by year" in Power BI shows an artificial drop.
- Shipping days are uniformly distributed (2–6), a sign of synthetic data.
