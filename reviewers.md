## Be Kind, Be Humble

https://en.wikipedia.org/wiki/Golden_Rule

https://github.com/corollari/linusrants (don't do this)

_Never_ use ad hominem.

**not preferable**

> You clearly do not understand the system. Give up. Become a peanut farmer.

**preferable**

> Overall good job :thumbsup: This line, however, seems to differ from the spec. Could you explain this part to me?

## Code Review Does Not Put People Down, It Brings People Up

https://habr.com/en/post/440736/

It can be quite easy to assume any criticism is a personal attack. We can use certain phrasing to make our reviews seems less like personal attacks. Avoid making sweeping label statements about a person's identity and focus on the **outcomes** and **impact** of the code, not the person.

**not preferable**

> **You** missed x thing in the feature.
> 
> **You** have a lack of attention to detail.
> 
> **Your** code is hard to understand.

**preferable**

> The feature spec lists x, **it** does not seem to be included here though.
> 
> **I** am having a hard time understanding this, could you help me?
> 
> Do you think **we** should strive for better code coverage in this feature?

## No Nitpicking

https://en.wikipedia.org/wiki/Law_of_triviality

We shouldn’t spend a lot of time on things that can be automated in tooling or codified in a style guide or trivial cosmetic changes.

**not preferable**

> Can we use tabs instead of spaces?
>
> Can we use absolute imports here?
> 
> Can we alphabetically arrange the variables?

## Do Not Ask Submitters To Fix Large Unrelated Issues

If they didn’t cause it, there should be no reason for them to fix it. We can defer the task for later. A deferrable task is intrinsically a low-priority task. If you spot something that should be fixed, but was not introduced in the PR, raise an issue and share with the team at a later time.

For small issues the reviewer can suggest that the submitter include the fix in the PR, but this is optional.

**not preferable**

> Not introduced here, but could you fix X, Y, Z?

**preferable**

> I see there is an issue on line 9, although it was not introduced in this commit. I raised an issue for this which we can fix at another time.

## Ask Questions, Use The Socratic Method

The [Socratic Method](https://en.wikipedia.org/wiki/Socratic_method) is

> a form of cooperative argumentative dialogue between individuals, based on asking and answering questions to stimulate critical thinking and to draw out ideas and underlying presuppositions.

Put simply, it is preferable for a reviewer to ask questions during a code review in order to gain insight on the submitter’s thought process and intent. An additional benefit to this method is that if the submitter actually had no specific intent, asking questions about the solution can reveal to the submitter that their solution, perhaps, is not optimal.

Asking a question also seems much less of a personal attack.

**not preferable**

> This isn’t the right pattern to use.

**preferable**

> I see you have chosen this pattern. Could you please explain the pros/cons of pattern A vs pattern B?

## There is No “Perfect” Code, Only Better Code

https://en.wikipedia.org/wiki/Perfect_is_the_enemy_of_good

To quote the [google code review guidelines](https://google.github.io/eng-practices/review/reviewer/standard.html)

> There is no such thing as “perfect” code—there is only better code. Reviewers should not require the author to polish every tiny piece of a PR before granting approval. Rather, the reviewer should balance out the need to make forward progress compared to the importance of the changes they are suggesting. Instead of seeking perfection, what a reviewer should seek is continuous improvement.

**not preferable**

> No, my way is still right because of X, Y. [offers no solution to move forward]

**preferable**

> I see we have some disagreements on which pattern is the most idiomatic and correct. How about I create a guideline doc that we can follow in the future? For now, I will approve the PR and perhaps we can refactor in the next PR :thumbsup:

## Technical Facts Take Precedence Over Personal Preferences

https://en.wikipedia.org/wiki/Fredkin%27s_paradox

If there are any number of equally arbitrary options from which to choose, any implementation will therefore also be arbitrary. A codebase is more easily understandable when it is rooted in technical facts rather than arbitrary decisions.

An argument that is not based on technical facts and data is considered a personal preference.

If there are a number of arbitrary solutions to a problem, the solution that is codified in documentation takes precedence. If there is no documentation, the current implementation style should be considered idiomatic.

**not preferable**

> A + B + C is better than C + B + A, and also better than B + A + C.

**preferable**

> Due to [some technical facts and/or presented data], solution A is preferable to solution B.

Suggestions to make code “cleaner” must always be supported with evidence that one of (but not limited to) the following will happen

- the logic becomes simpler
- performance is improved
- the implementation follows a standard design pattern

Simply moving around logic into separate functions does not inherently make a codebase “cleaner”

## Always Move Forward (Know When To Defer Tasks)

It is not preferable to block a PR from being merged, for reason that can be handled at a later time. Sometimes it is not preferable to defer a task for later. Use your judgement.

**not preferable**

> You know we could have written this test with pattern B instead of pattern A? Redo it.

**preferable**

> The test in this PR seems to pass :ok_hand: . I think I should have explained that it is preferable to use pattern B over pattern A. I raised a ticket to refactor this in the future, as a working test is still beneficial.

## Adhere To The Designed Spec

Do not usurp the role of the product manager by asking the submitter to add unplanned features and enhancements. Do not ask for corrections for unplanned and impossible edge cases. Required tests should be part of the grooming process to determine what the critical test paths are.

**not preferable**

> Can you also include this behavior? It will make it better for the user.

**preferable**

> For now this is good :ok_hand:, but I think we could improve upon the UX at a later phrase. Let me raise a ticket and clarify with the product manager and designer.
