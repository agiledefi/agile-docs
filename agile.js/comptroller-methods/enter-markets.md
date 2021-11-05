# Enter Markets

Enters the user's address into Agile Protocol markets.

* `markets` \(any\[\]\) An array of strings of markets to enter, meaning use those supplied assets as collateral.
* `[options]` \(CallOptions\) Call options and Ethers.js overrides for the transaction. A passed `gasLimit` will be used in both the `approve` \(if not supressed\) and `mint` transactions.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the enterMarkets transaction.

```text
const agile = new Agile(window.ethereum);

(async function () {
  const trx = await agile.enterMarkets(Agile.ETH); // Use [] for multiple
  console.log('Ethers.js transaction object', trx);
})().catch(console.error);
```

