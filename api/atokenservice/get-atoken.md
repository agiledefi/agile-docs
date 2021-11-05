# GET: /atoken

**ATokenRequest**

The request to the aToken API can specify a number filters, such as which tokens to retrieve information about or moment in time. The following shows an example set of request parameters in JSON:

```text
{
  "addresses": [] // returns all tokens if empty or not included
}
```

| Type | Key | Description |
| :--- | :--- | :--- |
| bytes | `addresses` | List of token addresses to filter on, e.g.: \["0x...", ,"0x..."\] |

**ATokenResponse**

The aToken API returns an overall picture of aTokens matching the filter.

```text
{
    status: true,
    data: {
        agileRate: "118900000000000000",
        dailyAgile: "1369728000000000000000",
        markets: [
            {
            address: "0x405bfbd29cfad8cd5513de848064e96fd3db890b",
            symbol: "aBNB",
            name: "aBNB",
            underlyingAddress: null,
            underlyingName: "ETH",
            underlyingSymbol: "ETH",
            agileSpeeds: "0",
            borrowerDailyAgile: "0",
            supplierDailyAgile: "0",
            agileBorrowIndex: "1000000000000000000000000000000000000",
            agileSupplyIndex: "1000000000000000000000000000000000000",
            borrowRatePerBlock: "23782343987",
            supplyRatePerBlock: "0",
            exchangeRate: "200000000000000000000000000",
            underlyingPrice: "1190005700000000000000",
            totalBorrows: "0",
            totalBorrows2: "0",
            totalBorrowsUsd: "0",
            totalSupply: "0",
            totalSupply2: "0",
            totalSupplyUsd: "0",
            cash: "0",
            totalReserves: "0",
            reserveFactor: "0",
            collateralFactor: "500000000000000000",
            borrowApy: "5.112350694414863249",
            supplyApy: "0",
            borrowAgileApy: "0",
            supplyAgileApy: "0",
            liquidity: "0",
            tokenPrice: "1190.0057",
            totalDistributed: "0",
            totalDistributed2: "0",
            lastCalculatedBlockNumber: 9605249,
            borrowerCount: 0,
            supplierCount: 0,
            marketVolumeLog: {
                id: "8f0935bb-048b-4420-a37b-74890b8a8483",
                address: "0x405bfbd29cfad8cd5513de848064e96fd3db890b",
                totalSupplyUsd: "0",
                totalBorrowsUsd: "0",
                totalSupplyUsd24h: "0",
                totalBorrowsUsd24h: "0",
                blockNumber: 9605193,
                createdAt: "2021-02-05T12:00:00.000Z",
                updatedAt: "2021-02-05T12:00:00.000Z"
                }
            }
        ],
        request: {
            addresses: [
                "0x405bfbd29cfad8cd5513de848064e96fd3db890b"
            ]
        },
        marketVolumeLog: {
            id: "b29cd0f2-4c24-4fe4-b03b-92d422ba0f62",
            address: null,
            totalSupplyUsd: "0",
            totalBorrowsUsd: "0",
            totalSupplyUsd24h: "0",
            totalBorrowsUsd24h: "0",
            blockNumber: 9605193,
            createdAt: "2021-02-05T12:00:00.000Z",
            updatedAt: "2021-02-05T12:00:00.000Z"
        },
        borrowerCount: 0,
        supplierCount: 0
    }
}
```

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| STokenResponseData | `data` | The result matching the requested filter. |

**STokenResponseData**

| Type | Key | Description |
| :--- | :--- | :--- |
| string | `agileRate` | Agile speed per block |
| string | `dailyAgile` | Daily agile distribution amount |
| uint32 | `borrowerCount` | Borrower count |
| uint32 | `supplierCount` | Supplier count |
| STokenRequest | `request` | The request parameters are echoed in the response |
| MarketVolumeData | `marketVolumeLog` | Market volume data |
| Market | `markets` | The list of market\(see Market below\) matching the requested filter. |

**Market**

This includes a list of aTokens contextualized to the full market.

| Type | Key | Description |
| :--- | :--- | :--- |
| bytes | `address` | The public Ethereum address of the aToken |
| string | `symbol` | The symbol of the atoken |
| string | `name` | The name of the atoken |
| bytes | `underlyingAddress` | The address of the underlying token |
| string | `underlyingName` | The name of the underlying token |
| string | `underlyingSymbol` | The symbol of the underlying token |
| string | `agileSpeeds` | Agile speed per block |
| string | `borrowerDailyAgile` | Borrower daily agile |
| string | `supplierDailyAgile` | Supplier daily agile |
| string | `agileBorrowIndex` | Agile borrow index |
| string | `agileSupplyIndex` | Agile supply index |
| string | `borrowRatePerBlock` | The floating borrow interest rate |
| string | `supplyRatePerBlock` | The floating supply interest rate |
| string | `exchangeRate` | The aToken / underlying exchange rate. This rate increases over time as supply interest accrues. |
| string | `underlyingPrice` | The price of the underlying token in eth |
| string | `totalBorrows` | The amount of underlying tokens borrowed from the aToken |
| string | `totalBorrows2` | The amount of underlying tokens borrowed from the aToken handled by decimals |
| string | `totalBorrowsUsd` | The USD amount of underlying tokens borrowed from the aToken |
| string | `totalSupply` | The number of aTokens in existence |
| string | `totalSupply2` | The number of aTokens in existence handled by decimals |
| string | `totalSupplyUsd` | The USD amount of aTokens in existence |
| string | `cash` | The current liquidity of the aToken |
| string | `totalBookings` | Total bookings |
| string | `reserveFactor` | Reserve factor |
| string | `collateralFactor` | The amount of the value of the underlying token that will count as collateral. eg. cEth with collataral factor 0.75 means 1 eth of supply allows 0.75 eth of borrowing. |
| string | `borrowApy` | Borrow apy |
| string | `supplyApy` | Supply apy |
| string | `borrowAgileApy` | The floating agl apy for borrowing this token |
| string | `supplyAgileApy` | The floating agl apy for supplying this token |
| string | `liquidity` | liquidity amount |
| string | `tokenPrice` | aToken price |
| string | `totalDistributed` | Total distributed agl amount |
| string | `totalDistributed2` | Total distributed agl amount handled by decimals |
| uint32 | `lastCalculatedBlockNumber` | Last block number to update market data |
| uint32 | `borrowerCount` | The number of accounts with outstanding borrows |
| uint32 | `supplierCount` | The number of accounts holding this aToken |
| MarketVolumeData | `marketVolumeLog` | Market volume data |

**MarketVolumeData**

| Type | Key | Description |
| :--- | :--- | :--- |
| uuid | `id` | Unique id of MarketVolumeData |
| bytes | `address` | The public Ethereum address of the aToken |
| string | `totalSupplyUsd` | Total supply USD |
| string | `totalSupplyUsd24h` | 24hr change of total supply USD |
| string | `totalBorrowsUsd24h` | 24hr change of total borrow USD |
| uint32 | `blockNumber` | Last calculated block number |
| datetime | `createdAt` | Created timestamp |
| datetime | `updatedAt` | Updated timestamp |

