# Threat modeling focus on the Assets.

A summary of some already [succint advice](https://news.ycombinator.com/item?id=23299771) on how to approach threat modeling by [Jacek Złydach](http://jacek.zlydach.pl/).

1. Be careful to not place to much focus on the Actors, Actions or Consequences. 
2. The combinations of Actors and Actions can be confusing and nearly endless.
3. Framing the modeling around the Actors and Actions makes judging their individual and overall impact to risk difficult.
4. Everything pivots around Assets, because they're affected by a particular Actor and Action.
5. It's the Assets that motivates most attacks and the primary source of consequences.
6. Don't get stuck thinking out the motives behind an attack.
7. Instead focus on the Assets you have and on what can go wrong (e.g. financial, privacy, intergrity impact) .
8. Anytime you hear or read Actor think of it as Attackers (…all the way down). 
9. Just as increasing the cost of any attack can be helpful for defense, spiralling down into endless taxonomies and hierarchies of Actors, Actions, and Consequences can be helpful for the attacker.
