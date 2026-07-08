# Source: https://docs.trade.xyz/asset-directory/equity-indices

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/asset-directory/equity-indices.md).

### 

External Price Derivation

For equity indices such as SP500® and XYZ100, the relayer consumes executable quotes for both the underlying spot index and the corresponding traditional (dated) equity index futures from institutional liquidity providers. During the cash session, the spot index value is used directly as the oracle price. Outside the cash session, the futures price is discounted to an implied spot value using an empirically observed discount rate. This two-source design extends spot pricing coverage.

#### 

Cash Session

During the cash session, the spot index value serves as the oracle price. Simultaneously, the relayer observes the spot–futures basis and derives the implied annualized net discount rate:

dt\=1Ttln⁡(FtSt)d\_t = \\frac{1}{T\_t} \\ln\\left(\\frac{F\_t}{S\_t}\\right)dt​\=Tt​1​ln(St​Ft​​)

where FtF\_tFt​​ is the concurrent futures price, StS\_tSt​​ is the spot index value, and TtT\_tTt​​ is the time to futures settlement in years. The net discount rate d\=r−qd = r-qd\=r−q implicitly captures the prevailing interest rate rrr and forward dividend yield qqq without requiring either to be specified independently.

The relayer maintains a continuous-time exponentially weighted moving average of dtd\_tdt​ with a time constant τ\=1\\tau = 1τ\=1 hour:

dˉt\=βt,dˉt−+(1−βt)dt,βt\=e−Δt/τ\\bar{d}\_t = \\beta\_t, \\bar{d}\_{t^-} + (1 - \\beta\_t) d\_t, \\qquad \\beta\_t = e^{-\\Delta t / \\tau}dˉt​\=βt​,dˉt−​+(1−βt​)dt​,βt​\=e−Δt/τ

where Δt\=t−tprev\\Delta t = t - t\_{\\text{prev}}Δt\=t−tprev​​ is the elapsed time since the prior update. As a protective measure, each EMA update is clamped such that ∣dˉt−dˉt−∣≤0.01 bps|\\bar{d}\_t - \\bar{d}\_{t^-}| \\leq 0.01\\text{ bps}∣dˉt​−dˉt−​∣≤0.01 bps, ensuring no single observation produces a disproportionate rate adjustment.

#### 

Extended Session

Outside the cash session — but within futures trading hours — the oracle price is derived by discounting the futures price at the prevailing EMA discount rate:

St\=Fte−dˉtTtS\_t = F\_t e^{-\\bar{d}\_t T\_t}St​\=Ft​e−dˉt​Tt​

The EMA rate established during the prior cash session carries forward unchanged until the next cash session opens, at which point the EMA resumes updating with live basis observations.

#### 

Parameters

- Discount Rate EMA Time Constant (τ)(\\tau)(τ) : 1 hour
 
- Discount Rate EMA Clamp: 0.01 bps per update
 

Underlying Suffix

Active Until (applies to both SP500 and XYZ100)

H6

`2026-03-16T14:00:00 UTC`

M6

`2026-06-15T14:00:00 UTC`

U6

`2026-09-14T14:00:00 UTC`

Z6

`2026-12-14T15:00:00 UTC`

[PreviousCommodities](https://docs.trade.xyz/asset-directory/commodities) [NextUS](https://docs.trade.xyz/asset-directory/equity-indices/us)

Last updated 15 days ago

Was this helpful?