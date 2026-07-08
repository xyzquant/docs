# Source: https://docs.trade.xyz/asset-directory/stocks/japan

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/asset-directory/stocks/japan.md).

#### 

**External Coverage**

For Japan-listed equities, the Relayer derives external prices during market open trading sessions (JST, UTC+9):

- **Morning Session:** 8:20 AM – 4:30 PM JST
 
- **Afternoon Session:** 5:00 PM – 11:59 PM JST
 

#### 

**Internal Pricing**

Internal pricing applies outside of the market open sessions, including:

- **Afternoon Break:** 4:30 PM – 5:00 PM JST
 
- **Market Closed:** 11:59 PM – 8:20 AM JST
 
- **Weekends and** [**Exchange Holidays**](https://www.jpx.co.jp/english/corporate/about-jpx/calendar/)
 

#### 

**FX Conversion**

The relayer aggregates executable quotes for JPY-denominated instruments alongside real-time [USD/JPY](https://app.pyth.com/explore/FX.Index.USD%2FJPY) FX rates. To maintain consistency with XYZ’s linear contract structure, which is margined and settled exclusively in USDC, the system automatically converts these quotes into USD pricing. This ensures a seamless trading experience and eliminates currency friction for users.

#### 

**Data Source**

See the [Specification Index](https://docs.trade.xyz/consolidated-resources/specification-index) page for pricing referencing sources.

[PreviousKorea](https://docs.trade.xyz/asset-directory/stocks/korea) [NextHong Kong](https://docs.trade.xyz/asset-directory/stocks/hong-kong)

Last updated 13 days ago

Was this helpful?