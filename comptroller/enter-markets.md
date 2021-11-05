# Enter Markets

Enter into a list of markets - it is not an error to enter the same market more than once. In order to supply collateral or borrow in a market, it must be entered first.

**Comptroller**

```text
function enterMarkets(address[] calldata aTokens) returns (uint[] memory)
```

* `msg.sender`: The account which shall enter the given markets.
* `aTokens`: The addresses of the aToken markets to enter.
* `RETURN`: For each market, returns an error code indicating whether or not it was entered. Each is 0 on success, otherwise an [Error code](error-codes.md).

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
SToken[] memory aTokens = new SToken[](2);
aTokens[0] = SErc20(0x3FDA...);
aTokens[1] = SEther(0x3FDB...);
uint[] memory errors = troll.enterMarkets(aTokens);
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const aTokens = [SErc20.at(0x3FDA...), SEther.at(0x3FDB...)];
const errors = await troll.methods.enterMarkets(aTokens).send({from: ...});
```

