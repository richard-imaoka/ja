Software Metrics and Harmful Optimization
When you set your goal as improving some metrics, consider whether it leads to wrong optimization.
For example, if set your development team’s target as maximizing “the number of releases per week”, people could rush to release too early, even if the released feature is not well tested. Then, the next release to fix the previous release also counts. That’s wrong optimization to maximize the number of releases per week.
One way to avoid wrong optimization is to introduce other metrics as constraint. You can set a goal like:
Goal: Maximize the number of releases, as long as test coverage > 80%
Also, you can introduce procedures to prevent wrong optimization. For the above case, you can let developers do pair-programming, peer code-reviews, or test first development, etc.
Still, metrics and procedures themselves do not lead you to your goal. There are still pitfalls. You need to make effort to use them right. For test coverage, you can still make a test case that never happens in real use, but just to pass the test and to increase the coverage. Also, peer-review can be sloppy if everyone just wants to maximize the number of releases.
Remember your ultimate goal cannot be measured by metrics. Your ultimate goal would be like “add customer value through technologies”. Or it could be an image or vision about how your company should be.
Pay attention to wrong optimization. Make effort to correctly use metrics, and constraint (other metrics and procedure).