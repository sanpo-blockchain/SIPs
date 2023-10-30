|SIP|Title|Status|Type|Category|Author|Created|
|--:|:--:|:--:|:--:|:--:|:--|:--:|
|7|Sanpō Storage|Review|Standard|Extensions|Yutaka Otake(@YErikOhtake)|2023-10-15|

# Simple Summary
Provide distributed storage services.

# Abstract
In order to handle content in NFT, it is necessary to store media files. Media files include images, audio, and video, all of which require a certain amount of storage.

It is not impossible to store files on the blockchain. However, as the file size increases, the data size of the block also increases, resulting in a massive increase in network data traffic.

However, even if files are stored outside the blockchain, in a system where one company provides a service to store files, if that company stops providing the service, the files will be lost.

A mechanism to prevent the loss of files is needed, which can be achieved through distributed storage.

Access to media files should be based on rights information recorded in the blockchain. Therefore, distributed storage should be linked to the blockchain.


In addition, storage services should also be operated by DAOs (just like blockchain services), and an incentive mechanism for storage service providers is necessary.

# Use of Distributed Storage
Consider SPT ownership (purchase) as a contribution to the Sanpō-Network and allow a certain amount of SPT holders to use distributed storage.

The SPT balances held and the capacity available for distributed storage are shown below.
|Balance(SPT)|maxFileSize(GiB)|
|--:|--:|
|10|1|
|50|5|
|100|10|
|500|100|
|1000|500|
