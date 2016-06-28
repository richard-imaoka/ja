Pricing and Accounting Software - Debt
In this article we'll review Financial and Technical debt again. We will see what makes us software call in the 'debt' metaphor, and

Why the metaphor Technical "Debt" is used? Because it causes maintenance costs
Let's review why people call software as Technical Debt. There is an excellent summary article, "Towards an understanding of technical debt", which puts Technical Debt into 5 different categories:

Maintenance work
Features of the codebase that resist change
Operability choices that resist change
Code choices that suck the will to live
Dependencies that resist upgrading
Eventually, as software causes cost as such, people call it Technical Debt, something you have to pay for.
Financial Debt, you have to pay it back
Speaking of Financial Debt, typically you have periodic payments to pay back the debt you are obligated. And as the time goes by, the debt amount decreases.


Image by sheelamohan at FreeDigitalPhotos.net
Also another important property is that usually it is straightforward to derive the periodic payment amount, from the debt amount for Financial Debt.


Technical Debt does not require you to pay it back
On the other hand, Technical Debt doesn't hold the properties as discussed above for usual Financial Debt. As Ward Cunningham writes in "Ward Explains Debt Metaphor", you don't need to pay back Technical Debt.


Image by David Castillo Dominici at FreeDigitalPhotos.net
If you don't pay back (i.e. clean up) Technical Debt, you need to keep paying continuous and consistent maintenance cost over time.
We need mathematical models to tie Technical Debt and Software maintenance cost
Also another important property about Technical Debt is it is not straightforward to relate the mainteance cost amount and the Technical Debt amount. For example, if you incrase the number of lines if your software source code, chances are that your maintenance cost might more than double or even triple as a result.

With the advance of today's technologies, it is becoming easier to collect and calculate software metrics, for Technical Debt. For example, simply the number of lines in your code, cyclomatic complexity, frequency of issues from a certain portion of the code, etc.


Images by Janaka Dharmasena and sheelamohana at FreeDigitalPhotos.net
Then you need mathematical models to relate the software metrics to the maintenance cost. Just showing software metrics will not get you anywhere. You need to carefully review the metrics and use them to effectively manage your software maintenance cost.
References
@kellan, "Towards an understanding of technical debt", https://medium.com/@kellan
Ward Cunningham, "Ward Explains Debt Metaphor", Cunningham & Cunningham, Inc.