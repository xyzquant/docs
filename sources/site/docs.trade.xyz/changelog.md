# Source: https://docs.trade.xyz/changelog

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/changelog/discovery-bounds-v2.md).

### 

March 13, 2026 - Updated Discovery Bounds Methodology

> We upgraded the discovery bounds methodology, starting with CL. The v2 methodology is described in the [External Price](https://docs.trade.xyz/perp-mechanics/external-price) section of the documentation; the following is an archive of the v1 discovery bounds design with which CL was launched.

## 

How it works

Discovery Bounds are leverage-based limits that restrict how far the mark price may deviate from the external oracle price. Enabled by default on all markets, these bounds provide clearly defined price levels within which market makers and other market participants can confidently participate, without risk of liquidation. Their purpose is to prevent price movements that exceed what may reasonably constitute true price discovery.

#### 

Bound Range

The mark price is restricted to move within `1 / max leverage` of the last externally derived oracle price. Discovery Bounds are enforced 24/7, but are particularly relevant during internal pricing sessions (e.g., weekends or holidays), in which the external reference price may remain unchanged for extended periods. Market participants can use this information to manage their risk and margin accordingly.

Refer to the [Specification Index](https://docs.trade.xyz/consolidated-resources/specification-index)for the max leverage and discovery bounds per market.

#### 

Example

If the Silver oracle price is $75 at Friday’s 17:00 ET close, given 25× max leverage, the applicable Discovery Bound is ±4%. As a result, both the mark price and oracle price are restricted to the range $72 – $78 until external pricing resumes on Sunday at 18:00 ET.

If Silver is trading above Friday’s last externally-derived fair price and a trader believes the move does not reflect fair value, they may enter a short position. Once external pricing resumes, the market may reprice toward the externally-derived reference price depending on prevailing market conditions. Importantly, if a trader’s liquidation price lies outside the active price bounds, their position cannot be liquidated while those bounds are in effect.

[PreviousPre-IPO Perpetual Markets Risks and Disclaimers](https://docs.trade.xyz/legal-and-disclaimers/pre-ipo-perpetual-markets-risks-and-disclaimers) [NextOracle Time Constant Update](https://docs.trade.xyz/changelog/oracle-time-constant-update)

Last updated 3 months ago

Was this helpful?