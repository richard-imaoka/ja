---
layout: post
title:  "Review of Test Driven Development History and Literature"
date:   2016-05-28 21:08:00 +0900
categories: TDD
---

Growth Stage and TDD Strategies
When developers talk about TDD, Test Driven Development, there are always heated discussions. A typical question is whether a startup company should do TDD or should not, like below.
Is Test Driven Development practical for a startup?

Ted Cruz is renowned even by members of his own party for being an unlikeable jerk. The man is, somehow, apparently…
www.quora.com	
I think actually the answer is obvious to everyone, but it doesn’t mean there is a single clear practice for everyone to follow.
Answer: Do TDD as long as it gives you more benefits than burden, and if it slows you down, you should probably stop doing TDD or you are doing it incorrectly.
Sorry, you felt I am not answering to the question then. :| The “answer” I gave was obvious, but it didn’t tell you what to do exactly. Well, still it’s one step forward knowing the answer, isn’t it? (i.e.) you realized there is no single practice everyone can follow.
I think a more practical question could be ”to what extent I should do TDD, at my current growth stage or circumstances?“
If you are in a startup, think about TDD approaches that doesn’t slow down your business but give little more confidence about every code change. The key is to how TDD speeds up release processes by making tests easier. Also how frequently you see failure and errors from your products, which could have been prevented by TDD.
Remember test code is also technical debt, as well as production code. You have to maintain tests. So the benefits from tests must always exceed the burden of test maintenance. Otherwise, you just get trapped with long-existent test failures, which no one fixes.
Test Driven Development and Technical Debt

Test Driven Development speeds up development, but at the same time slows down development too. It is a matter of…
medium.com	
In a stage where you got a promising portion of market, and trying to grow quickly, there are higher chances that the defect rates raise up sharply. Your business and software are growing exponentially, so there will be a lot more chances that get messed up. In that case, assuming you got enough money from venture capitals, you might also want to invest in test and have more solid culture of TDD. Again the important thing is to speed up your releases, development cycles.
In a matured stage, it is possible that a large code base has very weak sets of tests. Maybe there are unstable pieces of code and components, causing a lot of headache to developers. Start with components with the most impact, which could be improved by TDD. Don’t dream of 100% coverage of every single component if you are not close enough to that. Writing test code is also an investment, requires resources, so you need decent benefit from that activities and avoid extra burden from failing tests, which no one wants to maintain.
