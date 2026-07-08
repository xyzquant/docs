# Source: https://docs.trade.xyz/changelog/funding-rate-formula-update

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/changelog/funding-rate-formula-update.md).

### 

_December 19, 2025 - Scaling Factor for Funding Rate Formula Update_

The default funding rate for crypto perps has remained unchanged at 0.01% / 8 hours since Bitmex first introduced the mechanism in 2016. Borrow rates for traditional asset classes (e.g., equities, commodities) are typically closer to SOFR + 1-2%. We reduced the funding rate across all XYZ markets by applying a scaling factor of 0.5 to Hyperliquid’s funding rate formula. This lowers baseline funding to ~5.5% annualized and results in less aggressive funding during weekend price discovery as well.

The specific formula is `Funding Rate XYZ (F) = 0.5 [Average Premium Index (P) + clamp (interest rate - Premium Index (P), -0.0005, 0.0005)]`.

[PreviousOracle Time Constant Update](https://docs.trade.xyz/changelog/oracle-time-constant-update) [NextEquity Indices v1](https://docs.trade.xyz/changelog/equity-indices-v1)

Last updated 5 months ago

Was this helpful?