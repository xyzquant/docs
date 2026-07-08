# Source: https://docs.trade.xyz/perp-mechanics/overview

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/perp-mechanics/overview.md).

A perpetual derivative contract (or "perp") is a derivative product that allows traders to speculate on an asset's price. Unlike traditional futures, which settle on a fixed date, positions can be held indefinitely. Perps rely on a funding rate mechanism to keep the contract price aligned with the underlying spot price.

XYZ perpetuals are linear contracts, margined and settled in USDC. The oracle is denominated in USD\*, and no USDC/USD conversion is applied. Economic exposure is therefore _quanto_ with USD P&L cash-settled in USDC.

Listed on the XYZ HIP-3 deployment, XYZ perpetual's matching, order types, funding, liquidations, and auto-deleveraging are managed by HyperCore. Three components are bespoke: the _oracle price,_ the _mark price,_ and the _external price_.

The _Relayer_ is responsible for computing oracle, mark, and external prices for each asset and broadcasting updates to HyperCore. TradeXYZ manages a distributed set of Relayer instances which transmit updates approximately every 3 seconds. XYZ's oracle updater address: `0x1234567890545d1Df9EE64B35Fdd16966e08aCEC`.

[PreviousXYZ Architecture](https://docs.trade.xyz/) [NextOracle Price](https://docs.trade.xyz/perp-mechanics/oracle-price)

Last updated 3 months ago

Was this helpful?