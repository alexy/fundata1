Karmic Social Capital is a strict mathematically defined value for a node in a social network, computed iteratively with each reply edge added to the communication graph.  The complete mathematical definition is provided in

[Alexy Khrabrov and George Cybenko, Mind Economy: Social Capital in Social Networks, European Conference on Complex Systems, Lisbon, 2010](khrabrov-2010-mind-economy-eccs.pdf)

Here's a recap in plain English.

We want a measure which is more explainable than the PageRank and lets us parameterize what we value in a network.  We like nothing better than a good karma, and define karma as being responsive to those who talk to you, as well as being able to elicit responses from those folks you address.

At each step, we adjust your Karmic Social Capital as a function of its past value, decaying it with a multiplier, and adding new infusion from the karmic rewards.  We keep your balance of communications with everybody who talked to you or to whom you talked by now.  If the balance is negative, meaning you owe some replies, and you provide them, we reward you.  Likewise, if the balance if positive, it means you overreplied to somebody; if they have now replied back, you get more points.

We renormalize each kind of karmic reward by the total achieved in a day; and we advance from day to day in an inductive fashion.  The norms are output at each stage as a debugging measure; you'll get used to their correct values in the course of running the benchmark.