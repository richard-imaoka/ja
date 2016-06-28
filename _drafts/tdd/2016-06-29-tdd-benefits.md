TDD Benefits In TDD, code development is kept within the developer’s intellectual control because he or she is continuously making small design and implementation decisions and increasing functionality at a relatively consistent rate. New functionality is not considered properly implemented unless the new unit test cases and every other unit test cases written for the code base run properly. Some possible benefits of TDD are: 

— Better Design. TDD is considered as much of (and in some cases, more of) a design process than a test process. Kent Beck, the person responsible for the inclusion of TDD in XP and Ward Cunningham, an early proponent of TDD in an XP context, immediately stated, “Test-first coding is not a testing technique” (Beck 2001; Note: the test-first coding practice eventually came to be known as TDD). They assert that TDD Fig. 2 TDD methodology overview Empir Software Eng (2008) 13:289–302 291 is an analysis and design technique and that: “Test-first code tends to be more cohesive and less coupled than code in which testing isn’t part of the intimate coding cycle” (Beck 2001).

 — Efficiency. The fine granularity of test-then-code cycle gives continuous feedback to the developer. With TDD, faults and/or defects are identified very early and quickly as new code is added to the system. Consequently, the source of the problem is also more easily determined since the problems have not been in existence for long. We contend that the efficiency of fault and defect removal and the corresponding reduction in the debugging and maintenance time compensates for the additional time spent writing and executing test cases.

 — Test Assets. The automated unit test cases written with TDD are valuable assets to the project. Subsequently, when the code is enhanced, modified, or updated, running the automated unit tests may be used for the identification of newly introduced defects, i.e., for regression testing. 

— Reducing Defect Injection. Unfortunately, maintenance fixes and “small” code changes may be nearly 40 times more error prone than new development (Humphrey 1989), and often, new faults are injected during the debugging and maintenance phases. The ease of running the automated test cases after changes are made should also enable smooth integration of new functionality into the code base and therefore reduce the likelihood that fixes and maintenance changes introduce new defects. The TDD test cases are essentially a high-granularity, low-level, regression test. By continuously running these automated test cases, one can find out whether a change breaks the existing system early on, rather than leading to a late discovery.

PDF2 Efficiency and Feedback: The fine granularity of the testthen-code cycle gives continuous feedback to the developer. 
Low-Level design: The tests provide a specification of the low level design decision in terms of the classes, methods and interfaces created.
 Reducing Defect Injection. Often with debugging and software maintenance, working code is “patched” to alter its properties and specifications, and designs are neither examined nor updated. Unfortunately, such fixes and “small” code changes may be nearly 40 times more error prone than new development [11]. By continuously running these automated test cases, one can find out whether a change breaks the existing system. 
Test Assets: TDD makes programmers write code that is automatically testable. Such automated unit test cases written with TDD are valuable assets to the project in terms of regression testing [16].

PDF3 such documentation is embedded in the code, thus the lifecycle of code and documentation should merge in only one. 

 it provides an unambiguous and immediate definition of functional quality for the code: if the tests succeed, the code is accepted as good.

 the access is fast: the developer just needs to execute the suite in order to get the content of the documentation, rather than browsing many sheets full of different diagrams.

Kent Beck We need to answer some basic strategic questions before we can talk about the details of how to test:

What do we mean by testing?
When do we test?
How do we choose what logic to test?
How do we choose what data to test?

Test (noun) 
 How do you test your software? Write an automated test.

Test is a verb meaning “to evaluate.” No software engineers release even the tiniest change without testing, except the very confident and the very sloppy. I’ll assume that if you’ve gotten this far, you’re neither. Although you may test your changes, testing changes is not the same as having tests. Test is also a noun, “a procedure leading to acceptance or rejection.” Why does test the noun, a procedure that runs automatically, feel different from test the verb, such as poking a few buttons and looking at answers on the screen?

What follows is an influence diagram, à la Gerry Weinberg’s Quality Software Management. An arrow between nodes means that an increase in the first node implies an increase in the second node. An arrow with a circle means that an increase in the first node implies a decrease in the second node.

What happens when the stress level rises?

This is a positive feedback loop. The more stress you feel, the less testing you will do. The less testing you do, the more errors you will make. The more errors you make, the more stress you feel. Rinse and repeat.

How do you get out of such a loop? Either introduce a new element, replace one of the elements, or change the arrows. In this case we’ll replace Testing with Automated Testing.

“Did I just break something else with that change?” Figure 25.1 shows the dynamic at work. With automated tests, when I start to feel stress, I run the tests. Tests are the Programmer’s Stone, transmuting fear into boredom. “No, I didn’t break anything. The tests are all still green.” The more stress I feel, the more I run the tests. Running the tests immediately gives me a good feeling and reduces the number of errors I make, which further reduces the stress I feel.





Figure 25.1. The “no time for testing” death spiral

“We don’t have time to run the tests. Just release it!” The second picture isn’t guaranteed. If the stress level rises high enough, it breaks down. However, with the automated tests you have a chance to choose your level of fear.

Should you run the test after you write it, even though you know it’s going to fail? No, don’t bother. For example, I was working with a couple of very sharp younger programmers on implementing in-memory transactions (a very cool technique every programming language should have). The question was this: how were we going to implement rollback if we started a transaction, changed a few variables, then let the transaction be garbage collected? Simple enough to test, youngsters. Stand back and watch the master at work. Here is the test. Now how are we going to implement this?

Two hours later — hours marred with frustration because a mistake implementing such low-level features generally crashes the development environment — we rolled back to where we had started. Wrote the test. Ran it on a whim. It passed. Duh…. The whole point of the transaction mechanism wasthat variables weren’t really changed until the transaction was committed. Okay, I suppose you could go ahead and run that new test if you want to.

Isolated Test 
 How should the running of tests affect one another? Not at all.

When I was a young programmer — long, long ago when we had to dig our own bits out of the snow and carry heavy buckets of them barefooted back to our cubicles, leaving bloody little footprints for the wolves to follow…. Sorry, just reminiscing. My first experience of automated tests was having a set of long-running, overnight, GUI-based tests (you know, record the keystrokes and mouse events and play them back) for a debugger I was working on. (Hi Jothy, hi John!) Every morning when I came in, there would be a neat stack of paper on my chair describing last night’s test runs. (Hi Al!) On good days there would be a single sheet summarizing that nothing broke. On bad days there would be many, many sheets, one for each broken test. I began to dread days when I saw a pile of paper on my chair.

I took two lessons from this experience. First, make the tests so fast to run that I can run them myself, and run them often. That way I can catch errors before anyone else sees them, and I don’t have to dread coming in in the morning. Second, I noticed after a while that a huge stack of paper didn’t usually mean a huge list of problems. More often it meant that one test had broken early, leaving the system in an unpredictable state for the next test.

We tried to get around this problem by starting and stopping the system between each test, but it took too long, which taught me another lesson about seeking tests at a smaller scale than the whole application. But the main lesson I took was that tests should be able to ignore one another completely. If I had one test broken, I wanted one problem. If I had two tests broken, I wanted two problems.

One convenient implication of isolated tests is that the tests are order independent. If I want to grab a subset of tests and run them, then I can do so without worrying that a test will break now because a prerequisite test is gone.

Performance is the usual reason cited for having tests share data. A second implication of isolated tests is that you have to work, sometimes work hard, to break your problem into little orthogonal dimensions, so setting up the environment for each test is easy and quick. Isolating tests encourages you to compose solutions out of many highly cohesive, loosely coupled objects. I always heard this was a good idea, and I was happy when I achieved it, but I never knew exactly how to achieve high cohesion and loose coupling regularly until I started writing isolated tests.

Test List 
 What should you test? Before you begin, write a list of all the tests you know you will have to write. The first part of our approach to dealing with programming stress is never to take a step forward unless we know where our foot is going to land. When we sit down to a programming session, what is it we intend to accomplish?

One strategy for keeping track of what we’re trying to accomplish is to hold it all in our heads. I tried this for several years, and found I got into a positive feedback loop. The more experience I accumulated, the more things I knew that might need to be done. The more things I knew might need to be done, the less attention I had for what I was doing. The less attention I had for what I was doing, the less I accomplished. The less I accomplished, the more things I knew that needed to be done.

Just ignoring random items on the list and programming at whim did not appear to break this cycle.

I got in the habit of writing down everything I wanted to accomplish over the next few hours on a slip of paper next to my computer. I had a similar list, but with a weekly or monthly scope, pinned on the wall. As soon as I had all that written down, I knew I wasn’t going to forget something. When a new item came up, I would quickly and consciously decide whether it belonged on the “now” list or the “later” list, or whether it didn’t really need to be done at all.

Applied to test-driven development, what we put on the list are the tests we want to implement. First, put on the list examples of every operation that you know you need to implement. Next, for those operations that don’t already exist, put the null version of that operation on the list. Finally, list all of the refactorings that you think you will have to do in order to have clean code at the end of this session.

Instead of outlining the tests, we could just go ahead and implement them all. There are a couple of reasons writing tests en masse hasn’t worked for me. First, every test you implement is a bit of inertia when you have to refactor. With automated refactoring tools (for example, you have a menu item that renames the declaration and all uses of a variable), this is less of a problem. But when you’ve implemented ten tests and then you discover that the arguments need to be in the opposite order, you are just that much less likely to go clean up. Second, if you have ten tests broken, you are a long way from the green bar. If you want to get to green quickly, you have to throw all ten tests away. If you want to get all of the tests working, then you are going to be staring at a red bar for a long time. If you are sufficiently addicted to the green bar that you can’t go to the bathroom if the bar is red, then that can be an eternity.

Conservative mountain climbers have a rule that of your four hands and feet, three of them must be attached at any one time. Dynamic moves where you let go of two at once are much more dangerous. The pure form of TDD, wherein you are never more than one change away from a green bar, is like that three-out-of-four rule.

As you make the tests run, the implementation will imply new tests. Write the new tests down on the list. Likewise with refactorings.

“This is getting ugly.”

“<sigh> Put it on the list. We’ll get to it before we check in.”

Items that are left on the list when the session is done need to be taken care of. If you are really halfway through a piece of functionality, then use the same list later. If you have discovered larger refactorings that are out of scope for the moment, then move them to the “later” list. I can’t recall ever moving a test case to the “later” list. If I can think of a test that might not work, getting it to work is more important than releasing my code.

Test First 
 When should you write your tests? Before you write the code that is to be tested.

You won’t test after. Your goal as a programmer is running functionality. However, you need a way to think about design, you need a method for scope control.

Let’s consider the usual influence diagram that relates stress and testing (but not stress testing, that’s different): Stress above, negatively connected to Testing below, negatively connected to Stress (see Test(noun) earlier in this chapter). The more stress you feel, the less likely you are to test enough. When you know you haven’t tested enough, you add to your stress. Positive feedback loop. Once again, there needs to be a way to break the loop.

What if we adopted the rule that we would always test first? Then we could invert the diagram and get a virtuous cycle: Test-First above negatively connected to Stress below, negatively connected to Test-First.

When we test first, we reduce the stress, which makes us more likely to test. There are lots of other elements feeding into stress, however, so the tests must live in other virtuous cycles or they will be abandoned when stress increases enough. But the immediate payoff for testing — a design and scope control tool — suggests that we will be able to start doing it, and keep doing it even under moderate stress.

Assert First 
 When should you write the asserts? Try writing them first. Don’t you just love self-similarity?

Where should you start building a system? With stories you want to be able to tell about the finished system.
Where should you start writing a bit of functionality? With the tests you want to pass with the finished code.
Where should you start writing a test? With the asserts that will pass when it is done.

Jim Newkirk introduced me to this technique. When I test assert-first, I find it has a powerful simplifying effect. When you are writing a test, you are solving several problems at once, even if you no longer have to think about the implementation.

Where does the functionality belong? Is it a modification of an existing method, a new method on an existing class, an existing method name implemented in a new place, or a new class?
What should the names be called?
How are you going to check for the right answer?
What is the right answer?
What other tests does this test suggest?

Pea-sized brains like mine can’t possibly do a good job of solving all of these problems at once. The two problems from the list that can be easily separated from the rest are, “What is the right answer?” and “How am I going to check?”

Here’s an example. Suppose we want to communicate with another system over a socket. When we’re done, the socket should be closed and we should have read the string abc.

testCompleteTransaction() {
   ...
   assertTrue(reader.isClosed());
   assertEquals("abc", reply.contents());
}




Where does the reply come from? The socket, of course:

testCompleteTransaction() {
   ...
   Buffer reply= reader.contents();
   assertTrue(reader.isClosed());
   assertEquals("abc", reply.contents());
}




And the socket? We create it by connecting to a server:

testCompleteTransaction() {
   ...
   Socket reader= Socket("localhost", defaultPort());
   Buffer reply= reader.contents();
   assertTrue(reader.isClosed());
   assertEquals("abc", reply.contents());
}




But before this, we need to open a server:

testCompleteTransaction() {
   Server writer= Server(defaultPort(), "abc");
   Socket reader= Socket("localhost", defaultPort());
   Buffer reply= reader.contents();
   assertTrue(reader.isClosed());
   assertEquals("abc", reply.contents());
}




Now we may have to adjust the names based on actual usage, but we have created the outlines of the test in teeny-tiny steps, informing each decision with feedback within seconds.

Test Data 
 What data do you use for test-first tests? Use data that makes the tests easy to read and follow. You are writing tests to an audience. Don’t scatter data values around just to be scattering data values around. If there is a difference in the data, then it should be meaningful. If there isn’t a conceptual difference between 1 and 2, use 1.

Test Data isn’t a license to stop short of full confidence. If your system has to handle multiple inputs, then your tests should reflect multiple inputs. However, don’t have a list of ten items as the input data if a list of three items will lead you to the same design and implementation decisions.

One trick in Test Data is to try never to use the same constant to mean more than one thing. If I am testing a plus() method, it is tempting to test 2 + 2, because that is the classic example of addition, or 1 + 1, because that is so simple. What if we got the arguments reversed in the implementation? (Okay, okay, that doesn’t matter in the case of plus(), but you get the idea.) If we use 2 for the first argument, for example, then we should use 3 for the second argument. (3 + 4 was a watershed test case when bringing up a new Smalltalk virtual machine back in the olden days.)

The alternative to Test Data is Realistic Data, in which you use data from the real world. Realistic Data is useful when:

You are testing real-time systems using traces of external events gathered from the actual execution
You are matching the output of the current system with the output of a previous system (parallel testing)
You are refactoring a simulation and expect precisely the same answers when you are finished, particularly if floating point accuracy may be a problem

Evident Data 
 How do you represent the intent of the data? Include expected and actual results in the test itself, and try to make their relationship apparent. You are writing tests for a reader, not just the computer. Someone in decades to come will be asking him- or herself, “What in the heck was this joker thinking about?” You’d like to leave as many clues as possible, especially if that frustrated reader is going to be you.

Here’s an example. If we convert from one currency to another, we take a 1.5 percent commission on the transaction. If the exchange rate from USD to GBP is 2:1, then if we exchange $100, we should get 50 GBP — 1.5% = 49.25 GBP. We could write this test like this:

Bank bank= new Bank(). 
bank.addRate("USD", "GBP", STANDARD_RATE);
bank.commission(STANDARD_COMMISSION);
Money result= bank.convert(new Note(100, "USD"), "GBP");
assertEquals(new Note(49.25, "GBP"), result);




or we could try to make the calculation obvious:

Bank bank= new Bank(); 
bank.addRate("USD", "GBP", 2);
bank.commission(0.015);
Money result= bank.convert(new Note(100, "USD"), "GBP");
assertEquals(new Note(100 / 2 * (1 - 0.015), "GBP"), result);




I can read this test and see the connection between the numbers used in the input and the numbers used to calculate the expected result.

One beneficial side effect of Evident Data is that it makes programming easier. Once we’ve written the expression in the assertion, we know what we need to program. Somehow we have to get the program to evaluate a division and a multiplication. We can even use Fake It to discover where the operations belong incrementally.

Evident Data seems to be an exception to the rule that you don’t want magic numbers in your code. Within the scope of a single method, the relationship between the 5’s is obvious. If I had symbolic constants that were already defined, though, I would use the symbolic form.