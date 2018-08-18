# Block Size, Block Speed and Transaction Size

There are three different variables that affect the current throughput in transactions per second \(tps\) processed by the current network:

1. Size of Block
2. Time for block confirmation \(aka Block time or Block Speed\)
3. Size of transaction

The current formula for Bitcoin throughput in _tps_ is the following:

![Screen Shot 2018-01-09 at 11.22.25 AM](/Users/federico/Projects/index-of-knowledge/assets/Screen Shot 2018-01-09 at 11.22.25 AM.png)

## 1. Increasing Block Size

While increasing the block size is one of the solutions for on-chain scalability, has certain pros and cons:

###### Pros

* Fit more transactions in a single block
* Reduced transaction fees - there is no much competition for space
* Easy implementation
* Increased throughput \(although linear\)
* Proposed by Satoshi Nakamoto himself \(themselves?\)

###### Cons

* Centralization - as block sizes grow, running a full node becomes more expensive in terms of memory, bandwidth and processing power
* Larger blocks take longer to propagate and longer to validate 
* Lead to a greater advantage for the authoring miner at also finding the next block
* More beneficial for large miners
* May cause network split due to hard fork
* One time fix - what if blocks reach capacity once more? Slippery slope
* May not be necessary due to alternatives

## 2. Increasing Block Speed \(reducing confirmation time\)

###### Pros

* “Easy” implementation as well, as simple as changing average block difficulty
* No loss of long-term security despite faster block times in context of double spends

###### Cons

* Requires better bandwidth to keep up with network and storage space to keep up with faster blockchain growth
* Larger miners enjoy higher mining efficiency → centralization risk
* Propagation time/block time ratio increases → More frequent forks \(orphaned blocks\)
* Orphaned block: a valid block propagated but not contained within the longest chain
* High orphan rates lowers the effective hash power percentage of the network → decrease the security of a network \(a malicious actor now needs less hash power to pull a “51% attack”\)

## 3. Decrease Tx Size

###### Pros

* Doesn’t require extra bandwidth or storage space -- increases transactions/block without excess load
* Difficult to disagree with morally or philosophically -- just requires optimizing data in transactions

###### Cons

* Not easy to do -- what can be cut out?
* One time fix -- can’t do again
* Small amount, is it even worthwhile?
* Hard fork? Soft fork? Depends on implementation



