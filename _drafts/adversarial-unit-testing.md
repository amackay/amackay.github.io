---
published: false
---
## Adversarial unit testing

I have written plenty of unit tests in my time as a software engineer. On the face of it, unit testing seems like a pretty dry topic. You write a bunch of tests for various edge cases, to make sure that the software is implemented properly. I think many developers see test-writing as boring, and least compared to the more interesting task of actually implementing the software.

I like to think of testing as a contest. Long before I worked in the software industry, I did some programming practice by participating in [TopCoder programming contests](https://www.topcoder.com/community/arena). In a contest round, after contestants have spent most of their time implementing solutions to the problems, there is a "[Challenge Phase](https://www.topcoder.com/thrive/articles/How%20To%20Compete%20in%20SRMs#6)". In this phase, you can inspect other people's code and suggest a test case that would prove that their implementation is incorrect. If you succeed, you earn some points for coming up with the tricky test case, and the test case is added to the test suite that all contestants' code must pass.

As a naturally competitive person, this way of thinking about testing has stuck with me. In an abstract ideal case, we could think of testing as a game with two players - the diligent tester and the lazy implementer.

The implementer wants to write code that passes all the tests, but apart from that doesn't care about code correctness, and so will put in the minimum amount of effort to pass the tests. So if there is a tricky edge case, they won't bother accounting for it unless there is a test for it.

The tester wants the implementer to write a correct implementation, but can only influence the implementation by writing tests. The tester is not lazy, so they are happy to write many many tests, but they still won't bother with completely redundant tests. Writing the exact same test multiple times wouldn't serve any purpose.

The tester and implementers interests differ, but they aren't diametrically opposed. For example, if faced with a comprehensive test suite, the implementer could hypothetically still write incorrect code, by writing an almost correct implementation that purposely returns the wrong value only when there is some very specific set of input values... but they wouldn't bother with that, since writing a correct implementation would be less effort at that point. So it's effectively a non-zero-sum game.

