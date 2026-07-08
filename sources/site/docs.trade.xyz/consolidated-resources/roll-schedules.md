# Source: https://docs.trade.xyz/consolidated-resources/roll-schedules

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/consolidated-resources/roll-schedules.md).

#### 

Roll Schedule:

The following table denotes the active contract month for markets that reference futures-based price feeds (e.g., COPPER, WTIOIL, BRENTOIL, and NATGAS), at the start of each month. The roll period is the 5th-10th business day of the month, wherein the reference contract transitions from the month-start active contract to the next active contract. Updated weightings take effect when the oracle switches back to external pricing at 6pm ET.

**Example Roll**

WTIOIL is currently referencing the Q6 contract and will roll into U6. The transition occurs as follows:

- **2026-07-08 5:30PM ET** — 80% front-month (**Q6**), 20% next-month (**U6**)
 
- **2026-07-09 5:30PM ET** — 60% front-month, 40% next-month
 
- **2026-07-10 5:30PM ET** — 40% front-month, 60% next-month
 
- **2026-07-13 5:30PM ET** — 20% front-month, 80% next-month
 
- **2026-07-14 5:30PM ET** — 0% front-month, 100% next-month (roll complete)
 

Instrument

2026-04-08 5:30PM to 2026-04-14 5:30PM ET

2026-05-07 5:30PM to 2026-05-13 5:30PM ET

2026-06-05 5:30PM to 2026-06-11 5:30PM ET

2026-07-08 5:30PM to 2026-07-14 5:30PM ET

2026-08-07 5:30PM to 2026-08-13 5:30PM ET

2026-09-08 5:30PM to 2026-09-14 5:30PM ET

2026-10-07 5:30PM to 2026-10-13 5:30PM ET

2026-11-06 5:30PM to 2026-11-12 5:30PM ET

2026-12-07 5:30PM to 2026-12-11 5:30PM ET

COPPER

`K6 to N6`

`N6`

`N6 to U6`

`U6`

`U6 to Z6`

`Z6`

`Z6`

`Z6 to H7`

`H7`

WTIOIL (CL)

`K6 to M6`

`M6 to N6`

`N6 to Q6`

`Q6 to U6`

`U6 to V6`

`V6 to X6`

`X6 to Z6`

`Z6 to F7`

`F7 to G7`

BRENTOIL

`M6 to N6`

`N6 to Q6`

`Q6 to U6`

`U6 to V6`

`V6 to X6`

`X6 to Z6`

`Z6 to F7`

`F7 to G7`

`G7 to H7`

NATGAS

`K26 to M26`

`M26 to N26`

`N26 to Q26`

`Q26 to U26`

`U26 to V26`

`V26 to X26`

`X26 to Z26`

`Z26 to F27`

`F27 to G27`

[PreviousHoliday Closures](https://docs.trade.xyz/consolidated-resources/holiday-closures) [NextMargin Modes](https://docs.trade.xyz/risk-and-margining/margin-modes)

Last updated 22 days ago

Was this helpful?