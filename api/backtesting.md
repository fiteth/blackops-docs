# Backtesting API

## POST /api/backtesting/simulate

Run a backtest simulation.

**Request Body:**

```json
{
  "minSmartMoneyScore": 50,
  "maxSmartMoneyScore": 100,
  "minCoinsTraded": 5,
  "maxCoinsTraded": 30,
  "minAverageGain": 5,
  "minMedianGain": 1.5,
  "maxRugRate": 0.3,
  "minMoonRate": 0.2,
  "maxFailureRate": 0.5,
  "minWalletCount": 2,
  "minCumulativeScore": 100,
  "correlationWindowMinutes": 5,
  "excludeCopytraders": true
}
```

**Response:**
```json
{
  "summary": {
    "totalTokens": 150,
    "totalWallets": 45,
    "walletsMeetingCriteria": 200,
    "totalRugs": 15,
    "rugRate": 0.1,
    "avgMaxGain": 45.5,
    "medianMaxGain": 12.3,
    "count5x": 50,
    "count10x": 30,
    "count20x": 15,
    "count50x": 8,
    "count100x": 3
  },
  "parameters": { ... },
  "tokens": [ ... ]
}
```

---

## GET /api/backtesting/stats

Get statistics about available backtesting data.

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/backtesting/stats"
```

---

## GET /api/backtesting/correlations

Get correlation analysis between wallet metrics and outcomes.

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/backtesting/correlations"
```
