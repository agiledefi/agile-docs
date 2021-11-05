# Claim AGL

Create a transaction to claim accrued AGL tokens for the user.

* `[options]` \(CallOptions\) Options to set for a transaction and Ethers.js method overrides.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the vote transaction.

```text
const agile = new Agile(window.ethereum);

(async function() {

  console.log('Claiming AGL...');
  const trx = await compound.claimAgile();
  console.log('Ethers.js transaction object', trx);

})().catch(console.error);
```

