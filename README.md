# GPUComputeTerminal

Terminal-style Monte Carlo dashboard for AI GPU/accelerator spot pricing with hyperscaler capex tracking, model release sentiment, and token economics.

## Features

- **Monte Carlo simulation** — Geometric Brownian Motion engine, configurable paths (100 / 1k / 10k) and horizons (5 / 30 / 90 / 252 periods).
- **SKU watchlist** — 10 SKUs (H100, B200, H200, A100, L40S…).
- **Live tick simulation** — synthetic ticks every few seconds with deterministic seed for reproducibility.
- **Strategy signals** — BUY / AVOID / WAIT derived from Price MA Cross, Utilization MR, Capex Momentum, Token Skew, Infra Chatter.
- **GCT chatter panel** — positive / neutral / negative sentiment with sample posts per SKU.
- **SKU KPIs** — aggregate value, P&L, expected return, 95% VaR, Sharpe, sentiment.
- **Custom panel** — hyperscaler 2026 capex bar chart and per-SKU tokens-per-dollar curve.
- **Accessible by default** — WCAG 2.2 AA: keyboard nav, ARIA live regions, screen-reader chart alternatives, 4.5:1 contrast in dark mode.

## Running

No build step. Live at https://pablowilliams.github.io/GPUComputeTerminal/.

For local development, any static server works:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Data pipeline

The dashboard reads `data/quotes.json` on load and on each tick. A scheduled GitHub Action (`.github/workflows/refresh-data.yml`) regenerates synthetic close histories every hour so the visible data evolves. Replace the generator with a real data source to go live.

## Architecture

- `index.html` — semantic layout, landmarks, headings
- `app.js` — data, Monte Carlo engine, sentiment, signal logic, rendering
- `styles.css` — dark terminal theme with AA-contrast tokens

## License

Private. All rights reserved.
