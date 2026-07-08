# Source: https://docs.trade.xyz/asset-directory/stocks/korea

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/asset-directory/stocks/korea.md).

#### 

**External Coverage (**GMT+9)

For Korean Indices/Equities, the relayer sources executable quotes from institutional data providers for market open sessions.

- Pre-market Session - 8:00 AM – 8:50 AM
 
- Main Session - 9:00 AM – 3:30 PM
 
- After-hours Session - 3:40 PM – 8:00 PM
 

#### 

**Internal Coverage (GMT+9)**

- Weekdays
 
 - 8:50 AM to 9:00 AM
 
 - 3:30 PM - 3:40 PM
 
 - 8:00 PM - 8:00 AM
 
 
- Weekends
 
 - Friday 8:00 PM to Monday 8:00 AM
 
 
- Holidays - [Holiday Closures](https://docs.trade.xyz/consolidated-resources/holiday-closures)
 

Additionally, _Internal Pricing_ will be used if there is a gap of more than 30 seconds between external oracle datapoints. This ensures continuous pricing coverage across all sessions, including after-hours. You can read more about the internal pricing mechanism [here](https://docs.trade.xyz/perp-mechanics/oracle-price#internal-pricing).

#### 

**FX Conversion**

The relayer aggregates executable quotes for KRW-denominated instruments alongside real-time [USD/KRW](https://insights.pyth.network/price-feeds/FX.USD%2FKRW) FX rates. To maintain consistency with XYZ’s linear contract structure, which is margined and settled exclusively in USDC, the system automatically converts these quotes into USD pricing. This ensures a seamless trading experience and eliminates currency friction for users.

#### 

**Markets**

Instrument

Description

SKHX / USDC

SK Hynix Inc. perpetual contracts are listed under ticker $SKHX. SK Hynix Inc. provides products and services for the electronics components industries. The company manufactures semiconductors such as dynamic random access memory (DRAM), NAND flash memory, and static random access memory (SRAM) chips. The SKHX oracle price tracks the USD value of 1 common share of SK Hynix Inc. The oracle price can be replicated by dividing the KRW price of 000660 KS Equity by the USD/KRW exchange rate.

Example:

\- KRW Price of 1 common share of SK Hynix Inc. (KRX Ticker 000660): 886,000 KRW

\- USD/KRW Exchange Rate: 1,444.10 KRW/USD

SKHX Oracle = 886,000 KRW / 1,444.10 KRW/USD = $613.53 USD

SMSN / USDC

Samsung Electronics Co., Ltd. perpetual contracts are listed under the ticker $SMSN. Samsung Electronics Co., Ltd. is a global leader in consumer electronics and semiconductor manufacturing. The company produces memory chips (DRAM and NAND), logic chips, smartphones, display panels, home appliances, and other electronic components.

The SMSN oracle price tracks the USD value of 1 common share of Samsung Electronics Co., Ltd. The oracle price can be replicated by dividing the KRW price of 005930 KS Equity (Samsung Electronics common shares) by the USD/KRW exchange rate.

Example:

- KRW Price of 1 common share of Samsung Electronics (KRX Ticker 005930): 181,000 KRW
 
- USD/KRW Exchange Rate: 1,444.10 KRW/USD
 

SMSN Oracle = 181,000 KRW / 1,444.10 KRW/USD = $125.34 USD

HYUNDAI / USDC

Hyundai Motor Company perpetual contracts are listed under the ticker $HYUNDAI. Hyundai is a leading global automobile manufacturer headquartered in South Korea. Hyundai is also the majority owner of Boston Dynamics, a U.S.-based robotics company known for advanced humanoid and quadruped robots, reflecting Hyundai’s strategic expansion into robotics, automation, and next-generation mobility technologies.

The HYUNDAI oracle price tracks the USD value of 1 common share of Hyundai Motor Company.

The oracle price can be replicated by dividing the KRW price of 005380 KS Equity (Hyundai common shares) by the USD/KRW exchange rate.

Example:

- KRW Price of 1 common share of Hyundai Motor (KRX Ticker 005380): 499,000 KRW
 
- USD/KRW Exchange Rate: 1,444.10 KRW/USD
 

HYUNDAI Oracle = 499,000 KRW / 1,444.10 KRW/USD = $345.54 USD

EWY / USDC

The South Korea ETF perpetual contracts are listed under the ticker $EWY. The underlying ETF tracks the investment results of an index composed of large and mid-cap South Korean equities. No FX conversion is required at the contract level, as currency exposure (USD/KRW) is embedded within the ETF’s net asset value.

#### 

**Data Source**

See the [Specification Index](https://docs.trade.xyz/consolidated-resources/specification-index) page for pricing referencing sources.

[PreviousUS](https://docs.trade.xyz/asset-directory/stocks/us) [NextJapan](https://docs.trade.xyz/asset-directory/stocks/japan)

Last updated 2 months ago

Was this helpful?