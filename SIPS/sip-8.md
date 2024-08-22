  |SIP|Title|Status|Type|Category|Author|Created|
  |--:|:--:|:--:|:--:|:--:|:--|:--:|
  |8|Change the timeout value of go-ethereum(geth)'s call|Final|Standard|Core|Yutaka Otake(@YErikOhtake)|2023-10-16|

# Simple Summary
Change the timeout value of geth function call from the default of 5 seconds to 30 seconds.

# Abstract
The default timeout for geth function call is 5 seconds.

When using a smart contract that may handle a large amount of data, such as a [Content-NFT](https://github.com/sanpo-blockchain/Content-NFT/), the search process may take time and may not return a response in 5 seconds.

Considering such cases, extend to 30 seconds and monitor progress.

# Implementation
## go-ethereum 1.10.9 or lower
- The timeout value is described in the source code, so modify the program and build the binary.
- Source code to modify
  
  geth/go-ethereum/internal/ethapi/api.go 933:

  before

  ```  result, err := DoCall(ctx, s.b, args, blockNrOrHash, accounts, vm.Config{}, 5*time.Second, s.b.RPCGasCap())```

  after

  ```  result, err := DoCall(ctx, s.b, args, blockNrOrHash, accounts, vm.Config{}, 30*time.Second, s.b.RPCGasCap())```

- GETH node 1.10.9 or lower requires complicated procedures, and mixing multiple versions is undesirable from an operational standpoint, so the policy is to **upgrade to 1.10.10 or higher**.

## go-ethereum 1.10.10 or higher
- Add the timeout setting to go-ethereum startup options.
  
  ```--rpc.evmtimeout 30s```

# Response status
(2023/11/30)
- We asked the node operators to respond this SIP.

(2023/12/28)
- Of the two nodes to be upgraded, one node (hakuhodo) has already been upgraded. The other node (singulanet-corridor) will be upgraded over the year-end and New Year holidays.
- Nodes that have not yet been done should be completed by the end of January 2024.
