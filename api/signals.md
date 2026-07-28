# Signals

## GET /api/signals

Get alpha alerts.

This protected subscriber route requires `Authorization: Bearer ACCESS_TOKEN`.

**Query Parameters:**

| Parameter     | Type   | Description                                                                                           |
| ------------- | ------ | ----------------------------------------------------------------------------------------------------- |
| `signalTypes` | string | Comma-separated: `HUGE`, `BIG`, `WEAK`, `REVIVAL`                                                     |
| `chain`       | string | `SOL`, `TON`, or `ROBINHOOD`                                                                          |
| `search`      | string | Optional search term                                                                                  |
| `hours`       | number | Signals from the last N hours; omit for all-time                                                      |
| `limit`       | number | Results per page; default `50`, maximum `200`                                                         |
| `offset`      | number | Pagination offset                                                                                     |
| `sort`        | string | `timestamp`, `maxGainPercent`, `confidence`, `walletCount`, `currentGainPercent`, or `totalSolVolume` |
| `order`       | string | `asc` or `desc`                                                                                       |

The feed also supports its documented volume, flag, and deduplication filters. Policy-invalidated rows are excluded.

**Example:**

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/signals?signalTypes=HUGE,BIG&limit=10"
```

## GET /api/signals/performance

Get signal performance statistics.

Results deduplicate by chain and token for the selected filters.

**Query Parameters:**

| Parameter     | Type   | Description            |
| ------------- | ------ | ---------------------- |
| `signalTypes` | string | Filter by signal types |
| `hours`       | number | Time range in hours    |

**Example:**

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/signals/performance?signalTypes=HUGE,BIG"
```

***

## GET /api/public/top-alerts

Get up to 10 unique top-performing coins. This endpoint is public.

**Query Parameters:**

| Parameter     | Type   | Description                      |
| ------------- | ------ | -------------------------------- |
| `chain`       | string | `SOL`, `TON`, or `ROBINHOOD`     |
| `signalTypes` | string | Comma-separated signal types     |
| `hours`       | number | Default 30 days; maximum 90 days |
