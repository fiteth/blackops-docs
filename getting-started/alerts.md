# Understanding Alerts

Alerts identify correlated smart-wallet buys on Solana, Robinhood, and TON.

The engine groups eligible buys of one token in a rolling 30-minute window. It requires at least two wallets and applies chain-specific score and volume gates.

## Alert Types

| Type        | Timing after correlation                              |
| ----------- | ----------------------------------------------------- |
| **HUGE**    | Within 1 minute                                       |
| **BIG**     | Within 10 minutes                                     |
| **WEAK**    | Within 30 minutes                                     |
| **REVIVAL** | A token alerted over 24 hours earlier qualifies again |

These are timing categories, not confidence labels.

### Trigger gates

| Chain     | Wallets | Combined score | Combined buys |
| --------- | ------: | -------------: | ------------: |
| Solana    |      2+ |            80+ |         $150+ |
| TON       |      2+ |           100+ |         $100+ |
| Robinhood |      2+ |           160+ |    No minimum |

## Alert Information

Each alert includes:

* A summary of smart wallets, score, and buy window
* Entry price and market cap
* Current price and gain percentage
* All-time high since alert

The summary states that X smart wallets, with combined score Y, bought within Z minutes. Alert cards do not provide wallet addresses or individual wallet buys.

## Filtering Alerts

Use the dashboard filters to focus on:

* Chain, signal type, and performance period
* Search, sorting, pagination, and flagged status
* Performance and Top Gainers views

## Real-Time Updates

Signals appear in Alpha Feed through a live connection. They can also reach chain-and-strength Telegram destinations and browser notifications.

Signals are continuously repriced. They retain entry, current, and ATH performance. Performance views deduplicate each chain and token within their selected period.
