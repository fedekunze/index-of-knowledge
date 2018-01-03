# Throughput

There are three different variables that affect the current throughput in transactions per second \(tps\) processed by the current network:

1. Size of Block
2. Time for block confirmation
3. Size of transaction

The current formula for Bitcoin throughput in tps is the following:


$$
\frac{1 MiB}{1 block} \times \frac{1 txn}{546 bytes} \times \frac{1 block}{10 min}  \approx 3.2 tps
$$


## 1. Increasing Block Size

While increasing the block size is one of the solutions for on-chain scalability, has certain pros and cons:

### Pros

* Reduced transaction fees - there is no much competition for space
* Easy implementation
* Increased throughput \(although linear\)
* Proposed by Satoshi Nakamoto \(cite\)

## Cons

* Centralization - as block sizes grow, running a full node becomes more expensive in terms of memory and bandwith
* May cause a hard fork and split the network
* One time fix. There arises the question of what if blocks reach capacity one more time?

## 2. Increasing Block Speed \(confirmation time\)

This is one of the main differences between Ethereum \(17s confirmation time\) vs Bitcoin \(10 min confirmation time\).

While this is a easy implementation as well \(you only need to change the average block difficulty\), this can create more frequent forks or orphaned blocks. Orphan blocks are valid block propagated but not included in the longest main chain. Also, it requires better bandwidth and storage space to keep up with network and blockchain growth, both of which encourage centralization in pools. \(Cite or argument\)

Nevertheless, long-term security is maintained despite faster block times in context of double spend attacks. This is not the case in the short term \(argument\).

