# Hit Ratio Dashboard

A single-page site that calculates your trading **hit ratio** (win rate), average win/loss, risk:reward, expectancy, and net P&L from a CSV of your trades. No backend, no build step — just one HTML file, hosted free on GitHub Pages.

## How to use it

1. Open the live site (link below once deployed).
2. Click the upload box (or drag & drop) and select a CSV of your trades.
3. Your stats and trade log render instantly. Data is stored only in your browser's `localStorage` — nothing leaves your machine.

## CSV format

| column | required | notes |
|---|---|---|
| `date` | optional | any format, shown as-is |
| `symbol` | optional | ticker name |
| `side` | optional | `long` or `short` — used only if `pnl` is derived |
| `entry` | optional | entry price |
| `exit` | optional | exit price |
| `qty` | optional | position size |
| `pnl` | recommended | profit/loss for the trade (positive = win, negative = loss) |

If you don't include a `pnl` column, the dashboard will try to calculate it from `entry`, `exit`, `qty`, and `side`. A sample file (`sample-trades.csv`) is included, and you can also download one from the "Download sample CSV" button on the site.

## Deploying to your own GitHub Pages

See the setup steps Claude gave you in chat, or:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/hit-ratio-dashboard.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source → Deploy from branch → main / (root)**. Your site will be live at:

```
https://<your-username>.github.io/hit-ratio-dashboard/
```
