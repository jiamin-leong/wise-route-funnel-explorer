# Route Funnel Explorer

An interactive, multi-dimensional analysis tool built for a product analyst case study on launching a new international money-transfer route (INR → USD). It explores a synthetic launch-funnel dataset (73,440 events, 40,223 users) across region, platform, and customer experience.

**Live demo:** https://jiamin-leong.github.io/wise-route-funnel-explorer/

## What it does

- **Explorer tab** — filter the funnel (Transfer Created → Funded → Transferred) by region, platform, experience, and date range; a cross-tab heatmap lets you compare any two dimensions at once to surface segment-level issues that single-dimension views hide.
- **Deck Charts tab** — a weekly % share (cumulative area) chart, a grouped conversion-comparison bar chart, and a ranked comparison view, each with a selectable dimension/metric, styled to match a companion slide deck.
- **Export PNG** on every chart, for reuse in slides or documents.

## Why it exists

Single-dimension cuts of this dataset (region alone, platform alone, experience alone) look only mildly uneven. Crossing three dimensions at once reveals that new customers on Android in APAC have an almost-completely broken funding step (~2.7% Created→Funded vs. 36–61% everywhere else) — a finding invisible in any one-dimensional view. This tool was built to make that kind of cross-dimensional exploration fast and repeatable rather than a one-off analysis.

## Stack

Single self-contained HTML file — vanilla JS, hand-rolled SVG charts, [html2canvas](https://github.com/niklasvonm/html2canvas) for PNG export. No build step; data is pre-aggregated from the source CSV into small JSON files under `data/`.

## Running locally

Any static file server works, e.g.:

```
python3 -m http.server 8000
```

then open `http://localhost:8000`.
