### Segregated Witnesses





Segregated Witnesses \(Segwit\) aims to move script signatures out of transactions into a separate structure.  

◼ Signatures are hundreds of bytes in data and take ~60% of the transaction size.

◼ txids of each transaction in a block are hashed into a binary merkle tree, the root of which is included in the block header.

