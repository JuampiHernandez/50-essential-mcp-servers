[← back to README](../README.md)

# payments & fintech

## 26. stripe

payments, subscriptions, refunds, customer lookups. official.

- **install:** `claude mcp add --transport http stripe https://mcp.stripe.com` then complete oauth — or run locally with `npx -y @stripe/mcp --api-key=YOUR_STRIPE_SECRET_KEY`
- **link:** https://docs.stripe.com/mcp
- **gotcha:** refunds and subscription changes move real money. stripe's own docs recommend enabling human confirmation on tools and warn about prompt-injection when mixing with other servers. control scope with a restricted api key. read-only until proven.

## 27. paypal

invoices, transactions, payouts via the official paypal agent toolkit / mcp.

- **install:** paypal ships an official remote mcp plus the paypal agent toolkit; follow paypal's developer docs for the current endpoint and oauth setup
- **link:** https://www.paypal.ai
- **gotcha:** same as stripe. money-moving tools stay supervised — confirm every write.

## 28. plaid

bank data aggregation, balances, transactions.

- **install:** official plaid MCP, oauth flow
- **link:** https://plaid.com/docs/
- **gotcha:** this is people's banking data. read-only, and think hard about where the context window ends up.

## 29. quickbooks

bookkeeping, invoicing, reconciliation.

- **install:** community/intuit server, oauth
- **link:** https://developer.intuit.com
- **gotcha:** accounting writes have downstream consequences (tax, audit). keep a human signing off.
