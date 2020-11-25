<div class="my-4 text-center">![Nosferatu](b://013dcdc3e700f5486e998af583659d275fe754af18f9ba8c9c060b3468eb88f0)</div>


# The Terror Of Mining Pool Centralization.

_Daniel Krawisz_

**Originally published [09 Nov 2014 at Bitcoinist.com](https://bitcoinist.com/the-centralization-of-mining-pools/).**


One of the many issues that has a lot of Bitcoiners periodically soiling their pants in fear is that of mining pool centralization. Earlier this year was a [crisis](https://bitcoinmagazine.com/articles/mining-pool-centralization-crisis-levels-1389302892) with GHash.io and in the year before was one with BTCGuild (which has announced it is going offline soon. How the mighty have fallen). Naturally, nothing came of these supposed crises other than all manner of exhibitionist hang-wringing, such as when Peter Todd [told everyone](https://www.reddit.com/r/Bitcoin/comments/281ftd/why_i_just_sold_50_of_my_bitcoins_ghashio/) he had sold half his bitcoins due to the threat.

But what about the 51% attack? What about decentralization? Bullshit. The 51% attack is a risk that arises when one party controls more than half the total hash rate on the network. However, a mining pool does not control its own hash rate. The owners of the computers on the pool control it. To say that a mining pool controls its own hashing power is like saying that a CEO is in control of a company when he is not a majority shareholder. A power which can be revoked at any sign of malfeasance is not much of a power. True, it can happen that a CEO may bully the stockholders into going along with him on projects that are not in their best interest, but this is unlikely for mining pool operators because they take on much less of a leadership role.

When a pool runs half of the network’s hash rate, it is capable of some mischief, but only in the short term. For example, GHash.io is known to have performed [Finney attacks](https://www.reddit.com/r/Bitcoin/comments/279sex/ghashio_double_spending/) against gambling sites. However, if a mining pool tried to act maliciously for very long, the miners would soon move to another pool. Unfortunately, the response to this has been to wailing and teeth gnashing about mining pool centralization rather than promoting improvements to the mining infrastructure that would have made it easier for miners to react to this sort of thing in the future.

There are valid reasons for mining pools to be big. The whole purpose of a mining pool is to reduce the variance of the mining reward to miners who own tiny fractions of the network hash rate, and large pools do a better job of this than small ones. Opposing mining pool centralization is therefore an uphill battle. There will always be a few large pools that control the overwhelming majority of the network because that is a natural consequence of the economics of mining. Instead of attempting the impossible, people should be building ways that miners can easily react to bad behavior on the part of their mining pools.

A pool that begins to mine maliciously or engages in a 51% attack is detectable, and software could be developed to allow miners to react to it automatically. For example, miners could connect to several pools at once and adjust the hashes they give to each pool in response to one that grows too large. Miners actually have good reason to connect to several pools for their own self-interest. As this [BitcoinTalk thread](https://bitcointalk.org/index.php?topic=78031.0) shows, miners can reduce their individual reward variance by mining on multiple pools at once. I only suggest this as a possibility, but the mere fact that miners could automatically react to misbehavior from pools means that the pools are not the ones with any real power.

Already some work has been done to make miners more independent from pools. In 2012, the [getblocktemplate](https://en.bitcoin.it/wiki/Getblocktemplate) protocol was developed to supersede the older getwork() protocol. This protocol gives individual miners the authority to decide which transactions go in each block. Unfortunately it is not used much yet because it requires individual miners to run full nodes and it requires more bandwidth between miner and pool to prove that the miner is contributing work to the pool.

There are other safeguards that could be become standard practices. The big pools themselves could work better to oppose one another. If one of them becomes too large (around 25% of the network—the point at which malicious mining becomes possible), then the others can ignore blocks from that pool. If some anonymous agent releases attempts to orphan several blocks in a chain, then they can ignore his new chain. All this requires is coordination.

Finally, with the right infrastructure it would be possible for Bitcoin users to choose which pool to send their transactions to. This would allow them to benefit smaller pools with extra transaction fees. This, too, could be done automatically.

Fallacies in economics often result from a failure to distinguish between things that can change easily from things that do not change easily. Typically, this leads to fears that certain trends will continue without limit or to a confusion of cause and effect. Generally speaking, the more adaptable factor is the driver of economic change and the less adaptable must react to it. A failure to identify the more adaptable factor, therefore, leads to a failure to identify which factor is the cause of the other. In Bitcoin, the owners of the hashing power are always more adaptable than the mining pools, and therefore they have the means to keep the mining pools in check.

I have argued here that mining pool centralization could be automatically opposed by miners, users, and other pools. However, if mining pool centralization was really such a terrible risk, these things would have been built already. So far, informal solutions have sufficed to remind the miners to reapportion their hashing power when one pool has become too great. If mining pool centralization actually becomes a serious problem—by which I mean, one that is actually making Bitcoin less useful—then miners will begin to implement better practices to stop it. That this option exists even though it has not yet been put into practice ought to be enough for Bitcoiners to sleep peacefully.