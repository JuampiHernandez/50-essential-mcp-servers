[← back to README](../README.md)

# trading & markets

same warning as web3, louder: execution servers place real orders. market volatility means slippage. use limit orders, scrutinize every agent-suggested trade before approving, and paper-trade first.

## 36. alpaca

official server (v2, rebuilt on fastmcp). trade us equities, etfs, options and crypto, manage a portfolio, pull real-time data — all in plain english. 61 tools.

- **install:** clone `alpacahq/alpaca-mcp-server`, configure with api keys; supports paper and live environments
- **link:** https://github.com/alpacahq/alpaca-mcp-server
- **gotcha:** start in the paper environment. seriously. guard the keys like passwords and review every suggested order — the docs themselves push limit orders over instant to control slippage.

## 37. ccxt

unified read access to 20+ crypto exchanges (binance, coinbase, kraken, bybit) for market data and analysis.

- **install:** community server (lazydino) via npx
- **link:** https://github.com/lazy-dinosaur/ccxt-mcp
- **gotcha:** community-maintained. if you enable trade execution rather than just data, you're in real-money territory — treat it that way.

## 38. polygon.io

market data feeds — stocks, options, forex, crypto, aggregates and trades.

- **install:** polygon.io publishes an official mcp server; grab the current package and api-key setup from their docs
- **link:** https://polygon.io/docs
- **gotcha:** data only, no execution. clean and safe.

## 39. coingecko

crypto prices, market caps, historical data.

- **install:** `claude mcp add --transport http coingecko https://mcp.api.coingecko.com/sse`
- **link:** https://docs.coingecko.com
- **gotcha:** free tier is rate-limited. fine for research.

## 40. tradingview

charts and market data context.

- **install:** community server via npx
- **link:** https://www.tradingview.com
- **gotcha:** community-maintained and scrape-based — fragile when tradingview changes their site. treat as best-effort.
