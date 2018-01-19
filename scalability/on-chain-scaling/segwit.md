### Segregated Witnesses

Segregated Witnesses \(Segwit\) aim to reduce transaction sizes by cleverly combining or pruning the transaction signatures, this produces a greater throughput and lower storage requirements. 

![](/assets/Screen Shot 2018-01-09 at 12.01.36 PM.png)

In a technical perspective, it aims to move script signatures out of transactions into a separate structure.  Signatures are hundreds of bytes in data and take ~60% of the transaction size. 

![](https://lh5.googleusercontent.com/GevIHuNXyJ7STIcVjA4FP0_eiQw14zJu60rZOO9nD_awmGj3by_yc4lfiox3mKdjab5TaSyXsfidoTWd9HtwMil22l59GLOOLhTuWA1e9CsGrAicAeKYI-htETpjSp3JdptY9lgP)

txids of each transaction in a block are hashed into a binary merkle tree, the root of which is included in the block header. If the TXID doesn’t include the signature data, the blockchain now has no evidence that the correct signatures were included in each transaction. The potential solution for this is a SegWit-enabled miner that creates an additional merkle tree of WTXIDs, which include the witness data. The root of this merkle tree will be included in the coinbase transaction of the block, so if the signatures data stored in the merkle tree changes, the root is modified and therefore the txid of the coinbase transaction changes and the block header is then invalid, affecting the whole blockchain.

 The SegWit proposal defines a new type of maximum block size in terms of block weight, which by requirement needs to satisfy block weight ≤ 4,000,000 bytes:

**base size**: block size in bytes with the original transaction serialization without any witness-related data, as seen by a non-upgraded node.

**total size**:  block size in bytes with transactions serialized as described in BIP144, including base data and witness data.

block weight = base size \* 3 + transaction size

With this new set of rules, the expected block size is 2.1MB, although SegWit nodes can have a potential effective block size increase up to 4MB, without increasing the block-size limit itself. Thus, SegWit blocks seem smaller in terms of base size than the pre-SegWit nodes, and since signatures do not affect the UTXOs, they can be eventually removed from the blockchain after a long period post-confirmation, reducing the size of the overall blockchain. 

Old nodes won’t see the new fields, and will see the scriptPubKey data as meaningless text, or “anyone-can-spend”. It’s neither invalid nor their money, so they will still include these transactions. $$x = y$$ 

One of the most common arguments against segwit is that it incentivizes validationless mining.



