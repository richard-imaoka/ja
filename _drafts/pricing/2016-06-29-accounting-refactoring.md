Refactoring Software is Explained in Financial Accounting Context
'Technical Debt' is a known metaphor in Software Engineering. We already explained how enhancement can be explained in the Financial Accounting context, so how it works for refactoring?

The previous post, Software Enhancement is Explained in Financial Accounting Context, showed how software enhancement can be explained from a Financial Accounting perspective.

Good refactoring only reduces Technical Debt
Refactoring is an activity to clean up your code, and make it easier to maintain. As Martin Fowler said, it is to preserve the original behavior of the software, but still make it better designed.


So, essentially the Technical Debt will be reduced without having to reduce software's value.

As the Technical Debt was decreased, the software becomes easier to maintain, less error prone, and the mainteance cost will be saved.
Bad refactoring actually increases Technical Debt
So far a happy scenario, but what happens when you do bad refactoring? For example, you introduced unexpected bugs, or you chose wrong design or implementation so that it actually becomes difficult to maintain and change the code going forward.


In such a case, total Technical Debt of the software is increased,

And thus the maintenance cost is also increased. It is analogous to increase in Financial Debt causing increase in debt charge too. You will see loss from this refactoring activity.
Bad Refactoring should be reverted immediately
So, what to do, when you did bad refactoring? You revert it back! Unfortunately, in practice, it is sometimes found that previous refactoring had unexpected bad impact, and you need to revert the refactoring.

The best practice in refactoring is to do it in very small steps. If you do large scale refactoring, and the problems are realized later, it gets much harder to revert to the original state. So, if you cannot revert the refactoring, your software will operate in an inferior quality - more maintenance cost than before.

References
Martin Fowler, "Refactoring Improving the Design of Existing Code", Martin Flower.com