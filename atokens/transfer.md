# Transfer

Transfer is an ERC-20 method that allows accounts to send tokens to other Ethereum addresses. A aToken transfer will fail if the account has [entered](../comptroller/enter-markets.md) that aToken market and the transfer would have put the account into a state of negative [liquidity](../comptroller/get-account-liquidity.md).

**SErc20 / SEther**

```text
function transfer(address recipient, uint256 amount) returns (bool)
```

* `recipient`: The transfer recipient address.
* `amount`: The amount of aTokens to transfer.
* `RETURN`: Returns a boolean value indicating whether or not the operation succeeded.

**Solidity**

```text
SEther aToken = SEther(0x3FDB...);
aToken.transfer(0xABCD..., 100000000000);
```

**Web3 1.0**

```javascript
const aToken = SErc20.at(0x3FDA...);
await aToken.methods.transfer(0xABCD..., 100000000000).send({from: 0xSender});
```

