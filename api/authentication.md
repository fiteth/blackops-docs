# Authentication

All API requests require authentication via API key.

## Getting Your API Key

1. Log into [blackops.capital](https://blackops.capital)
2. Go to Account Settings
3. Copy your API key

## Using Your API Key

Add the `X-API-Key` header to all requests:

```bash
curl -H "X-API-Key: YOUR_API_KEY" https://api.blackops.capital/api/signals
```

## Example Request

```bash
curl -H "X-API-Key: YOUR_API_KEY" \
  "https://api.blackops.capital/api/signals?signalTypes=HUGE,BIG&limit=10"
```

## Response Format

All responses return JSON:

**Success:**
```json
{
  "success": true,
  "data": { ... }
}
```

**Error:**
```json
{
  "success": false,
  "error": "Error message"
}
```

## Rate Limits

No rate limits currently enforced. Please be reasonable.
