  |SIP|Title|Status|Type|Category|Author|Created|
  |--:|:--:|:--:|:--:|:--:|:--|:--:|
  |8|Change the timeout value of go-ethereum(geth)'s call|draft|Standard|Core|Yutaka Otake(@YErikOhtake)|2023-10-16|

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

## go-ethereum 1.10.10 or higher
- Add the timeout setting to go-ethereum startup options.
  
  ```--rpc.evmtimeout 30s```
