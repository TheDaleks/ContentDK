---
layout: post
title: How to Reduce Expected Network Criminality
permalink: reduce-criminality
excerpt: To a violent criminal, the Anoncoin market (in other words, goods offered for anoncoin) is more useful than the Bitcoin market because it’s easier for him to use violence to get Anoncoin. Consequently, violent criminals will have portfolios with more Anoncoin and will therefore cluster with more Anoncoin holders. 
---

You are a node in the network. The connections in the network consist not just of your friends, but anyone who is secretly spying on you.

## Expected Network Criminality

Consider a path through the network graph. Consider

<code>(1 - p) (sum over all nodes i in the path) c_i p^i</code>

Where

    <code>i</code> is the index of the node along the path.
    <code>c_i</code> is the criminality of the node <code>i</code>. This is a number from <code>0</code> to <code>1</code>.
    <code>p</code> is the expected probability of meeting a friend of a friend in this graph.

The result will be a number between 0 and 1 that I define to be the criminality of the path. It is an idea about how closely a path connects you to all violent criminals along it.

Consider the average criminality of all infinite random walks starting from a given node and which never return to their starting point. This is the expected network criminality from the standpoint of the given node. The average expected network criminality for all nodes is an idea about how much criminality would be expected in the network, not knowing who one is in it. It is like the “veil of ignorance” of John Rawls.

##Anoncoin vs Bitcoin

Anoncoin allows for valid orders to transmit money that cannot be traced to a particular node. In Bitcoin, all valid orders to transmit money can be traced to a node. Knowing nothing about who we are (in other words, under the veil of ignorance) which sort of coin is preferable?

Two networks can consist of the same people (in particular, the same number of criminals) and have different expected network criminalities because of different processes by which connections were created. A network in which violent criminals can make connections more easily will have a higher expected network criminality because more paths out of the average person will lead to a violent criminal.

The problem with Anoncoin is that it is vulnerable to rubber hose cryptography. Because the transmission order cannot be traced to a definite node, no one can say later whether any such order was created as a result of violence or whether any injured node which identifies himself later was the origin of the message.

In Anoncoin, violent criminals are more likely to go out and make new connections with other people because of the vulnerability which Anoncoin has to rubber hose cryptography. Thus, in a world that uses Anoncoin, everyone is more surrounded by criminals than in a world that uses Bitcoin, even if there are the same number of criminals.

I now ask, can Anoncoin maintain value in competition with Bitcoin?

## Portfolio-weighted Expected Network Criminality

Consider portfolios of cryptocoins as vectors. The portfolios consisting of one unit of one crypto are orthogonal unit vectors. Consider the line which consists of all vectors in a given direction, in other words, all portfolios having the same ratios of coins irrespective of total value. Consider this line as a point in projective space.

Consider a network in which every node is associated with a point in projective space. Consider a random walk which weighs nodes according to the distance between two points in projective space.

The portfolio-weighted network criminality of a node is the average criminality of all infinite random walks that do not return to the origin weighted by projective distance to the origin. In other words, the random walk is more likely to go through people who have similar portfolios to yourself.

Money causes people to cluster. In other words, a friend of a friend is more valuable if you both use the same money. Portfolio-weighted network criminality is an idea about future clustering around criminals that occurs in a network in which Anoncoin and Bitcoin coexist.

## Consequences

To a violent criminal, the Anoncoin market (in other words, goods offered for anoncoin) is more useful than the Bitcoin market because it’s easier for him to use violence to get Anoncoin. Consequently, violent criminals will have portfolios with more Anoncoin and will therefore cluster with more Anoncoin holders.

If your portfolio is Anoncoin-weighted, your portfolio-weighted expected network criminality is higher. You can reduce your portfolio-weighted expected network criminality by selling Anoncoin and buying Bitcoin. This makes sense because your portfolio is genuinely less valuable if it increases your expected network criminality.

Which force is stronger? Criminals preferring Anoncoin or non-violent people preferring Bitcoin? If the first is stronger, Anoncoin goes up and Bitcoin goes down as more criminals reduce their Bitcoin holdings without replenishing them. Thus the portfolio-weighted expected network criminality of Anoncoin increases for Anoncoin investors and decreases for Bitcoin investors. That makes Bitcoin a better buy but it also means that lots of nonviolent people are dupes who will end up being victims of violence. Violent criminals will be rewarded as long as other people don’t understand what is happening.

On the other hand, if non-violent people prefer Bitcoin, then there will be no market for Anoncoin for criminals to be interested in. Violent criminals will have difficulty making new connections and therefore expected network criminality is lower. Thinking ahead about value leads to better outcomes.

## The Nature of Anonymity

Anonymity is a service that a group of people all give to one another. Everyone is both provider and consumer. This is important to understand because everyone in the group is responsible for the service. If someone can use your service to steal money, then all money becomes less valuable. If you have been anonymous, what did you do to ensure that your service cannot enable people to steal money? If you have done nothing, you have created something attractive to violent criminals.

Can an anonymizing service be designed that keeps violent criminals out? It cannot because violent criminals are always more motivated on average to want the service. A peaceful anonymity service must always turn away its best customers. Expected network criminality goes down the more difficult it is for peoples’ money to arrive at an anonymizing service. Thus it always goes up closer to the anonymizing service. Peaceful anonymization is a fight against value. Everyone who wants nonviolence is much better off reducing expected network criminality by avoiding anonymity services.

If your coin changes into Anoncoin without your understanding, you have been duped into helping violent criminals erase records without knowing that you had the responsibility of being an anonymity service provider. Furthermore, your expected degree of clustering with violent criminals has increased without your knowledge. BTC is being transformed into Anoncoin without the full understanding of the BTC investors.

Anonymity is the ultimate con. People who have it believe that it is making them more free, but it is really just turning them into murder victims. The more quickly people understand this, the faster BTC, Monero and the rest will go to zero. The better the problem is understood, the less people will be at risk.
