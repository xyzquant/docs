# Source: https://docs.trade.xyz/risk-and-margining/margin-modes

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/risk-and-margining/margin-modes.md).

XYZ inherits its margining mechanisms from Hypercore.

#### 

Margin Mode

When opening a position, a margin mode is selected. Refer to the 'Margin Mode' column on [Specification Index](https://docs.trade.xyz/consolidated-resources/specification-index) to see the default margin mode for each market.

_Cross Margin:_ is the default for markets where cross margin is enabled. Cross margin allows for maximal capital efficiency by sharing collateral between all other cross margin positions.

_Normal Isolated Margin:_ allows an asset's collateral to be constrained to that asset. Liquidations in that asset do not affect other isolated positions or cross positions. Similarly, cross liquidations or other isolated liquidations do not affect the original isolated position.

_Strict Isolated Margin_: functions the same as isolated margin, with the additional constraint that margin cannot be removed. Margin is proportionally removed as the position is closed.

#### 

Initial Margin and Leverage

Leverage can be set by a user to any integer between 1 and the max leverage. Max leverage depends on the asset.

The margin required to open a position is `position_size * mark_price / leverage`. _Normal Isolated Margin_ positions support adding and removing margin after opening the position. Isolated positions will apply unrealized pnl as additional margin for the open position. The leverage of an existing position can be increased without closing the position. Leverage is only checked upon opening a position. Afterwards, the user is responsible for monitoring the leverage usage to avoid liquidation. Possible actions to take on positions with negative unrealized pnl include partially or fully closing the position or adding margin (if isolated).

**Maintenance Margin:** the minimum collateral you must keep to avoid liquidation. If your account equity (collateral + PnL) falls below the maintenance level, you'll be liquidated. The maintenance level is currently determined by multiplying the maintenance margin by the total open notional position. The maintenance margin is set to half of the initial margin at max leverage for that asset, which varies from 3-40x. In other words, the maintenance margin ranges from 1.25% (at 40x max leverage) to 16.7 (at 3x max leverage).

[PreviousRoll Schedules](https://docs.trade.xyz/consolidated-resources/roll-schedules) [NextLiquidation Mechanics](https://docs.trade.xyz/risk-and-margining/liquidation-mechanics)

Last updated 6 days ago

Was this helpful?