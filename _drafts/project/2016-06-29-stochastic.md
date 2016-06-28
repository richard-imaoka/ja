Review of 'Stochastic Cost Estimation and Risk Analysis in Managing Software Projects' paper
I found an interesting paper - 'Stochastic Cost Estimation and Risk Analysis in Managing Software Projects' - which presents a method to analyze project duration using Monte Carlo Simulation. Monte Carlo is a typical simulation method in Financial Engineering, so it's interesting to see the bridge between Financial Engineering and Quantitative Software Engineering

"Stochastic cost estimation and risk analysis in managing software projects"

You can dowload the paper from the above link.

Monte Carlo Simulation in Finance
Monte Carlo is a typical simulation technique for a random process, In Financial Engineering, it is commonly used to calculate the price of an asset, especially complicated derivative assets.

Very briefly, it works as:

You model a random price movement of an asset (model means a Mathematical equation to describe the movement)
Run a simulation and then you see a random price movement path
Repeat the simulation multiple times (1,000, 10,000, or 100,000 ... dependent on the problem)
See the resulting probability distribution, and take the average
 Monte carlo simulation
By Sc1171 (Own work) [(CC BY-SA 4.0)], via Wikimedia Commons
Using Monte Carlo for a simple model like stock price doesn't make much sense, but Monte Carlo is a powerful tool for pricing complicated derivative assets, where the pricing model is too complicated to derive an answer (i.e. the price) mathematically. If you cannot solve the price mathematically, then Monte Carlo allows you to still price the derivative asset with a large number of simulations.

Monte Carlo in Software Engineering
So, how this paper used the Monte Carlo technique to estimate the software project risk? Firstly, it split a software project into multiple phases

Planning and Bid Preparation
Requirements Definition
Analysis and Design
Code and Debug
Integrate and Test
Deployment and Acceptance
Each phase of this is modeled as a random process (i.e.) it has a range of possible completion dates. And each phase is modeled as a different a different random (e.g. different standard deviation, etc).

The below is a figure from the paper, showing the results of 5,000 Monte Carlo simulations of the entire project.


What are the benefits, and challenges?
Benefits

The paper provided a basic, but a powerful and standard framework to see how the possible project completion date distribution would look like. It is very similar to derivative pricing with Monte Carlo in Finance.

Over time, you can tweak the model for each project phase, comparing the simulation with past-completed projects, and the models would be expected to be more accurate.

Challenges

There could be problems though, since it weighs historical data to predict the possible future project completion. If new technologies are introduced and they completely change the game, which is typical, historical projects do not predict future projects well.

Also this paper is based on Water-fall like project style. Maybe Agile projects need a bit different modeling.

However, this is still an informative paper providing probabilistic view on software project management.

References
Connor, AM; MacDonell, SG, "Stochastic cost estimation and risk analysis in managing software projects", Proceedings of the ISCA 14th International Conference on Intelligent and Adaptive Systems and Software Engineering (IASSE). Toronto, Canada, ISCA, pp.140-144