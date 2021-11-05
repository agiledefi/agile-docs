# Get Price

Gets an asset's price from the Agile Protocol open price feed. The price of the asset can be returned in any other supported asset value, including all aTokens and underlyings.

* `asset` \(string\) A string of a supported asset in which to find the current price.
* `[inAsset]` \(string\) A string of a supported asset in which to express the `asset` parameter's price. This defaults to USD.
* `RETURN` \(string\) Returns a string of the numeric value of the asset.

```text
const agile = new Agile(window.ethereum);
let price;

(async function () {

  price = await agile.getPrice(Agile.WBTC);
  console.log('WBTC in USD', price); // 6 decimals, see Open Price Feed docs

  price = await agile.getPrice(Agile.ETH, Agile.USDC); // supports aTokens too
  console.log('ETH in USDC', price);

})().catch(console.error);
```

