<div class="my-4 text-center">![Dumb Baby](b://6237e18a8c633c9a7282e07d3c57158d100a67ead14057b97b15d26c585e089d)</div>

# Ethereum Is Doomed.

_Daniel Krawisz_

**Originally published [20 June 2016 at Nakamoto Institute.org](https://nakamotoinstitute.org/mempool/ethereum-is-doomed/).**


As [some have noted](https://twitter.com/jgarzik/status/736945669978525696), I did not understand Ethereum very well when I wrote my [previous article](https://nakamotoinstitute.org/mempool/the-coming-demise-of-altcoins/) that touched on it. I dismissed Ethereum as just another altcoin with extra bells and whistles. However, there was a huge opportunity hiding in there, open to anyone who understood the system well enough. I wish I had examined it further and much more deeply because right now someone who did that, [someone whom I now admire](https://pastebin.com/CcGUBgDG), is sitting on three million ethers. *Update*: the note is [probably not](https://news.ycombinator.com/item?id=11927891) from the real hacker. I still agree with its argument.

This person has developed a new investment strategy for the age of smart contracts: You simply look for a way to exploit the smart contract which causes it to send cash into your account, and then invest in it so as to control it in a way that [extracts the money](https://hackingdistributed.com/2016/06/18/analysis-of-the-dao-exploit/).

Ethereum truly is different from other altcoins. If I had looked into Ethereum more carefully, I might have noticed that economics was not the only subject that the Ethereum devs did not understand. They also don’t understand law and software engineering. They created a situation in which bugs would be expected to arise in an environment in which bugs are legally exploitable. That is hacker heaven.

Let’s say that A wants to send ethers to B. I will write <code>A→B</code> as the atomic operation which removes money from <code>A</code>'s balance and adds it to <code>B</code>’s. This operation fails if <code>A</code>'s balance is not big enough. To send money in Ethereum, it is as if we had a function that looked like this:

<pre>
send[f, x, y] = If[
    // Send funds to B and call f; roll back if an error is generated.
    Try[ A→B; f[]; True, False],
    // Call this if no error was generated.
    x[],
    // Call this if an error was generated.
    y[] ]
</pre>

where <code>x</code> and <code>y</code> are functions provided by <code>A</code>, and f is a function provided by <code>B</code>. In other words, <code>A</code> sends the ethers to <code>B</code>, who immediately gets to call a function that does whatever he wants with the money. That function is <code>f</code>. If his function fails for some reason,<code>A→B</code> is rolled back and function <code>y</code> is executed. Otherwise, <code>x</code> is executed. Anyone can provide <em>any</em> function to be executed upon receiving funds.[^1]

This is already enough of a nightmare, but suppose you have a public function available to the hacker which is of the form

<pre>
hackMe[f] =
    // Use q to check whether we owe the attacker money.
    If[q[], send[f, x, y]]
</pre>

<p>where <code>q</code> is a function that is supposed to fail if the attacker has no right
to demand funds.</p>
<p>Suppose that the hacker calls <code>hackMe</code>, and provides an <code>f</code> of the form</p>
<pre>
f[] = p[]; hackMe[f]
</pre>

<p>If the hacker can get <code>q</code> to succeed inappropriately, the following code is
executed upon calling <code>hackMe</code>:</p>
<pre>
q[]; A→B; p[]; q[]; A→B; p[]; ... q[]; A→B; y[] ...
</pre>

If nothing else stops this execution, it will eventually stop when <code>A→B</code> fails as a result of A not having enough funds. It can also fail if the call stack fills up or if the computation runs out of [gas](https://www.cryptocompare.com/coins/guides/what-is-the-gas-in-ethereum/),but these are complications on top of the fundamental problem. A hacker can try to ensure that only the last send fails so as to end up with everything.

<div class="my-4 text-center">![Konrad S. Graf Via Twitter](b://2087db78b8408380895bac065abc96aa7b6eff08f41f8474b2ee36f80896d405)</div> Via [Twitter](https://twitter.com/KonradSGraf/status/743843080961409025)

A naive approach to this bug would be to write <code>q</code> so that it keeps track of how much is owed to <code>B</code> and fails if the money should already have been paid. However, this approach is not good enough because in the mean time, from function <code>p</code>, the attacker might run more code which you have made available to him which creates further liabilities. The fix which the Ethereum team released to upgrade DAO 1.0 to 1.1 takes this naive approach, as explained[here](http://hackingdistributed.com/2016/06/18/analysis-of-the-dao-exploit #was-1-1-vulnerable)

I've provided a scenario in which the result is to extract funds, but the issue is much more general than that. You can think of an Ethereum smart contract as being like a object in object-oriented programming, with a set of public methods that any other contract can call. If you call another contract's public methods, he can call any of <em>your</em> public methods and attempt to screw with your internal state. There are different names for this depending on what the malicious contract does (such as [(reentry and solar-storm)](https://blog.blockstack.org/solar-storm-a-serious-security-exploit-with-ethereum-not-just-the-dao-a03d797d98fa#.wpg35euyp) but the problem is really the same kind of problem you would have if you just allowed people to run whatever code you wanted on your own computer.

~~text~~This problem is so serious that it cannot be treated as a bug in the DAO. The problem is with Solidity itself, which is the scripting language used in Ethereum~~text~~*Update:* The problem actually all the way down to the Ethereum virtual machine. While reading the Solidity documentation, I noticed this:

> If <code>x</code> is a contract address, its code (more specifically: its fallback function, if present) will be executed together with the <code>send</code> call (this is a limitation of the EVM and cannot be prevented).

This means the same issue exists in [Serpent](https://mc2-umd.github.io/ethereumlab/docs/serpent_tutorial.pdf) another Ethereum scripting language, and every other one they might come up
with.

Imagine a bright eyed and bushy-tailed new programmer writing his first big contract: "Now let’s see here…” he thinks. “I’m using the send function. That means that I have to search for blocks of code that I’ve written which an attacker could attempt to run in an infinite loop until there is no money left. First of all, which possible blocks of code could be made to go in an infinite loop? It could be any part that calls send, intermixed with anything that the attacker wants to call in between… hmmm… " You have to think this every time you send anyone money. It is totally ridiculous to expect anyone to do this reliably. The only difference is that a novice would fail every single time he tried to write a contract, whereas an expert wouldn't even bother trying.

Now I have described this issue so as to make it very clear what is going on, but in Solidity, the function I have called <code>f</code> is not very visible to the programmer. It’s a method called the “default function” that can be defined on every address. It executes automatically when you send to that address. So if I was writing <code>hackMe</code> in Solidity, I wouldn’t have directly referenced the function <code>f</code> as I wrote, but it executes anyway. It is very easy to write <code>hackMe</code> in Solidity.

The [manual on Solidity](http://solidity.readthedocs.io/en/latest/) opens with “Solidity is a high-level language whose syntax is similar to that of JavaScript”, as if that were something to brag about. But apparently Solidity has much more than just a superficial resemblance to JavaScript. Solidity is like programming in JavaScript, except with your bank account accessible through the Document Object Model.

A sign that no one is prepared to write smart contracts in Solidity is the fact that the Ethereum dev team, the people who designed both Solidity and the DAO, could not even fix their own bug. They don’t have the ability to approach these bugs correctly, and neither, in my opinion, does anyone else. It may be <em>possible</em> to reliably write smart contracts that work correctly, but currently no one knows how to do it. The dev team is not likely to figure it out any time soon because they still think that this is just a bug in the DAO rather than a serious problem with their entire system. If you want a smart contract that you can actually use, you have to be <em>certain</em> that it is bug-free before it is deployed. there are no known tools or methods available to Solidity developers which could provide an appropriate level of certainty. Such tools will take years to be developed and until they are in common use, no Ethereum smart contract should be trusted. Ethereum is doomed.

The legal implications of this hack are more interesting than the hack itself. Because the code of the DAO is a legally-binding contract, how can you argue so as to convince a judge that some behavior of the program is really a bug? The DAO provides nothing other than its own code to specify how it is supposed to work. For example, there is [no specification in a formal language](https://www.reddit.com/r/ethereum/comments/4opjov/the_bug_which_the_dao_hacker_exploited_was_not/),or proofs as to its correctness. If the Ethereum team knew how to test software, they might have produced something like that, which also could have provided corroborating evidence that any bug was unintended.

I fully support the attacker’s actions, and I wish I had thought of it first. His ethers may become worthless before he can sell them for Bitcoin, but he may also have [made a huge short on ethers](http://hackingdistributed.com/2016/06/18/analysis-of-the-dao-exploit/#step-3-the-big-short) just before executing the attack and made around $1 million that way.

For a final comment on the Ethereum team’s response, I provide an insightful quote from [Emin Gün
Sirer](http://hackingdistributed.com/2016/06/17/thoughts-on-the-dao-hack/#what-s-a-hack-when-you-don-t-have-a-spec)

> Had the attacker lost money by mistake, I am sure the devs would have had no difficulty appropriating his funds and saying “this is what happens in the brave new world of programmatic money flows.” When he instead emptied out coins from The DAO, the only consistent response is to call it a job well done.

<div class="my-4 text-center">![Artwork by [Big λ](https://twitter.com/BigLambda/status/891148584334245888)](b://6237e18a8c633c9a7282e07d3c57158d100a67ead14057b97b15d26c585e089d)</div>

[^1] If you don’t believe me read this analysis of the hack [here](https://hackingdistributed.com/2016/06/16/scanning-live-ethereum-contracts-for-bugs/):

> To have a contract send Ether to some other address, the most straightforward way is to use the send keyword. This acts like a method that’s defined for every “address” object.

I love how he says this in such a matter-of-fact way, like that's no big deal.

Also note [this poor developer’s unease](https://vessenes.com/ethereum-griefing-wallets-send-w-throw-considered-harmful/) upon learning about this “feature”:

> Here’s the deal. In Bitcoin, an address is the public key that corresponds to a private key held by a wallet. I’m lying a bit to aid comprehension. But, fundamentally, it’s just a bit of data. In Ethereum, an address could be similar – not a contract, but a public key. But, it could also be another smart contract’s address. The Mist client encourages users to make a wallet contract as a first step after loading up, for example. Users would then offer the address of that contract as their ‘wallet address’. Other contracts do not typically utilize any mechanism to distinguish between an address of a private key, and an address of a wallet. It’s a fundamental transaction in Ethereum to send money to a contract, and developers seem to expect it to ‘just work’ like in Bitcoin or other digital currencies, perhaps with a transaction fee attached.

