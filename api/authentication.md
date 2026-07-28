# Authentication

Protected routes require a signed-in session with a valid Bearer access token. Subscriber routes also require an active subscription. Admins bypass the subscription gate.

## Using an access token

The browser application obtains access and refresh tokens through its login and signup flows. No customer API key exists.

Send the access token in the `Authorization` header:

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" https://api.blackops.capital/api/signals
```

## Example Request

```bash
curl -H "Authorization: Bearer ACCESS_TOKEN" \
  "https://api.blackops.capital/api/signals?signalTypes=HUGE,BIG&limit=10"
```

## Rate Limits

The general limit is 100 requests per minute.

Credential-entry endpoints allow 10 failed attempts per 15 minutes. Successful attempts do not consume this failure budget.
