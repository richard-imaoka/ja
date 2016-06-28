Software Liquidity and Monolithic Spread
As in the previous article, software is an illiquid asset and its replacement cost tends to be very high. However, there is a way to recude replacement cost. Since the high cost is coming from liquidity, if you make the software more liquid, (i.e.) easier to get rid of or create, it can be a cost saving opportunity.

Replacing a huge, monolithic software system is more expensive than replacing small-pieced system
Let's assume you have a huge monolithic system and its replacement cost to a newer system is represented as follows.


If you split up the monolithic system into smaller components,


Then you would be able to replace each component individually. And each of them has its own replacement cost.


Comparing the sum of small-component replacement and monolithic replacement, it tends to be that the replacement of the monolithic system is more expensive. Let's call this as "Monolithic Spread" - this is the cost you are paying for your monolithic (i.e.) illiquid, harder-to-replace system. It can be explained that smaller piece of the system is easier to replace, thus lower cost.


Monolithic spread matters on replacement, but there is an opposite effect on maintenance cost
Thinking about replacement, it feels like your system should always be split up into smaller pieces so that each component can be easily replaced by newer technology.

However, there is a known counter effect talking about maintenance cost. In certain cases, dividing up a monolithic system into smaller pieces can cause more maintenance cost. So if you have no immediate plan of software replacement, you should be careful.

We will cover that topic in the next article.

Monolithic vs. Microservice trade-off, Replacement and Maintenance
Almost always a larger system is harder to replace, than a system with smaller components. So thinking about replacement cost, is it always better to construct a system with fine-grained small components? Not actually, there is a trade-off on it.

Small-Component software system is easier to replace than huge monolithic system
As we see in the previous article, generally a software system consisting of smaller components is easier to replace, than a monolithic system. It is almost always easier to replace something smaller than bigger.


However, there is a trade-off when splitting a system into smaller components
So, it is likely any software system is replaced at some point, and to keep up with the speed of changing in today's market, is it always a better strategy to build up a software system with fine-grained small components?

An example - Micro-Service discussion highlights this trade-off
The below article by Martin Fowler exactly discussed this trade off. Smaller-component systems have less productivity in everyday maintenance (i.e. higher maintenance cost) compared to a monolithic system, if the system is not too complex .

 Follow
 Hacker News @HNTweets
MicroservicePremium by Martin Fowler: http://martinfowler.com/bliki/MicroservicePremium.html … Comments: https://news.ycombinator.com/item?id=9538945 
11:10 PM - 13 May 2015
Photo published for bliki: MicroservicePremium
bliki: MicroservicePremium
The microservice architectural style is useful for handling complex systems, but brings its own complexity so should not be used for simpler environments.
martinfowler.com
  Retweets   likes
Conclusion: 1) Too big, complex system -> split it, 2) not too big -> take a balance
As discussed by Martin, a general strategy is:

"don't even consider microservices unless you have a system that's too complex to manage as a monolith"
This means that if your system is a too big and complex monolith, chances are that if you split it into smaller pieces (probably in micro-service sytle), you get benefit in both daily maintenance and replacement.

If your system is reasonably sized, but still feels like bit the size and the complexity is preventing you from necessary replacement, it is a more difficult situation. You would still get a replacement cost benefit from split into smaller components, but it needs to be compared against maintenance cost change.

To make a decision on start splitting your system, and make the split work effective, you would need:

Cost calculation model and right metrics to validate replacement pays off
Iterative reviews to see if the replacement work still pays off