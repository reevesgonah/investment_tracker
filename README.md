# Investment Tracker

A simple, mobile-first web app for tracking contributions across investment "brackets" and seeing how each one is actually performing, even when you invest in small amounts at different times and prices.

**Live app:** https://reeves-investment-tracker.netlify.app

## Brackets (editable in code)

| Bracket | Purpose |
| --- | --- |
| Emergency Fund (MMF) | Money you may need quickly |
| Mid-term (Bond Fund) | Life transitions / medium horizon |
| Kenyan Stocks (NSE/CDS) | Long-term local growth, logged per company |
| Global (S&P 500 / Ndovu) | Long-term global exposure |

## Features

- **Contribution log per bracket**: date and amount for funds; company, shares and price per share for stocks.
- **Current value per bracket**: you enter it from your broker/fund app, since the app does not pull live prices.
- **XIRR (annualised return)**: accounts for *when* each contribution went in, so irregular monthly top-ups are measured fairly. This is the same calculation as Excel's `XIRR`.
- **Gain / loss and total invested** per bracket, plus a portfolio summary across all brackets.
- **Average cost per share** for the stocks bracket.
- **Export**: download a CSV, or **Copy CSV** for in-app browsers that block downloads.
- Light mode by default, with a dark mode toggle.

## How XIRR is calculated

Contributions are treated as outflows on their dates and the current value as an inflow today. The app finds the annual rate at which those cash flows net to zero (bisection search). XIRR shows "-" until a bracket has a current value, and can fail on unusual patterns such as everything happening on the same day.

## Privacy

There is no server, no account and no tracking. Everything is stored in your browser's `localStorage`, so each visitor starts with an empty tracker and only sees their own data.

- Clearing site data or switching browser/phone wipes it. Export or copy your CSV regularly.
- It does not sync between devices.

## Run locally

Single static file, no build step. Clone the repo and open `index.html` in a browser.

## Deploy your own copy

- **Netlify**: drag the folder onto https://app.netlify.com/drop
- **GitHub Pages**: Settings > Pages > deploy from the `main` branch root.

## Disclaimer

This is a personal record-keeping tool, not financial advice. Figures depend entirely on what you enter, and it does not fetch market data.

## License

MIT, see [LICENSE](LICENSE).
