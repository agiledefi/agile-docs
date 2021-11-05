# Get AGL Accrued

Get the amount of AGL tokens accrued but not yet claimed by an address.

* `_address` \(string\) The address in which to find the AGL accrued.
* `[_provider]` \(Provider \| string\) An Ethers.js provider or valid network name string.
* `RETURN` \(string\) Returns a string of the numeric accruement of AGL. The value is scaled up by 18 decimal places.

```text
(async function () {
  const acc = await Agile.agile.getAgileAccrued('0x4Ddc2D193948926D02f9B1fE9e1daa0718270ED5');
  console.log('Accrued', acc);
})().catch(console.error);
```

