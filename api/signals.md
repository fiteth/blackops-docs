# Signals API

## GET /api/signals

Get alpha alerts.

**Query Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `signalTypes` | string | Comma-separated: `HUGE`, `BIG`, `WEAK` |
| `hours` | number | Signals from last N hours (default: 720) |
| `limit` | number | Max results (default: 50) |
| `offset` | number | Pagination offset |
| `sort` | string | Sort by: `timestamp`, `maxGainPercent`, `walletCount` |
| `order` | string | `asc` or `desc` |

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/signals?signalTypes=HUGE,BIG&limit=10"
```

**Response:**
```json
{
  "signals": [
    {
      "id": "...",
      "token": "TokenMintAddress",
      "tokenSymbol": "SYMBOL",
      "signalType": "HUGE",
      "walletCount": 3,
      "timestamp": "2026-02-18T10:00:00.000Z",
      "entryPriceUsd": 0.0001,
      "currentPriceUsd": 0.0005,
      "athPriceUsd": 0.001,
      "currentGainPercent": 400,
      "maxGainPercent": 900,
      "entryMarketCapUsd": 100000,
      "marketCapUsd": 500000
    }
  ],
  "pagination": {
    "total": 855,
    "limit": 10,
    "offset": 0,
    "hasMore": true
  }
}
```

---

## GET /api/signals/performance

Get signal performance statistics.

**Query Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `signalTypes` | string | Filter by signal types |
| `hours` | number | Time range in hours |

**Example:**
```bash
curl -H "X-API-Key: YOUR_KEY" \
  "https://api.blackops.capital/api/signals/performance?signalTypes=HUGE,BIG"
```

---

## GET /api/signals/transactions

Get recent transactions from tracked wallets.

**Query Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `limit` | number | Max results |
| `wallet` | string | Filter by wallet address |
| `token` | string | Filter by token address |
