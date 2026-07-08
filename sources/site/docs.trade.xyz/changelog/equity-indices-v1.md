# Source: https://docs.trade.xyz/changelog/equity-indices-v1

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/changelog/equity-indices-v1.md).

### 

February 19, 2026 - Updated Index Methodology

> We upgraded the oracle derivation for equity indices (applicable to XYZ100). The v2 methodology is described in the [Equity Indices](https://docs.trade.xyz/asset-directory/equity-indices) section of the documentation; the following is an archive of the v1 oracle design with which XYZ100 was launched.

#### 

External Coverage

The Relayer derives external prices for equity indices 23/5, from Sunday 6:00 PM ET to Friday 5:00 PM ET, with daily gaps from 5:00 PM to 6:00 PM.

#### 

External Price Derivation

For equity indices such as XYZ100, the relayer consumes executable quotes for the underlying traditional (dated) equity index futures from institutional liquidity providers. This provides robust external pricing nearly 23 hours per day, five days per week, extending external coverage beyond daytime cash sessions.

The futures quote is adjusted to an implied spot value which is then included as the oracle price in a relayer update to HyperCore. The conversion of external prices from futures to spot follows the cost-of-carry model (spot—futures parity):

S\=Fe−(r−q)TS = F e^{-(r-q)T}S\=Fe−(r−q)T

where SSS is the spot (oracle) price, FFF is the externally-sourced dated-futures price, TTT is the time to settlement (in years), rrr is the interest rate, and qqq is the forward dividend yield.

The discount rate d\=(r−q)d = (r-q)d\=(r−q) takes into account the prevailing borrow rates, as well as the forward dividend yield of the underlying. The discount rate may be updated periodically in accordance with changing market conditions.

#### 

XYZ100

The XYZ U.S. 100 Index (XYZ100) tracks the value of a modified capitalization-weighted index of 100 large non-financial companies listed on a U.S. exchange.

**Parameters**

- Discount Rate ( r−qr-qr−q): 4%
 
- Primary Datasource: [https://insights.pyth.network/price-feeds/Equity.US.NMH6%2FUSD](https://insights.pyth.network/price-feeds/Equity.US.NMH6%2FUSD)
 

Underlying Suffix

Active Until

Expiration

H6

Copy

```
2026-03-15T22:00:00Z
```

Copy

```
2026-03-20T13:30:00Z
```

M6

Copy

```
2026-06-14T22:00:00Z
```

Copy

```
2026-06-19T13:30:00Z
```

U6

Copy

```
2026-09-13T22:00:00Z
```

Copy

```
2026-09-18T13:30:00Z
```

Z6

Copy

```
2026-12-13T22:00:00Z
```

Copy

```
2026-12-18T13:30:00Z
```

#### 

Example: Deriving Oracle Price for XYZ100

It is important for market participants to be able to independently replicate and verify oracle prices. Below, we walk through an example of deriving the external oracle (spot) price of XYZ100.

From the equity index calendar, we see that the active contract suffix is Z5, with an expiration time `2025-12-19 13:30:00 UTC`.

The Pyth NMZ5 feed is reporting a price of `$24,904.2` at the current time, `2025-10-14 17:06:05 UTC`.

The time to expiry is `0.180285473` years.

At the time of writing, the discount rate r−q\=4.0r-q=4.0%r−q\=4.0. Plugging in the following values into our equation.

- F\=24904.2F = 24904.2F\=24904.2
 
- r−q\=0.04r-q = 0.04r−q\=0.04
 
- T\=0.180285473T = 0.180285473T\=0.180285473
 

We calculate S\=24725.25S = 24725.25S\=24725.25

Thus, we've derived the spot price to be $24,725.25

[PreviousFunding Rate Formula Update](https://docs.trade.xyz/changelog/funding-rate-formula-update) [NextMarket Parameters](https://docs.trade.xyz/changelog/market-parameters)

Last updated 3 months ago

Was this helpful?