# ATokens

Each asset supported by the Agile Protocol is integrated through a aToken contract, which is an [EIP-20](https://eips.ethereum.org/EIPS/eip-20) compliant representation of balances supplied to the protocol. By minting aTokens, users \(1\) earn interest through the aToken's exchange rate, which increases in value relative to the underlying asset, and \(2\) gain the ability to use aTokens as collateral.

aTokens are the primary means of interacting with the Agile Protocol; when a user mints, redeems, borrows, repays a borrow, liquidates a borrow, or transfers aTokens, she will do so using the aToken contract.

There are currently two types of aTokens: SErc20 and SEther. Though both types expose the EIP-20 interface, SErc20 wraps an underlying ERC-20 asset, while SEther simply wraps Ether itself. As such, the core functions which involve transferring an asset into the protocol have slightly different interfaces depending on the type, each of which is shown below.

## How do aTokens earn interest?

Each [market](https://agile.finance/markets) has its own Supply interest rate \(APR\). Interest isn't distributed; instead, simply by holding aTokens, you'll earn interest.

aTokens accumulates interest through their exchange rate — over time, each aToken becomes convertible into an increasing amount of it's underlying asset, even while the number of aTokens in your wallet stays the same.

## Can you walk me through an example?

Let’s say you supply 1,000 USDC to the Agile protocol, when the exchange rate is 0.020070; you would receive 49,825.61 aUSDC \(1,000/0.020070\).

A few months later, you decide it’s time to withdraw your USDC from the protocol; the exchange rate is now 0.021591:

* Your 49,825.61 aUSDC is now equal to 1,075.78 USDC \(49,825.61 \* 0.021591\)
* You could withdraw 1,075.78 USDC, which would redeem all 49,825.61 aUSDC
* Or, you could withdraw a portion, such as your original 1,000 USDC, which would redeem 46,315.59 aUSDC \(keeping 3,510.01 aUSDC in your wallet\)

## How do I view my aTokens?

Each aToken is visible on [Etherscan](https://etherscan.io/tokens/label/agile), and you should be able to view them in the list of tokens associated with your address

aToken balances have been integrated into [Coinbase Wallet](https://itunes.apple.com/us/app/coinbase-wallet/id1278383455) and MetaMask; other wallets may add aToken support

## Can I transfer aTokens?

Yes, but exercise caution! By transferring aTokens, you’re transferring your balance of the underlying asset inside the Agile protocol. If you send a aToken to your friend, your balance \(viewable in the [Agile Interface](https://app.agile.finance/)\) will decline, and your friend will see their balance increase.

A aToken transfer will fail if the account has [entered](../comptroller/enter-markets.md) that aToken market and the transfer would have put the account into a state of negative [liquidity](../comptroller/get-account-liquidity.md).

