# Finance Tracker

> **Demo tool** — all data is stored locally in your browser (localStorage). Nothing is sent to any server. Clearing your browser data will erase your entries.

A lightweight personal finance tracker that runs entirely in the browser with no backend, no accounts, and no dependencies beyond Chart.js.

**Live demo:** https://constantinosMel.github.io/finance-tracker/

---

## Features

### Period Navigation
- Navigate between pay periods using the ← → arrows
- Set your **payday** in Settings (e.g. day 15) — each period runs from that day to the day before the next payday
- Works cleanly across month boundaries (e.g. Mar 15 – Apr 14)

### Transactions
- Log one-time income or expenses with a date, amount, and category
- Edit or delete any entry
- All periods are always editable — past months are not locked

### Recurring Items
- Define recurring income (salary, freelance retainer) and expenses (rent, subscriptions, insurance)
- Supports **monthly** and **yearly** frequencies with a specific day
- Recurring items automatically appear in every relevant period — no manual entry needed

### Debts & Payoff Projections
- Track loans, credit cards, mortgages, and other debts
- Records current balance, original balance, interest rate (APR), and monthly payment
- **Payoff projection chart**: simulates compound interest month-by-month and plots when each debt reaches zero
- Shows estimated payoff date and total interest cost per debt
- Update balance anytime via the "Pay" button

### Dashboard
- Period income, expenses, net balance, and total debt at a glance
- Income vs Expenses bar chart
- Expense breakdown by category (donut chart)
- Recent transactions list

### Settings
- Configurable currency symbol (default: €)
- Configurable payday (1–28)
- Export data as JSON
- Import data from a previous export
- Reset all data to sample values

---

## Data & Privacy

All data lives in your browser's `localStorage` under the key `financeTracker_v2`. No data ever leaves your device.

**To back up your data:** Settings → Export JSON
**To restore:** Settings → Import JSON

---

## Tech Stack

| | |
|---|---|
| Language | HTML, CSS, Vanilla JavaScript |
| Charts | [Chart.js 4.4.1](https://www.chartjs.org/) |
| Font | [Inter](https://fonts.google.com/specimen/Inter) (Google Fonts) |
| Storage | Browser localStorage |
| Hosting | GitHub Pages |
| Build | None — single `index.html` file |

---

## Running Locally

No build step required. Just open the file:

```bash
open index.html
```

Or serve it with any static server:

```bash
npx serve .
# or
python3 -m http.server
```

---

## Deploying

The repo includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that automatically deploys to GitHub Pages on every push to `main`.

To enable: **Repo Settings → Pages → Source → GitHub Actions**

---

## Limitations

This is a **demo/personal tool**, not a production financial application.

- No user authentication
- No cloud sync — data is per-browser, per-device
- No bank integrations or automatic transaction import
- No multi-currency support
- Debt payoff projections assume a fixed monthly payment and do not account for extra payments or rate changes
