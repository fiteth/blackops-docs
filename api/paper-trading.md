# Paper Trading

## GET /api/paper-trading/strategies

{% hint style="warning" %}
**Admin-only endpoint.** Paper Trading is a restricted research tool.
{% endhint %}

List all paper trading strategies.

**Example:**

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/paper-trading/strategies"
```

***

## GET /api/paper-trading/strategies/:id

Get a specific strategy with stats.

***

## POST /api/paper-trading/strategies

Create a new strategy.

**Request Body:**

```json
{
  "name": "Conservative HUGE",
  "signalTypes": ["HUGE"],
  "positionSizeSol": 1,
  "initialStopLossPercent": -50,
  "takeProfitLevels": [
    { "percent": 50, "sellPercent": 25, "newStopLossPercent": -20 },
    { "percent": 100, "sellPercent": 25, "activateTrailingStop": true, "trailingStopPercent": -30 },
    { "percent": 200, "sellPercent": 25 },
    { "percent": 500, "sellPercent": 25 }
  ],
  "isActive": true
}
```

***

## DELETE /api/paper-trading/strategies/:id

Delete a strategy.

***

## GET /api/paper-trading/positions

List positions.

**Query Parameters:**

| Parameter    | Type   | Description        |
| ------------ | ------ | ------------------ |
| `strategyId` | string | Filter by strategy |
| `status`     | string | `OPEN` or `CLOSED` |

***

## GET /api/paper-trading/stats

Get overall paper trading performance stats.
