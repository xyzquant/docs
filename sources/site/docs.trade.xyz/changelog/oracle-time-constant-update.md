# Source: https://docs.trade.xyz/changelog/oracle-time-constant-update

For the complete documentation index, see [llms.txt](https://docs.trade.xyz/llms.txt). This page is also available as [Markdown](https://docs.trade.xyz/changelog/oracle-time-constant-update.md).

### 

_April 30, 2026 - Oracle Time Constant Update_

We reduced the internal oracle time constant from 1 hour to 30 minutes for equity perpetuals.

### 

_November 21, 2025 - Oracle Time Constant Update_

We reduced the internal oracle time constant from 8 hours to 1 hour for equity perpetuals.

Effect in Practice

- Faster reflection of price discovery - during closed sessions, the oracle now tracks orderflow with a shorter time constant, reducing the gap between “traded price” and oracle.
 
- Lower funding drag on genuine moves - traders who are directionally right on gap moves keep more of the move (87% vs 10%); shorts who sit through those gaps receive much less funding compensation.
 
- Same safety properties - the 1 / max\_leverage band on mark vs last external spot still limits single-tick jumps and weekend bands in mark.
 

![](https://docs.trade.xyz/~gitbook/image?url=https%3A%2F%2F3922315282-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F5p3wcpw1W9gDfXen988X%252Fuploads%252FmaI9dQu6WRkt3brrB139%252Fimage.png%3Falt%3Dmedia%26token%3Dce7ad75d-3e01-4386-95ce-de503b99517d&width=768&dpr=3&quality=100&sign=f9dfc806&sv=2)

[PreviousDiscovery Bounds v2](https://docs.trade.xyz/changelog/discovery-bounds-v2) [NextFunding Rate Formula Update](https://docs.trade.xyz/changelog/funding-rate-formula-update)

Last updated 2 months ago

Was this helpful?