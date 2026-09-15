# Compute Market Monitor

A compact pricing monitor for comparing accelerator capacity across public-cloud and broker-style listings. It turns an intentionally synthetic price history into repeatable cost scenarios and workload-normalised comparisons.

## What it demonstrates

- Seeded lognormal scenarios over synthetic hourly accelerator prices.
- Spot-versus-reserved comparisons, workload economics and capacity signals.
- Inspectable calculations with chart summaries and accessible controls.
- Static deployment with no account, API key or hidden backend dependency.

The catalogue and price series are synthetic. Values illustrate product and engineering decisions; they are not quotations or purchasing advice.

## Run locally

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000`. The published version is available through GitHub Pages.

## Engineering note

The scenario engine is shared with four sibling studies. This application owns the compute-market terminology, cost model, data adapter and accelerator-specific comparison panels.
