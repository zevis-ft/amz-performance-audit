# Amazon PPC & Performance Audit Dashboard

A fully client-side, zero-install analytics dashboard for Amazon sellers. Upload your data exports and get an interactive multi-tab audit — no server, no account, no data ever leaves your browser.

🔗 **[Live Demo → GitHub Pages](https://your-username.github.io/amazon-audit/)**

---

## Features

| Tab | What it shows |
|-----|---------------|
| **Executive Dashboard** | Monthly sales trend (total / ad / organic), ACOS, TACOS, CTR, CVR — with YOY & MOM % changes |
| **ASIN Performance** | Per-ASIN and parent/child view with PPC cross-reference and TACOS |
| **PPC Performance** | Ad type summary, placement performance, top/wasted campaigns, negative keyword audit |
| **Search Term Analysis** | Aggregated search terms with action tags: Isolate, Potential Negative |
| **Search Query Performance** | Brand Metrics signals: High Opportunity, Underinvested, Inefficient, Dominant, Defensive Gap |
| **Targeting Performance** | Keywords & product targets classified as Scale, Reactivate, Wasted Spend, Low Impressions |

---

## How to Use

### 1. Open the dashboard
- **GitHub Pages:** visit the live link above
- **Local:** download `index.html` and open it in any modern browser (Chrome, Edge, Firefox, Safari)

### 2. Upload your data files

All files are processed locally in your browser. Nothing is uploaded anywhere.

| Slot | File Type | How to Export from Amazon |
|------|-----------|--------------------------|
| **Business Report** | CSV · Monthly | Seller Central → Reports → Business Reports → Detail Page Sales and Traffic by Month |
| **ASIN Performance** | CSV · 30 Days | Seller Central → Reports → Business Reports → Detail Page Sales and Traffic by Child Item |
| **Amazon Ads Bulk File** | XLSX · 30 Days | Amazon Ads → Bulk Operations → Download Bulk File (include SP, SB, SD sheets + search term reports) |
| **Copy Response (JSON)** | JSON · Monthly | Amazon Ads → Campaign Manager → Overview → select all campaigns → Export (or use the Paste JSON option) |
| **Brand Metrics** | CSV(s) · Last Month | Amazon Ads → Brand Metrics → Search Query Performance → Export (one file per brand, multiple supported) |

> **Tip:** For the JSON file you can either upload the file or paste the JSON directly using the **Paste JSON** toggle on the upload card.

### 3. Click "⚡ Process & Analyse"

The dashboard builds instantly. All 6 tabs become interactive.

---

## Tab Details

### Executive Dashboard
- Sales trend chart: Total Sales, Ad Sales, Organic Sales lines + Ad Spend bar (dual Y-axis)
- CTR vs CVR trend chart
- ACOS / TACOS / Spend trend chart
- Monthly breakdown table with **YOY and MOM % columns** for Total Sales, Ad Sales, Organic Sales, and Ad Spend
- Supports up to 24 months of data; warns if Business Report and JSON date ranges don't match

### ASIN Performance
- Parent / Child toggle
- PPC spend and sales cross-referenced from the Ads Bulk file
- ASIN thumbnails with clickable links to Amazon product pages
- Column filter on TACOS

### PPC Performance
- Ad type summary (SP / SB / SD) with spend %, ACOS, CPC, ROAS
- Placement performance table (Top of Search, Rest of Search, Product Pages, Amazon Business)
- Top 10 performing and top 10 wasted campaigns
- **Auto & Broad Negative Check:** detects missing ad-group-level negative keywords and multi-ASIN wasted spend campaigns

### Search Term Analysis
- Terms aggregated across campaigns (no double-counting)
- **Freq** column: how many campaign/ad-group combos the term appeared in
- **Targeted In** column: which match types the term is currently active under (Broad / Phrase / Exact)
- **Action tags:**
  - 🔵 **Isolate** — orders > 3 but high ACOS → move to own campaign
  - 🔴 **Potential Negative** — no orders with high spend, or low orders + high ACOS
- Column filters on Action and Targeted In

### Search Query Performance (Brand Metrics)
- Upload one CSV per brand/period — all data combined with accurate brand attribution
- Brand dropdown filter (by brand name, showing all periods for that brand)
- Signal tags: 🚀 High Opportunity · 📈 Underinvested · ⚠️ Inefficient · 👑 Dominant · 🛡 Defensive Gap
- SP spend cross-reference from search term reports
- Column filters on Targeted and Signal

### Targeting Performance
- Covers SP/SB keywords + SP/SB product targeting + SD contextual/audience
- Classified by: Scale · Reactivate · Relaunch · Wasted Spend · Low Impressions · No Impressions
- Campaign names correctly inherited from parent rows in the bulk file hierarchy
- Column filters on Type, Target Type, Match, State, Signal

---

## Privacy & Security

- **100% client-side** — all file parsing and analysis runs in your browser via JavaScript
- **No server** — there is no backend; the app is a single HTML file
- **No data transmitted** — your sales data, ASIN data, and ad data never leave your device
- **No account required** — no login, no cookies, no tracking
- Works fully offline after the page loads (CDN libraries are loaded once on first open)

---

## Technical Stack

| Library | Purpose | Version |
|---------|---------|---------|
| [PapaParse](https://www.papaparse.com/) | CSV parsing | 5.4.1 |
| [SheetJS (xlsx)](https://sheetjs.com/) | XLSX parsing | 0.18.5 |
| [Chart.js](https://www.chartjs.org/) | Charts | 4.4.0 |
| Vanilla JS + HTML | Everything else | — |

No build step. No npm. No framework. Just open `index.html`.

---

## Development

```bash
# Clone
git clone https://github.com/your-username/amazon-audit.git
cd amazon-audit

# Open locally — no build needed
open index.html   # macOS
start index.html  # Windows
xdg-open index.html  # Linux
```

To deploy to GitHub Pages:
1. Push `index.html` to the `main` branch
2. Go to **Settings → Pages → Source → main branch / root**
3. Your dashboard is live at `https://your-username.github.io/amazon-audit/`

---

## Changelog

### v3 (current)
- 6-tab dashboard: Executive, ASIN, PPC, Search Terms, Brand Metrics, Targeting
- YOY / MOM columns in monthly breakdown
- Search term aggregation + action tags (Isolate / Potential Negative)
- Multi-brand support in Brand Metrics with brand filter dropdown
- Campaign name inheritance fix for targeting/keyword rows
- Bidding adjustment placement name normalization
- Multi-ASIN wasted spend detection in auto/broad campaigns
- Ad-group-level negative keyword detection
- Filterable column dropdowns across all data tabs
- JSON paste mode for Copy Response

### v2
- ASIN Performance with parent/child toggle and ASIN image thumbnails
- PPC Performance overview with ad type summary
- Search Query Performance with signal engine

### v1
- Executive dashboard with monthly sales trend
- Business Report + JSON monthly ads data merge

---

## License

MIT — see [LICENSE](LICENSE)
