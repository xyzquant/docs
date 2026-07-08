# Source: https://docs.trade.xyz/asset-directory/stocks/hong-kong

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/asset-directory/stocks/hong-kong.md).

#### 

**External Coverage**

For Hong Kong-listed equities, the Relayer derives external prices during market open trading sessions (HKT / UTC+8):

- **Morning Session:** 9:30 AM – 12:00 PM HKT
 
- **Afternoon Session:** 1:00 PM – 4:00 PM HKT
 

#### 

**Internal Pricing**

Internal pricing applies outside of the market open sessions, including:

- **Lunch Break:** 12:00 PM – 1:00 PM HKT
 
- **Market Closed:** 4:00 PM – 9:30 AM HKT
 
- **Weekends and** [**exchange holidays**](https://docs.trade.xyz/consolidated-resources/holiday-closures)
 

#### 

**FX Conversion**

The relayer aggregates executable quotes for HKD-denominated instruments alongside real-time [USD/HKD](https://app.pyth.com/explore/FX.USD%2FHKD) FX rates. To maintain consistency with XYZ’s linear contract structure, which is margined and settled exclusively in USDC, the system automatically converts these quotes into USD pricing. This ensures a seamless trading experience and eliminates currency friction for users.

#### 

**Data Source**

See the [Specification Index](https://docs.trade.xyz/consolidated-resources/specification-index) page for pricing referencing sources.

[PreviousJapan](https://docs.trade.xyz/asset-directory/stocks/japan) [NextCommodities](https://docs.trade.xyz/asset-directory/commodities)

Last updated 20 days ago

Was this helpful?