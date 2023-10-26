  |SIP|Title|Status|Type|Category|Author|Created|
  |--:|:--:|:--:|:--:|:--:|:--|:--:|
  |5|Increase the value of gasLimit|Draft|Standard|Core|Yutaka Otake(@YErikOhtake)|2023-10-05|

# Simple Summary
Increase the processing performance of the sanpo blockchain by increasing the gas limit of authoritative nodes.

# Abstract
Increase the gas limit of the Authority node to 600,000,000. (currently go-ethereum's default value of 30,000,000.)

# What we looked into
We used a testnet to deploy [Content-NFT](https://github.com/sanpo-blockchain/Content-NFT/) smart contract to investigate the number of transactions stored in the block and block size due to changes in gasLimit by issuing a large number of transactions.

- Number of nodes and server specs
  - Authority 7
    
    Node issuing transaction: CPU 32core, Memory 64GB

    Other nodes: CPU 2core, Memory 8GB
  - Corridor 1
    
    CPU 2core, Memory 8GB

- block generation interval
  - 2 seconds 

- Transaction data size
  - 560 Byte

The following results were obtained.

## gasLimit: 30,000,000(default) 
- Number of transactions in one block

  Average. 73 transactions.
  
- Data size of one block

  Average. 41KB.

## gasLimit: 300,000,000
- Number of transactions in one block

  Average. 849 transactions.

- Data size of one block

  Average. 474KB.

# The following is an estimate from the results.

## gasLimit: 600,000,000

- Number of transactions in one block

  Approx. 1600 transactions.

- Data size of one block

  Approx. 900KB.

  A maximum of 900 KB of block-synchronous data communication occurs.
  Authority nodes also perform non-block-synchronous communications, but we do not believe this data size is large enough to affect these communications. However, if the data size is larger than this, we believe that an impact could occur.

  note: We are planning to conduct a survey with this gasLimit.  
  
# Implementation
- Add the gaslimit setting to go-ethereum startup options.
  
  ```--miner.gaslimit 600000000```
