Software as a complex derivative contract
To make right investment decisions for software, you need to correctly analyze the cost and revenue structure of the software. You can assume software as a complex derivative contract to make this analysis.


Images by sheelamohan and Stuart Miles at FreeDigitalPhotos.net
Incoming Cash Flow of Software = Revenue
To analyze software as a complex derivative, you need to decompose its cash flow structure. Firstly let's look at its incoming cash flow, which is revenues generated from software (in a more strict sense, revenues from the business dependent on the software).


Image by stockimages at FreeDigitalPhotos.net
It is almost always impossible to predict the exact revenues from the software, as you cannot tell what happens in the future, future revenue has probabilistic nature.

To make further analysis, in later articles, it is important to take this probabilistic, uncertain nature of future cash flow into account.

What if the software doesn't generate revenue at all?
There are cases where your software does not generate revenue at all. Even in such cases, you still pay maintenance cost for the software. Examples of such software is backend database or data layer, middle tier like messaging layer, or maybe internal books and record system for accounting.

In other articles, I will discuss how to make investment, const analysis on such software, but basic techniques are:

Just focus on the cost components of the software
Or, think about the entire "system"
and treat these as "part" of the whole revenue-generating system
Outgoing Cash Flow of Software = Maintenance Cost
The outgoing cash flow of software is maintenance cost in general. And the large part of the maintenance cost is the pay to the developers and support people of the software. Software metrics, for example as follows, help you to determine the cost break-down structure of software.

Frequency of troubles
Average time to trouble resolution
Build Frequency
Average build manual work load
As discussed in the below two articles, people's desktop app usage metrics can be a very useful metric.

Desktop app usage metrics... (e.g. RescueTime)
Pricing and Accounting Software - Expenses, Time-Tracking for Maintenance Cost Calculation Pricing and Accounting Software - Expenses, Time-Tracking with RescueTime

Once you collected necessary software metrics, then you need to determine and calculate the cost associated to the software.


Image by David Castillo Dominici at FreeDigitalPhotos.net



Software as a complex derivative contract
To make right investment decisions for software, you need to correctly analyze the cost and revenue structure of the software. Thinking about Financial derivatives and its arbitrage relationship, you can tell how to price financial contracts.

Arbitrage relationship on a Futures contract
The below video by Investtools (from Ameritrade) gives quick illustration of what futures contract is.


Once you understood what futures is, then let's think about its arbitrage relationship and how you derive the right price using arbitrage. Assume there is an oil futures contract in a Financial market, and its currently traded at $1,100 for 3-month delivery. So if you

Sell the futures contract, you will sell the oil at $1,100 3 months later
Buy the futures contract, you will buy the oil at $1,100 3 months later
To form up arbitraging trades, you can start selling the futures contract as in the below Fig. 1. Note that from the futures contract, no money, or oil exchange happens today.

Fig 1. Selling Futures contract

(Image by Suat Eman at FreeDigitalPhotos.net)
At the same time, you can buy the oil, which is currently traded at $1,000. Buying oil is an immediate trade, so you pay $1,000 and get the oil. However, you need to store oil somewhere, that will incur strage cost.

Fig 2. Buying Oil

Image by Suat Eman at FreeDigitalPhotos.net
Also, you borrow money from a bank to support the buy of the oil. When you return back money, you will be charged $50 extra.

Fig 3. Borrowing money to buy oil

Image by Suat Eman at FreeDigitalPhotos.ne
If you look at the above 3 figures, you will notice that you buy oil today and sell it 3 months later. So you will end up in no oil holding 3 months later. So you just need to think about what cash difference you end up, to calculate the profit. Then,

Buying Oil today (- $1,000) + Borrowing $1,000 - Storage Cost ($50) - Return Borrowing ($1,050) + Selling Oil in 3 months (+ $1,100 ) = zero

This means that the oil futures price = $1,100 is correctly priced from arbitrage perspective. If we talk about such a simple Financial derivative, arbitrage pricing is as simple as this. However, what about more complicated derivatives?

Arbitrage relationship on PRDC, a very complex derivative
PRDC, Power-Reverse Dual Currency trade is a very complicated instrument as follows. You can look at the linked Wikipedia Document, and see there are lot of components forming up this derivative transaction.


PRDC structure by Wikipedia
To construct an arbitrage pricing argument, you need to de-compose the complex derivative and apply the arbitrage pricing argument for each of the de-coupled components. However, as given on the Wikipedia page, it is practically impossible to construct perfect (or even nearly-perfect) arbitrage positions for PRDC.

De-compose Software, for arbitrage pricing discussion
The PRDC situation is a similar to software. To correctly price software, you can firstly de-compose it into smaller pieces, and apply arbitrage pricing method to calculate each component's fair price.

The difficulty is coming from the fact that, like PRDC, it is practically impossible to find out complete replacement or alternative to any software component, even if you divide it up to as small pieces as you can. That is why I treated software as complex derivative, like PRDC.

Anyway, we still need to de-compose software for arbitrage pricing, so let's assume there is a simple 2-tier web application software like below. You have a web server, and its backend database.


PRDC structure by Wikipedia
By de-composing it and looking into the database piece, you can calculate the cost contributions as follows:

Database License fee
Pay to Database Support Person
As the database itself does not generate revenue at all, we can only think about its cost.

Then we think about arbitrage - what would be the replacement and switching cost? Maybe, if you have the database license fee, you might want to use open source databsae software like MySQL or Postgress. Then there will be learning curve for the database support, and especially in the initial period after replacement you will see a higher number of issues than usual.

If the reduced database license fee, and reduced support person's workload (if possible) is worth the switching cost (increase in issues, supposedly short-term, development cost, etc), it is an arbitrage trade, but as said above, this is not perfect arbitrage as you have uncertainty that actual cost would increase.

We will dig in further into this software pricing method in other articles.