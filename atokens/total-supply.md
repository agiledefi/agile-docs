# Total Supply

Total Supply is the number of tokens currently in circulation in this aToken market. It is part of the EIP-20 interface of the aToken contract.

**SErc20 / SEther**

```text
function totalSupply() returns (uint)
```

* `RETURN`: The total number of tokens in circulation for the market.

**Solidity**

```text
SErc20 aToken = SToken(0x3FDA...);
uint tokens = aToken.totalSupply();
```

**Web3 1.0**

```javascript
const aToken = SEther.at(0x3FDB...);
const tokens = (await aToken.methods.totalSupply().call());
```

