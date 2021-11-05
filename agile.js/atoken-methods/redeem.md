# Redeem

Redeems the user's Ethereum asset from the Agile Protocol.

* `asset` \(string\) A string of the asset to redeem, or its aToken name.
* `amount` \(number \| string \| BigNumber\) A string, number, or BigNumber object of the amount of an asset to redeem. Use the `mantissa` boolean in the `options` parameter to indicate if this value is scaled up \(so there are no decimals\) or in its natural scale. This can be an amount of aTokens or underlying asset \(use the `asset` parameter to specify\).
* `[options]` \(CallOptions\) Call options and Ethers.js overrides for the transaction.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the redeem transaction.

```text
const agile = new Agile(window.ethereum);

(async function() {

  console.log('Redeeming ETH...');
  const trx = await agile.redeem(Agile.ETH, 1); // also accepts aToken args
  console.log('Ethers.js transaction object', trx);

})().catch(console.error);
```

