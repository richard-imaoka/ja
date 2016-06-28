---
layout: post
title:  "Review of Test Driven Development History and Literature"
date:   2016-05-28 21:08:00 +0900
categories: TDD
---

Many developers are (or were) passionate about test driven development. I think one reason for that is because of its psychological effects. It feels too good at the beginning.
Usually developers work in a code base with weak sets of tests. Especially, internally developed software within a company tends to have weak sets of test. And many developers maintain such internal software, and they are tired of it.
Then they hear about test driven development, and try it out in their job, or practice at home. And the red -> green cycle feels too good!! The red -> green practice was explained by Kent Beck, the father of test driven development, in the following book.
Test Driven Development: By Example

Edit description
www.amazon.com	
Once you start using test driven development, you enjoy this red -> green practice. The green light makes you feel happy. And resulting cleaner code make you feel you become a better developer. This gives you a fake sense of confidence, too strong than it actually should be. “God, with this simple approach, I came up with good code, good test coverage, and I feel safe when making changes to my code! Everyone should do this!!”
You need to take a step back. Being a good developer and writing good code is hard. It’s just hard. Much more difficult than test driven starters would think. Test driven development works very well at the beginning if you write code from scratch. However, you will suffer a lot later, even if you did a test driven approach from scratch.
At the beginning, adding tests are easy. And you write and maintain the tests. Newly added classes, methods, or functions are simple and short. This totally changes at a later stage. Again, even if you started test driven from scratch.
At some point, you need to maintain tests written by someone else. That could be a person who doesn’t understand the philosophy of good tests. And when people started running the code in real use cases, inevitably there are complicated cases, which you did not think of before. That results in messed-up if/else clauses in your code. And you see a lot of parameters added to methods and functions to make them more general. If the internal logic of a method or a function is messed with if/else clauses, tests also become ugly and verbose. Adding more parameters grows the number of test cases you write.
What happened here? At the beginning, you gained boost from the test driven approach. Because there was almost no maintenance effort at the beginning. However, when the code base grows, test code also grows. And you cannot avoid maintenance cost, even from both test code too.
Suffered from real experience, you would tend to conclude that test driven development is not practical, at least in your job place. Well, actually you came to the next stage at this point. It might not be test driven development any more, but still you have felt the importance of tests.
No matter whether it is test driven or not, tests are anyway critical. You should explore ways to write better tests, as a continuous journey. As I said, becoming a good developer is hard. And writing tests is a significant part of good software developer practices.