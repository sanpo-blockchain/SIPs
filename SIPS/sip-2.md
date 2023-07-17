|SIP|Title|Status|Type|Category|Author|Created|
|--:|:--:|:--:|:--:|:--:|:--|:--:|
|2| Sanpō Strage | Living | Standard |Extension|Koji Machi(https://t.me/kojimachi)|2023-7-17|

Describe the purpose, background, and specifications of Public Storage.


# Purpose and background
Public storage is decentralized file storage.
Blockchain is an excellent method for recording transaction data without tampering, but it is not suitable for writing large-size media data.
Therefore, it is common to build a separate distributed storage such as IPFS outside the blockchain and link blockchain transactions and media data with media IDs.
However, this method does not sufficiently ensure the persistence of media data, so many NFT projects use file storage provided by distributed storage projects such as Filecoin and Arweave separately from the blockchain.
Sanpō is a blockchain project focused on the content business, and ensuring the permanence of media data is a very important element in the content business.
Therefore, the Sanpō project decided to provide a distributed storage service that can store content data persistently without relying on external distributed storage project support.


# Outline
## Content data is stored in Distributed public storage
- Check the latest list of public storage operators registered on the blockchain and request storage of eligible operators to store data.
- Data storage performers are selected from among eligible operators in a round-robin fashion on a case-by-case basis.
- Data to be saved (moving images, images, audio) is subjected to a virus check, encrypted and saved in the storage. (Encryption prevents unauthorized access)|


## Register data storage history in blockchain
- Meta information (storage ID, storage capacity, data type, file name, success or failure of saving) of content data saved in public storage is registered in the blockchain.


## Grant SPT to storage operator
- Sanpō Token(SPT) is given to the storage operator according to the amount of data stored.


## Update storage operator information
- Update public storage operator list and register on blockchain.
- Conduct a review vote on the amount of compensation for the storage operator.

