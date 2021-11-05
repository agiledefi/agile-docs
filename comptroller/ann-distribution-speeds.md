# AGL Distribution Speeds

## AGL Speed

The "AGL speed" unique to each market is an unsigned integer that specifies the amount of AGL that is distributed, per block, to suppliers and borrowers in each market. This number can be changed for individual markets by calling the `_setAgileSpeed` method through a successful Agile Governance proposal.

The following is the formula for calculating the rate that AGL is distributed to each supported market.

```text
utility = aTokenTotalBorrows * assetPrice

utilityFraction = utility / sumOfAllAgiledMarketUtilities

marketAgileSpeed = agileRate * utilityFraction
```

## AGL Distributed Per Block \(All Markets\)

The Comptroller contract’s `agileRate` is an unsigned integer that indicates the rate at which the protocol distributes AGL to markets’ suppliers or borrowers, every Ethereum block. The value is the amount of AGL \(in wei\), per block, allocated for the markets. Note that not every market has AGL distributed to its participants \(see Market Metadata\).

The agileRate indicates how much AGL goes to the suppliers or borrowers, so doubling this number shows how much AGL goes to all suppliers and borrowers combined. The code examples implement reading the amount of AGL distributed, per Ethereum block, to all markets.

**Comptroller**

```text
uint public agileRate;
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);

// AGL issued per block to suppliers OR borrowers * (1 * 10 ^ 18)
uint agileRate = troll.agileRate();

// Approximate AGL issued per day to suppliers OR borrowers * (1 * 10 ^ 18)
uint agileRatePerDay = agileRate * 4 * 60 * 24;

// Approximate AGL issued per day to suppliers AND borrowers * (1 * 10 ^ 18)
uint agileRatePerDayTotal = agileRatePerDay * 2;
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);

let agileRate = await comptroller.methods.agileRate().call();
agileRate = agileRate / 1e18;

// AGL issued to suppliers OR borrowers
const agileRatePerDay = agileRate * 4 * 60 * 24;

// AGL issued to suppliers AND borrowers
const agileRatePerDayTotal = agileRatePerDay * 2;
```

## AGL Distributed Per Block \(Single Market\)

The Comptroller contract has a mapping called `agileSpeeds`. It maps aToken addresses to an integer of each market’s AGL distribution per Ethereum block. The integer indicates the rate at which the protocol distributes AGL to markets’ suppliers or borrowers. The value is the amount of AGL \(in wei\), per block, allocated for the market. Note that not every market has AGL distributed to its participants \(see Market Metadata\).

The speed indicates how much AGL goes to the suppliers or the borrowers, so doubling this number shows how much AGL goes to market suppliers and borrowers combined. The code examples implement reading the amount of AGL distributed, per Ethereum block, to a single market.

**Comptroller**

```text
mapping(address => uint) public agileSpeeds;
```

**Solidity**

```text
Comptroller troll = Comptroller(0x123...);
address aToken = 0xabc...;

// AGL issued per block to suppliers OR borrowers * (1 * 10 ^ 18)
uint agileSpeed = troll.agileSpeeds(aToken);

// Approximate AGL issued per day to suppliers OR borrowers * (1 * 10 ^ 18)
uint agileSpeedPerDay = agileSpeed * 4 * 60 * 24;

// Approximate AGL issued per day to suppliers AND borrowers * (1 * 10 ^ 18)
uint agileSpeedPerDayTotal = agileSpeedPerDay * 2;
```

**Web3 1.2.6**

```javascript
const aTokenAddress = '0xabc...';

const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);

let agileSpeed = await comptroller.methods.agileSpeeds(aTokenAddress).call();
agileSpeed = agileSpeed / 1e18;

// AGL issued to suppliers OR borrowers
const agileSpeedPerDay = agileSpeed * 4 * 60 * 24;

// AGL issued to suppliers AND borrowers
const agileSpeedPerDayTotal = agileSpeedPerDay * 2;
```

