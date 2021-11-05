# Borrow Rate

At any point in time one may query the contract to get the current borrow rate per block.

**SErc20 / SEther**

```text
function borrowRatePerBlock() returns (uint)
```

* `RETURN`: The current borrow rate as an unsigned integer, scaled by 1e18.

**Solidity**

```text
SErc20 aToken = SToken(0x3FDA...);
uint borrowRateMantissa = aToken.borrowRatePerBlock();
```

**Web3 1.0**

```javascript
const aToken = SEther.at(0x3FDB...);
const borrowRate = (await aToken.methods.borrowRatePerBlock().call()) / 1e18;
```

