# Sigma AI Performance Dashboard

A interactive HTML mockup of a client-facing AI performance reporting suite, designed to mirror the look and feel of a Sigma BI dashboard. Built to support internal stakeholder reviews and Confluence documentation.

---

## Overview

This dashboard visualises the performance and impact of AI-driven products across six reporting areas, including player segmentation, predictive modelling, risk detection, and personalisation. It is based on the Snowflake data architecture defined in the AI Reporting Framework specification (`CENTRALDW.BUS`).

The mockup is built as a single self-contained HTML file using Chart.js for data visualisation.

---

## Live demo

[View dashboard](https://michaelaspiteri.github.io/Sigma-AI-Performance-Dashboard/sigma_ai_executive_dashboard.html)

---

## Dashboards included

| Tab | Purpose |
|-----|---------|
| Executive overview | High-level KPIs, revenue trend, AI vs non-AI split, uplift summary |
| Player segmentation | VIP tier distribution, CLTV bands, segment migrations, RG risk |
| AI model performance | Model accuracy metrics, predicted vs actual, AUC trends, model metadata |
| Recommendations | CTR, conversion funnel, top games, revenue by week |
| Risk & compliance | High-risk player trends, bonus abuse breakdown, deposit growth by risk |
| Player drill-down | Individual player scores, wallet behaviour, activity timeline, recommended games |

---

## Data source (production)

All source tables are located in `CENTRALDW.BUS` on Snowflake.

**Dimension tables:** `dim_players`, `dim_games`, `dim_providers`, `dim_brands`

**Fact tables:** `fct_wagering`, `fct_wallet`, `fct_player_scores`

**Reporting layer (aggregated):** `agg_player_daily`, `agg_player_scores_latest`, `agg_player_scores_history`, `agg_ai_performance_daily`

Data refreshes every 12 hours for fact aggregations and every 48 hours for dimension tables.

---

## Embedding in Confluence

This dashboard is designed to be embedded in Confluence via the iFrame macro.

1. Open or create a Confluence page
2. Type `/iframe` to insert the iFrame macro
3. Set the src to the live URL above
4. Set height to `1100px` and width to `100%`
5. Switch the Confluence page to **Full width** layout for best results

---

## Running locally

No build step required. Just open the HTML file directly in a browser:

```bash
git clone https://github.com/MichaelaSpiteri/Sigma-AI-Performance-Dashboard.git
cd Sigma-AI-Performance-Dashboard
open sigma_ai_executive_dashboard.html
```

---

## Tech stack

- Plain HTML, CSS, JavaScript — no framework or build tool
- [Chart.js 4.4.1](https://www.chartjs.org/) via CDN for all charts
- [Tabler Icons](https://tabler.io/icons) via CDN for iconography
- Designed to match Sigma's visual language and layout conventions

---

## Status

This is a **mockup with sample data** for design review and stakeholder alignment purposes. It is not connected to live Snowflake data. Production dashboards will be built directly in Sigma once KPI definitions and aggregation grains are finalised.

Open points before production build:
- Warehouse confirmation (`ANALYTICS_WH`)
- KPI finalisation with client
- Aggregation grain sign-off
- AI impact attribution methodology
- Model version retention strategy

---

## Author

Michaela Spiteri
