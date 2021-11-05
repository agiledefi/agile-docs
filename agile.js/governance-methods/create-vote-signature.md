# Create Vote Signature

Create a vote signature for a Agile Governance proposal using EIP-712. This can be used to create an 'empty ballot' without burning gas. The signature can then be sent to someone else to post to the blockchain. The recipient can post one signature using the `castVoteBySig` method.

* `proposalId` \(string\) The ID of the proposal to vote on. This is an auto-incrementing integer in the Governor Alpha contract.
* `support` \(boolean\) A boolean of true for 'yes' or false for 'no' on the proposal vote. To create an 'empty ballot' call this method twice using true and then false for this parameter.
* `RETURN` \(object\) Returns an object that contains the `v`, `r`, and `s` components of an Ethereum signature as hexadecimal strings.

```text
const agile = new Agile(window.ethereum);

(async () => {

  const voteForSignature = await agile.createVoteSignature(20, true);
  console.log('voteForSignature', voteForSignature);

  const voteAgainstSignature = await agile.createVoteSignature(20, false);
  console.log('voteAgainstSignature', voteAgainstSignature);

})().catch(console.error);
```

