# Alpha Alerts

Alpha Alerts report correlated smart-wallet buys on SOL, TON, and Robinhood Chain.

## How It Works

The system monitors a wallet subset refreshed hourly. It uses Helius for SOL, TonAPI for TON, and Alchemy for Robinhood Chain.

Eligible buys of one token are grouped for 30 minutes. A signal needs at least two wallets and its chain's score and volume gates.

HUGE means correlation occurred within one minute. BIG means within 10 minutes. WEAK means within 30 minutes. REVIVAL means the token alerted over 24 hours earlier and qualified again.

Created signals are persisted, enriched with token metadata, and emitted through Socket.IO as `new-signal` events to Alpha Feed. Their prices update continuously.

## Alert Dashboard

The dashboard shows:

* Live alerts as they happen
* Historical alerts with performance data
* Chain, type, search, flagged-status, and period filters
* Pagination, sorting, and live connection status

## Performance Tracking

Every alert tracks:

* Entry price at time of alert
* Current price (updated live)
* All-time high since alert
* Percentage gains

Performance counts deduplicate chain and token within the chosen period. Top Gainers uses the highest-gain alert and lists up to 10 unique coins.

## Telegram Alerts

Signals are emitted to Alpha Feed and sent to their chain-and-strength Telegram destination. Browser notifications are also supported.
