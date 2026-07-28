# Wallets

## GET /api/wallets

Query wallets with filters.

This protected subscriber route requires `Authorization: Bearer ACCESS_TOKEN`.

**Query Parameters:**

| Parameter            | Type    | Description                         |
| -------------------- | ------- | ----------------------------------- |
| `minSmartMoneyScore` | number  | Minimum score (0-100)               |
| `maxSmartMoneyScore` | number  | Maximum score                       |
| `minWinRate`         | number  | Minimum win rate (0-1)              |
| `minMoonRate`        | number  | Minimum moon rate                   |
| `minAverageGain`     | number  | Minimum average gain                |
| `minMedianGain`      | number  | Minimum median gain                 |
| `maxRugRate`         | number  | Maximum rug rate                    |
| `minCoinsTraded`     | number  | Minimum coins traded                |
| `maxCoinsTraded`     | number  | Maximum coins traded                |
| `excludeCopytraders` | boolean | Exclude copytraders (default: true) |
| `chain`              | string  | Chain to query                      |
| `sortBy`             | string  | Sort field                          |
| `sortOrder`          | string  | `asc` or `desc`                     |
| `limit`              | number  | Max results                         |
| `page`               | number  | Page number                         |

**Example:**

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/wallets?chain=SOL&minSmartMoneyScore=80&minAverageGain=5&excludeCopytraders=true&limit=20&page=1"
```

***

## GET /api/wallets/:address

Get stats for a specific wallet.

This protected subscriber route requires `Authorization: Bearer ACCESS_TOKEN`.

**Example:**

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/wallets/CWyqwCt2F5Dxn36fsGd4fFnoze82NoBG3M6a8wYCqqsM"
```

## GET /api/wallets/:address/tokens

Get a wallet's token trade history.

This protected subscriber route requires `Authorization: Bearer ACCESS_TOKEN`.

**Example:**

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/wallets/CWyqwCt2F5Dxn36fsGd4fFnoze82NoBG3M6a8wYCqqsM/tokens"
```
