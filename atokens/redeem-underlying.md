# Redeem Underlying

The redeem underlying function converts aTokens into a specified quantity of the underlying asset, and returns them to the user. The amount of aTokens redeemed is equal to the quantity of underlying tokens received, divided by the current [Exchange Rate](exchange-rate.md). The amount redeemed must be less than the user's [Account Liquidity](https://github.com/agilefinance/agile-docs/tree/294e07fcebce7997c93709b5b9f8bbdb7e8271af/atokens/comptroller/get-account-liquidity.md) and the market's available liquidity.

**SErc20 / SEther**

```text
function redeemUnderlying(uint redeemAmount) returns (uint)
```

* `msg.sender`: The account to which redeemed funds shall be transferred.
* `redeemAmount`: The amount of underlying to be redeemed.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

**Solidity**

```text
SEther aToken = SEther(0x3FDB...);
require(aToken.redeemUnderlying(50) == 0, "something went wrong");
```

**Web3 1.0**

```javascript
const aToken = SErc20.at(0x3FDA...);
aToken.methods.redeemUnderlying(10).send({from: ...});
```

