# Claim AGL

Every Agile user accrues AGL for each block they are supplying to or borrowing from the protocol. Users may call the Comptroller's `claimAgile` method at any time to transfer AGL accrued to their address.

**Comptroller**

```text
// Claim all the AGL accrued by holder in all markets
function claimAgile(address holder) public

// Claim all the AGL accrued by holder in specific markets
function claimAgile(address holder, SToken[] memory aTokens) public

// Claim all the AGL accrued by specific holders in specific markets for their supplies and/or borrows
function claimAgile(address[] memory holders, SToken[] memory aTokens, bool borrowers, bool suppliers) public
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
troll.claimAgile(0x1234...);
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);
await comptroller.methods.claimAgile("0x1234...").send({ from: sender });
```

