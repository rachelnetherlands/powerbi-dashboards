# Supply Chain Performance

**Live page:** [rachelnetherlands.github.io/powerbi-dashboards/dashboards/supply-chain-performance](https://rachelnetherlands.github.io/powerbi-dashboards/dashboards/supply-chain-performance/)
· **Power BI report:** [open (sign-in required)](https://app.powerbi.com/reportEmbed?reportId=d7ba87c1-d758-4b59-82c4-433fada7a6b9&autoAuth=true&ctid=67faf4e1-0722-4b63-a20e-8aba41330063)

![Supply Chain Performance dashboard](assets/screenshot.png)

## Overview

This dashboard covers a beauty-products supply chain: 100 SKUs across skincare, haircare and cosmetics, 5 suppliers, 5 cities and 3 shipping carriers.
A dark sidebar of tile filters drives the whole page.

| Headline | Value |
|---|---|
| Total revenue | $577.6K |
| Units sold | 46,099 |
| Total supply chain costs | $52.9K |
| Average defect rate | 2.28% |

## Key insights

- **Skincare drives revenue.** It brings in $241.6K (42%), ahead of haircare ($174.5K) and cosmetics ($161.5K).
- **Mumbai and Kolkata** together account for 48% of revenue. Delhi is lowest at 14%.
- **Supplier 1 is the strongest partner.** It has the highest revenue ($157.5K) and the lowest defect rate (1.80%).
- **Supplier 5 has the highest defect rate** (2.67%). Supplier 4 has the highest manufacturing cost ($62.71 per unit).
- **Quality risk:** only 23 of 100 products passed inspection. 36 failed and 41 are still pending.
- **Sea freight is the cheapest mode.** Its average logistics cost is $418, compared with $562 for air.

## Visuals

| Visual | What it shows |
|---|---|
| KPI cards | Revenue, units, costs, average defect rate |
| Revenue by product type | Column chart |
| Shipping costs by carrier | Bar chart |
| Revenue share by location | Donut chart with % labels |
| Supplier scorecard | Revenue, defect rate, lead time and manufacturing cost per supplier |
| Revenue & units by customer segment | Combo chart (columns + line) |
| Sidebar | Tile slicers for product type, location, supplier and carrier, plus a *Clear filters* button |

## Data and build

- **Source:** [Supply Chain Analysis](https://www.kaggle.com/datasets/harshsingh2209/supply-chain-analysis) on Kaggle (100 rows × 24 columns). The raw file is not included here; download it from Kaggle.
- **Preparation:** each column was profiled in Python to check types, ranges and distinct values. The data was clean, so no rows were changed.
- **Model:** a Power BI push dataset (`SupplyChain` table), loaded through the Power BI REST API.
- **Measures:** revenue, units and costs are sums. Defect rate, lead time and manufacturing cost are averages.
- **Theme:** [`assets/theme.json`](assets/theme.json). Import it in the Power BI service under *Design → Import theme*, or in Desktop under *View → Themes → Browse for themes*.

## Limitations

- With only 100 products, a few products can move the averages a lot.
- The source has two similar columns, `Lead time` and `Lead times`, with no explanation of the difference. The scorecard uses manufacturing lead time instead.
- The live report is a secure embed, so viewers need a Power BI account with access to it.
