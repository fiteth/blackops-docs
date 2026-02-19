# Wallets API

## GET /api/wallets

Query wallets with filters.

**Query Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `minSmartMoneyScore` | number | Minimum score (0-100) |
| `maxSmartMoneyScore` | number | Maximum score |
| `minWinRate` | number | Minimum win rate (0-1) |
| `minMoonRate` | number | Minimum moon rate |
| `minAvgGain` | number | Minimum average gain |
| `minMedianGain` | number | Minimum median gain |
| `maxRugRate` | number | Maximum rug rate |
| `minCoinsTraded` | number | Minimum coins traded |
| `maxCoinsTraded` | number | Maximum coins traded |
| `excludeCopytraders` | boolean | Exclude copytraders (default: true) |
| `sortBy` | string | Sort field |
| `sortOrder` | string | `asc` or `desc` |
| `limit` | number | Max results |
| `page` | number | Page number |

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/wallets?minSmartMoneyScore=80&minWinRate=0.5&limit=20"
```

---

## GET /api/wallets/:address

Get stats for a specific wallet.

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/wallets/CWyqwCt2F5Dxn36fsGd4fFnoze82NoBG3M6a8wYCqqsM"
```

**Response:**
```json
{
  "success": true,
  "data": {
    "address": "CWyqwCt2F5Dxn36fsGd4fFnoze82NoBG3M6a8wYCqqsM",
    "smartMoneyScore": 95.12,
    "coinsTraded": 5,
    "winRate": 0.4,
    "avgGain": 130.28,
    "medianGain": 4.68,
    "moonRate": 0.4,
    "rugRate": 0.2,
    "realizedProfitUsd": 458.38,
    "topCoin1Symbol": "PENGUIN",
    "topCoin1Gain": 608.04
  }
}
```

---

## GET /api/wallets/:address/tokens

Get a wallet's token trade history.

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/wallets/CWyqwCt2F5Dxn36fsGd4fFnoze82NoBG3M6a8wYCqqsM/tokens"
```

**Response:**
```json
{
  "success": true,
  "data": {
    "wallet": "CWyqwCt2F5Dxn36fsGd4fFnoze82NoBG3M6a8wYCqqsM",
    "tokens": [
      {
        "token": "8Jx8AAHj86...",
        "tokenSymbol": "PENGUIN",
        "entryTimestamp": "2026-01-18T14:11:35.000Z",
        "entryMarketCap": 286249.67,
        "entryUsd": 14.25,
        "maxGain": 608.04,
        "realizedGain": 14.5,
        "realizedProfit": 769.69,
        "positionStatus": "EXITED",
        "holdDurationMin": 6965.4
      }
    ],
    "count": 5
  }
}
```
