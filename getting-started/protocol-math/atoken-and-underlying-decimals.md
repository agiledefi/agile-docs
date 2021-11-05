# aToken and Underlying Decimals

Prices and exchange rates are scaled by the decimals unique to each asset; aTokens are ERC-20 tokens with 8 decimals, while their underlying tokens vary, and have a public member named _decimals_.

| aToken | aToken Decimals | Underlying | Underlying Decimals |
| :--- | :--- | :--- | :--- |
| aBNB | 8 | ETH | 18 |
| aUSDC | 8 | USDC | 6 |
| aUSDT | 8 | USDT | 6 |
| aBUSD | 8 | BUSD | 18 |
| sLINK | 8 | LINK | 18 |
| sUNI | 8 | UNI | 18 |
| aCOMP | 8 | COMP | 18 |
| sWBTC | 8 | WBTC | 8 |
| sAGL | 8 | AGL | 18 |

