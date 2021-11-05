# Agile Constructor

Creates an instance of the Agile.js SDK.

* `[provider]` \(Provider \| string\) Optional Ethereum network provider. Defaults to Ethers.js fallback mainnet provider.
* `[options]` \(object\) Optional provider options.
* `RETURN` \(object\) Returns an instance of the Agile.js SDK.

```text
var agile = new Agile(window.ethereum); // web browser

var agile = new Agile('http://127.0.0.1:8545'); // HTTP provider

var agile = new Agile(); // Uses Ethers.js fallback mainnet (for testing only)

var agile = new Agile('ropsten'); // Uses Ethers.js fallback (for testing only)

// Init with private key (server side)
var agile = new Agile('https://mainnet.infura.io/v3/_your_project_id_', {
  privateKey: '0x_your_private_key_', // preferably with environment variable
});

// Init with HD mnemonic (server side)
var agile = new Agile('mainnet' {
  mnemonic: 'clutch captain shoe...', // preferably with environment variable
});
```

