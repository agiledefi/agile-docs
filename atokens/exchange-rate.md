# Exchange Rate

Each aToken is convertible into an ever increasing quantity of the underlying asset, as interest accrues in the market. The exchange rate between a aToken and the underlying asset is equal to:

```text
exchangeRate = (getCash() + totalBorrows() - totalReserves()) / totalSupply()
```

**SErc20 / SEther**

```text
function exchangeRateCurrent() returns (uint)
```

* `RETURN`: The current exchange rate as an unsigned integer, scaled by 1e18.

**Solidity**

```text
SErc20 aToken = SToken(0x3FDA...);
uint exchangeRateMantissa = aToken.exchangeRateCurrent();
```

**Web3 1.0**

```javascript
const aToken = SEther.at(0x3FDB...);
const exchangeRate = (await aToken.methods.exchangeRateCurrent().call()) / 1e18;
```

Tip: note the use of call vs. send to invoke the function from off-chain without incurring gas costs.

