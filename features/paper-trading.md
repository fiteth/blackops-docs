# Paper Trading

{% hint style="warning" %}
**Admin-only research tool.** Paper Trading is not a subscriber feature.
{% endhint %}

Simulate trades with signals without risking capital.

## How It Works

Research strategies can simulate trades when alerts fire. Track modeled performance without real money.

## Creating a Strategy

Define your strategy with:

* **Name** - Identify your strategy
* **Signal types** - Which alerts to trade (HUGE, BIG, WEAK, REVIVAL)
* **Position size** - SOL amount per trade
* **Initial stop loss** - When to cut losses (e.g., -50%)
* **Take profit levels** - Up to 5 TP levels with:
  * Target percentage gain
  * Percentage of position to sell
  * Optional: new stop loss after TP hit
  * Optional: activate trailing stop

## Example Strategy

```
Signal types: HUGE, BIG
Position size: 1 SOL
Stop loss: -50%

TP1: +50% → sell 25%, move stop to -20%
TP2: +100% → sell 25%, activate trailing stop at -30%
TP3: +200% → sell 25%
TP4: +500% → sell remaining
```

## Tracking Performance

View for each strategy:

* Open and closed positions
* Total realized P\&L
* Win rate
* Individual trade executions
* Entry/exit prices and timing

## Positions

Each position tracks:

* Entry price and timestamp
* Current price (live updated)
* Remaining position percentage
* Stop loss status
* Trailing stop (if activated)
* All executions (TP hits, stop outs)
