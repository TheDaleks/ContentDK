---
layout: post
title: Bitcoin Offers Solutions to All Your Byzantine Generals Problems
permalink: byzantine
excerpt: Bitcoin is like an advanced alien that has come down to earth offering a service that everybody needs but no one wants because they don't understand it. Bitcoin is a solution to the Byzantine Generals Problem and it offers itself as a service. But what is that service? This article explains the nature of Byzantine fault-tolerance.
image: https://blog.matterpool.io/content/images/size/w2000/2020/02/borg.png
---

Bitcoin is like an advanced alien that has come down to earth offering a service that everybody needs but no one wants because they don't understand it. Bitcoin is a solution to the Byzantine Generals Problem and it offers itself as a service. But what is that service? This article explains the nature of Byzantine fault-tolerance.

# The Byzantine General Problem

The _Byzantine Generals Problem_ was first discussed by [Lamport, et al](https://people.eecs.berkeley.edu/~luca/cs174/byzantine.pdf):

“A reliable computer system must be able to cope with the failure of one or more of its components. A failed component may exhibit a type of behavior that is often overlooked--namely, sending conflicting information to different parts of the system. The problem of coping with this type of failure is expressed abstractly as the Byzantine Generals Problem.”<sup class="footnote-ref">[[1]](#fn1)</sup>

In other words, a Byzantine Generals Problem can be defined as a network recovering from a node that fails by sending arbitrary data to other components. What can a node do if it can send "conflicting information" to different parts of the system? It can confuse other nodes about which is the failed component.

Lamport et al go on:

“We imagine that several divisions of the Byzantine army are camped outside an enemy city, each division commanded by its own general. The generals can communicate with one another only by messenger. After observing the enemy, they must decide upon a common plan of action. However, some of the generals may be traitors, trying to prevent the loyal generals from reaching agreement.”

Thus, Byzantine generals have a need to reach agreement in the presence of other generals who “may be traitors” in order to be successful in a battle. Systems which are not solutions to the Byzantine general’s problems are like systems in which traitors can prevent loyal generals from reaching agreement. A traitor is someone who fails by sending conflicting information to different generals.

A solution to the Byzantine Generals Problem, therefore, eliminates the influence of traitors from any decision-making process. Decisions involving real costs, similar to that of peoples’ lives in wartime, can be made reliably in a Byzantine fault-tolerant system.

Oleg Andreev has characterized the Byzantine Generals Problem in this way:  
“Imagine you are sitting in a bunker. You have no idea what people are out there and what are their intentions. You only receive some incoming messages from strangers that may contain anything. They can be just random garbage or deliberately crafted messages to confuse you or lie to you. You never know. You cannot trust anyone.”<sup class="footnote-ref">[[2]](#fn2)</sup>

Thus, from inside their bunkers, Bitcoiners separate truth from falsehood. Customers of their service become like generals who can identify all traitors among them and successfully defend or attack together.

# Trusted Third Parties

A trusted third party is an entity whose service is reliably providing truthful information to pairs of other nodes, information that they need in order to interact successfully. In the context of Byzantine fault-tolerance, this means that neither party can transmit conflicting information in a way that prevents honest nodes from agreeing. Any information which a trusted third party has that can prevent other nodes from transmitting conflicting information is information that the trusted third party can lie about in a way that causes the system to fail.

Trust is a promise not to be a traitor. Honest nodes who rely on trusted third parties cannot reliably all “attack” or “defend” at the same time. Thus, a system with a trusted third party violates Byzantine fault-tolerance.

In “Trusted Third Parties Are Security Holes”, Nick Szabo, proposes that the use of trusted third parties should be minimized and if they are used, the trusted system should be designed in parallel with the protocol that requires it.”<sup class="footnote-ref">[[3]](#fn3)</sup> In other words, if trust is simply assumed as part of the protocol design, then it is not a secure protocol. Trust must be established rather than assumed.

The whitepaper identifies trusted models with an inability to avoid fraud. Trusted models cannot avoid "mediating disputes" and therefore a “certain percentage of fraud is accepted as unavoidable”.<sup class="footnote-ref">[[4]](#fn4)</sup> In other words, no one really has absolute truth. Thus a trusted system, whose job is to provide truth, must resolve disputes in order to have truth. Fraud is a form of treachery that prevents honest nodes from agreeing. Since Bitcoin is Byzantine fault-tolerant, Bitcoin users avoid fraud.

Trust which has not been established can be abused. What happens when a trusted third party becomes abusive? The true risk of the “often overlooked” potential of failed nodes to send conflicting information to different parts of the system is the ability to confuse nodes as to who is a traitor. It can do this by transmitting information which causes honest nodes to misidentify traitors. This, in turn, can cause other nodes to fail and act against the system simply because they have believed lies and not because they are dishonest.

The shape of a network with trusted third parties is hub-and-spokes. Customers are sparsely connected to one another, but all connected to the trusted party in the center. The sparse connections of the customers creates their need for a trusted third party. In a hub-and-spokes network, the hub has a view of the whole network whereas the spokes do not. A superior view of the whole makes a successful trusted third party into a superior target for attack from traitors. These traitors may be hackers who try to break it from outside to access secret information or they may be agents of the trusted system itself who use their information to manipulate customers. Honest nodes can be trapped in an illusion that they struggle to break out of because of the ability of the trusted third party to make up new lies.

In _The Matrix_, Morpheus [tells Neo](https://www.youtube.com/watch?v=cqxwtEdxOCw), “When you are inside what do you see? … the very minds of the people we are trying to save. But until we do, these people are still a part of that system and that makes them our enemy. And many of them are so inured, so hopelessly dependent on the system that they will fight to protect it.”<sup class="footnote-ref">[[5]](#fn5)</sup>

_The Matrix_ also contains agents. These are “sentient programs” that “can move in and out of any hardware still hardwired to their system.” Thus, according to Morpheus, the agents can enter the minds of the humans that are connected to the Matrix and use them to attack outsiders. The agents, therefore, are like lies that are told to customers that cause them to misidentify traitors. This is why the people plugged into the matrix are both friends (people who should be rescued) and enemies. Bitcoin can rescue people from becoming Agent Smith.

![drawing](https://bico.media/69939064258a891ece4fce1b2f2240fde482869dab8fa49738ed5b88e0b9887e.jpg "A hub-and-spokes network. Image credit @5111 on Twetch")

In _Expanded Universe_, Robert A. Heinlein discusses an event that occurred during his trip to the Soviet Union in 1960 and the effect it had on him. When he and his wife first arrived in the USSR everyone was very friendly:

“[I]n Moscow, we had been picked up by two Russians the very first time we went out on the street. One was a technical translator; the other, a lady, was a museum curator. They were very friendly and stayed with us almost three hours, asking questions about the U.S. and inviting questions about the Soviet Union. This happened to us daily thereafter; we were always making casual acquaintance with Soviet citizens, on the Street, in parks, in restaurants, during intermissions at the theatre, everywhere. They were always curious about America, very friendly and extremely polite.”<sup class="footnote-ref">[[6]](#fn6)</sup>  
However, on May 5, the attitude of the Russians changed toward them.

“From the time we reached Leningrad until we left for Helsinki, Finland, not one Soviet citizen other than Intourist employees - who had to deal with us professionally - spoke to us under any circumstances. Not one.”

What had happened? Heinlein ascribed the cause to “control of all communications from the cradle to the grave.” On May 5, Khrushchev gave a five-hour speech that the Russians all listened to without options to receive countervailing information. In this speech he lied about an American spy plane that had grounded itself 1500 miles inside the USSR, saying that it was a military plane that had been shot down at the border. Because Russians generally all listened to the same sources of information, their attitudes could be "switched on and off like a lightbulb".

Friedrich Engles invented the term “false consciousness” to refer to “the notion that members of the proletariat unwittingly misperceive their real position in society and systematically misunderstand their genuine interests within the social relations of production under capitalism.”<sup class="footnote-ref">[[7]](#fn7)</sup> Agent Smith is like someone with false consciousness because he wants to attack someone who wants to rescue him. Engles believed he was talking about capitalism, but he inadvertently described what occurs under communism, or in any [cult-like](https://news.bitcoin.com/how-to-fight-cryptocurrency-cults/) group in which some central hub is trusted to provide absolute truth.

# Bitcoin's Competition

Trusted third parties are Bitcoin’s competitors, which can be emulated as sequences of Bitcoin transactions. Bitcoin competes with trusted third parties with its superior ability to ensure all honest nodes agree. The miners who provide Bitcoin as a service do not have to promise that the transactions will follow the rules. Any miner who fails to follow the rules creates a profit opportunity for the rest.

Who are Bitcoin’s competitors? Many organizations other than totalitarian governments such as the USSR are in a position to create a false reality that can cause honest nodes to misidentify traitors. The Bitcoin whitepaper specifically mentions trusted financial institutions. However, because Bitcoin enables micropayments, it can emulate other trusted third parties cheaply.

For example, social networks are trusted third parties. Because social networks before Bitcoin could not earn money through micropayments, their business model involves manipulating users into being useful to the social network. The social network can analyze the behavior of users and learn things about their behavior that none of them know. Bitcoiners can analyze themselves rather than be analyzed by the only party with all the data. The social network can control the discussion in order to make the community of users preferable to advertisers. Facebook has shown that it can alter users' moods by selecting content that is displayed to them.<sup class="footnote-ref">[[8]](#fn8)</sup> Much worse is possible.

On Bitcoin, we now have a social network called Twetch which relies on micropayments rather than ads. All interactions are Bitcoin transactions. Twetch cannot trap customers in an imaginary world nor does it have any reason to.

Unfortunately, Bitcoin has been so poorly understood that it was gravely damaged by an attack that involved manipulating many Bitcoiners who did not understand the dangers of a hub-and-spokes network into believing that Bitcoin is a trusted system. This attack was performed by a collusion between the Bitcoin Core developers and exchanges, both of which are trusted third parties that Bitcoiners ought to have realized were made obsolete by Bitcoin. Bitcoin exchanges are exactly the kind of trusted financial institutions that the Bitcoin whitepaper says must result in “a certain percentage of fraud”. The Bitcoin Core developers are a group of contributors to the Bitcoin github repository who claimed to know the best ways of changing the design of Bitcoin. Github is a trusted system that became an inviting target because of Bitcoin’s value.

Bitcoiners who believed that the Bitcoin Core github repository was Bitcoin were all transformed into Agent Smith. They treated anyone who wanted Bitcoin to scale as an enemy and tried to drive them out of the community. They became traitors not just of each other, but of themselves. They allowed the value of their coin to be destroyed by making it useless as money and dependent on the whims of the Core developers. Manipulators must remove Byzantine tolerance in order to maintain their position. Fortunately, they did not and in a truly Byzantine fault-tolerant system, they cannot. Bitcoin has been severely hurt by their attack but is immune to any future attacks like it. The real Bitcoin continues on as Bitcoin SV without Core manipulators. They and all they have fooled have expelled themselves. When they realize that BTC they have is worthless, it will be too late. They will not be able to buy Bitcoin with it.

Bitcoin’s competition does not have what Bitcoin has by definition. One by one, all competitors will fail eventually. Bitcoin will survive longer than any trusted system. That is its function and its service. All failed parts will be replaced. Bitcoin’s service is so useful that not wanting it is false consciousness. Honest people will unplug from the Matrix, look out from their bunkers, and see who their friends are. They will all attack or defend at the same time and their competitors will not. Resistance is futile.

# References

* * *

1.  Leslie Lamport, Robert Shostak, and Marshall Pease, The Byzantine Generals Problem [↩︎](#fnref1)

2.  Oleg Andreev, "Proof that Proof-of-Work is the only solution to Byzantine Generals' problem" [https://gist.github.com/oleganza/8cc921e48f396515c6d6](https://gist.github.com/oleganza/8cc921e48f396515c6d6) [↩︎](#fnref2)

3.  Nick Szabo, Trusted Third Parties Are Security Holes [↩︎](#fnref3)

4.  Satoshi Nakamoto, Bitcoin Whitepaper [↩︎](#fnref4)

5.  Wachowskis, The Matrix. [↩︎](#fnref5)

6.  Robert A. Heinlein, Expanded Universe [↩︎](#fnref6)

7.  [https://www.britannica.com/topic/false-consciousness](https://www.britannica.com/topic/false-consciousness) [↩︎](#fnref7)

8.  Adam D. I. Kramer, Jamie E. Guillory, and Jeffrey T. Hancock, [Experimental evidence of massive-scale emotional contagion through social networks](https://www.pnas.org/content/111/24/8788), Proceedings of the National Academy of Sciences, June 17, 2014 111 (24) 8788-8790 [↩︎](#fnref8)
