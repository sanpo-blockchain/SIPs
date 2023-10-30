  |SIP|Title|Status|Type|Category|Author|Created|
  |--:|:--:|:--:|:--:|:--:|:--|:--:|
  |9|Improved performance of Content-NFT search processing|Review|Standard|Application|Yutaka Otake(@YErikOhtake)|2023-10-16|

# Simple Summary
Improved performance of [Content-NFT](https://github.com/sanpo-blockchain/Content-NFT/) search processing

# Abstract
In Content-NFT, when an NFT is issued, the information is stored in an array.

Suppose that one million NFTs are issued.
If you want to see the NFTs that you own, you need to check the holders of the NFTs in order from the top of the array, so you need to check a maximum of 1 million NFTs.

This would be a time-consuming process.

We would like to implement a fast search mechanism and would like to discuss this mechanism.

## reference
We used to test services for business requirements issuing hundreds of thousands of NFTs in a Testnet environment.

There were times when searches took 7 to 9 seconds in an environment that issued approximately 500,000 NFTs.
