# Introduction

Blackops Capital is a crypto market-intelligence and alerting platform.

It discovers and scores historical wallet activity with Dune data and cached queries. PostgreSQL stores wallet, transaction, signal, subscription, and research records.

The live-tracked wallet subset refreshes hourly. Helius monitors Solana, TonAPI monitors TON, and Alchemy monitors Robinhood Chain.

Live Trading is a disabled-by-default, admin-only TON research capability. It is isolated from alerting and paper trading. It never trades customer funds automatically.

### Live wallet selection

| Chain     | Score | Other selection gates                                                                            |
| --------- | ----: | ------------------------------------------------------------------------------------------------ |
| SOL       |   30+ | No copytraders; rug rate below 50%; median gain above 1; average gain at least 5; up to 30 coins |
| TON       |   40+ | No copytraders; rug rate below 50%; median gain above 1; average gain at least 5; up to 30 coins |
| Robinhood |   60+ | No copytraders; rug rate at most 15%; median gain at least 1; average gain at least 5            |

## What You Get

* **Alpha Alerts** for correlated smart-wallet buys
* **Wallet Analytics** for subscriber research
* **API access** for subscribed users
* **Admin research tools** for backtesting and paper trading

## Supported Chains

* Solana (SOL)
* TON
* Robinhood Chain (ROBINHOOD)

Polymarket analytics are protected research capabilities. They are not a primary customer feature.

## Next Steps

1. [Create your account](account.md)
2. [Understand alerts](alerts.md)
3. [Explore the API](../api/authentication.md)
