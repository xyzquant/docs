# Source: https://docs.trade.xyz/risk-and-margining/auto-deleveraging

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/risk-and-margining/auto-deleveraging.md).

#### 

Backstop Liquidator:

The onchain backstop liquidator is live for XYZ markets where cross margin is enabled. This is a fully onchain strategy that takes over backstop liquidatable positions from assets where cross margin is enabled, making those assets less likely to experience ADL during high volatility events. The XYZ backstop liquidator helps manage undercollateralized positions in a way that is intended to reduce bad debt and minimize reliance on ADL. If market liquidations are insufficient, ADL serves as a final mechanism to help preserve system solvency.

#### 

Auto-Deleveraging:

Auto-deleveraging (ADL) is the final safeguard in the liquidation waterfall and exists to ensure system solvency under all conditions. It occurs only when both market and backstop liquidations (for cross margin assets) fail to close a position that has become under-collateralized.

In a perpetual derivatives market, every long is matched by a short, and all positions are collateralized with margin from a shared collateral pool. When a trader’s account equity or an isolated position value becomes negative, the system must rebalance by closing positions on the profitable side. Otherwise, the system would accrue bad debt and violate the zero-sum constraint that total long notional equals total short notional.

When ADL is triggered, users on the profitable side are ranked and selected for forced deleveraging based on a composite index that accounts for both profitability and leverage:

`sorting_index = (mark_price / entry_price) * (notional_position / account_value)`

Users with the highest ranking index (most profitable and most leveraged) are deleveraged first. Their positions are closed at the previous mark price against the insolvent side of the market. This transfer of position value ensures that aggregate system equity remains constant and that the platform has no bad debt.

The system minimizes the frequency of ADL events through conservative maintenance margin settings and by routing most liquidations through market orders or, if necessary, the XYZ backstop liquidator (for cross margin assets). ADL is therefore a rare, last-resort settlement mechanism.

In practical terms, ADL is similar to a system-wide rebalancing event that closes the loop when no external liquidity remains. It is mechanical, transparent, and non-discretionary. Every ADL event can be independently verified on-chain via Hypercore’s settlement records

[PreviousLiquidation Mechanics](https://docs.trade.xyz/risk-and-margining/liquidation-mechanics) [NextGeneral Disclaimer](https://docs.trade.xyz/legal-and-disclaimers/general-disclaimer)

Last updated 1 day ago

Was this helpful?