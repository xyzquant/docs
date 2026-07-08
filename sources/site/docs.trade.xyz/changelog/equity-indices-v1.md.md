# Source: https://docs.trade.xyz/changelog/equity-indices-v1.md

\> For the complete documentation index, see \[llms.txt\](https://docs.trade.xyz/llms.txt). Markdown versions of documentation pages are available by appending \`.md\` to page URLs; this page is available as \[Markdown\](https://docs.trade.xyz/changelog/equity-indices-v1.md). # Equity Indices v1 ### February 19, 2026 - Updated Index Methodology > We upgraded the oracle derivation for equity indices (applicable to XYZ100). The v2 methodology is described in the \[Equity Indices\](/asset-directory/equity-indices.md) section of the documentation; the following is an archive of the v1 oracle design with which XYZ100 was launched. #### External Coverage The Relayer derives external prices for equity indices 23/5, from Sunday 6:00 PM ET to Friday 5:00 PM ET, with daily gaps from 5:00 PM to 6:00 PM. #### External Price Derivation For equity indices such as XYZ100, the relayer consumes executable quotes for the underlying traditional (dated) equity index futures from institutional liquidity providers. This provides robust external pricing nearly 23 hours per day, five days per week, extending external coverage beyond daytime cash sessions. The futures quote is adjusted to an implied spot value which is then included as the oracle price in a relayer update to HyperCore. The conversion of external prices from futures to spot follows the cost-of-carry model (spot—futures parity): $$ S = F e^{-(r-q)T} $$ where $$S$$ is the spot (oracle) price, $$F$$ is the externally-sourced dated-futures price, $$T$$ is the time to settlement (in years), $$r$$ is the interest rate, and $$q$$ is the forward dividend yield. The discount rate $$d = (r-q)$$ takes into account the prevailing borrow rates, as well as the forward dividend yield of the underlying. The discount rate may be updated periodically in accordance with changing market conditions. #### XYZ100 The XYZ U.S. 100 Index (XYZ100) tracks the value of a modified capitalization-weighted index of 100 large non-financial companies listed on a U.S. exchange. \*\*Parameters\*\* \* Discount Rate ( $$r-q$$): 4% \* Primary Datasource:

| Underlying Suffix | Active Until | Expiration |
| --- | --- | --- |
| H6 | 
```
2026-03-15T22:00:00Z
```

 | 

```
2026-03-20T13:30:00Z
```

 |
| M6 | 

```
2026-06-14T22:00:00Z
```

 | 

```
2026-06-19T13:30:00Z
```

 |
| U6 | 

```
2026-09-13T22:00:00Z
```

 | 

```
2026-09-18T13:30:00Z
```

 |
| Z6 | 

```
2026-12-13T22:00:00Z
```

 | 

```
2026-12-18T13:30:00Z
```

 |

\#### Example: Deriving Oracle Price for XYZ100 It is important for market participants to be able to independently replicate and verify oracle prices. Below, we walk through an example of deriving the external oracle (spot) price of XYZ100. From the equity index calendar, we see that the active contract suffix is Z5, with an expiration time \`2025-12-19 13:30:00 UTC\`. The Pyth NMZ5 feed is reporting a price of \`$24,904.2\` at the current time, \`2025-10-14 17:06:05 UTC\`. The time to expiry is \`0.180285473\` years. At the time of writing, the discount rate $$r-q=4.0%$$. Plugging in the following values into our equation. \* $$F = 24904.2$$ \* $$r-q = 0.04$$ \* $$T = 0.180285473$$ We calculate $$S = 24725.25$$ Thus, we've derived the spot price to be $24,725.25 
\--- # Agent Instructions This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com. ## Querying This Documentation If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question. Perform an HTTP GET request on the current page URL with the \`ask\` query parameter, and the optional \`goal\` query parameter: \`\`\` GET https://docs.trade.xyz/changelog/equity-indices-v1.md?ask=&goal= \`\`\` \`ask\` is the immediate question: it should be specific, self-contained, and written in natural language. \`goal\` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal. The response will contain a direct answer to the question and relevant excerpts and sources from the documentation. Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.