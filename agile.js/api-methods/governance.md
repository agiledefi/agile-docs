# Governance

Makes a request to the GovernanceService API. The Governance Service includes three endpoints to retrieve information about AGL accounts. For more details, see the Agile API documentation.

* `options` \(object\) A JavaScript object of API request parameters.
* `endpoint` \(string\) A string of the name of the corresponding governance service endpoint. Valid values are `proposals`, `voteReceipts`, or `accounts`.
* `RETURN` \(object\) Returns the HTTP response body or error.

```text
(async function() {
  const proposal = await Agile.api.governance(
    { "proposal_ids": [ 20 ] }, 'proposals'
  );

  console.log('proposal', proposal); // JavaScript Object
})().catch(console.error);
```

