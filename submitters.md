## Be Humble, Be Respectful

Remember, code review should never be used a personal attack! We’re all in this together to ensure the long-term stability of our products.

**preferred**

> Reviewer: “There seems to be a typo here”
> Submitter: “Thanks! Fixed”

**not preferred**

> Reviewer: “There seems to be a typo here”
> <> Submitter: “I hate yuo, grammar nazi!”

If the reviewer points out something that isn’t correct, this guideline also applies

**preferred**

> Reviewer: “If we change this to X, will it still work?”
> Submitter: “Good point, actually this will not work because Y”

**not preferred**

> Reviewer: “If we change this to X, will it still work?”
> Submitter: “Of course not u smooth brain monke, maybe u should go back to the jungle”

## Proofread Your Own Diffs

To quote Robert C. Martin in Clean Code: A Handbook of Agile Software

> Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer’s intent but rather is full of crisp abstractions and straightforward lines of control.

Have you ever had to doublecheck and proofread your taxes, important forms, important emails sent to clients, presentations…anything? Code is no exception. Submitting your draft MR and re-reading the diff is a great way to catch mistakes before you ask for review.

Proofreading also allows you to read the diff as if you were the reviewer; the diff should be just as clear to you as it is to anybody else. Take a small break, then come back and re-read your diff. If you find anything confusing, the reviewer will definitely find it confusing as well.

## Submit Drafts Early

If you are working on a ticket and come across a code smell or something you think can be implemented in a number of ways it can be beneficial to raise a draft MR early and leave comments asking for help or advice. If it happens you chose a non-optimal solution and were asked to re-work your entire MR during review, seeking guidance early on can save you a lot of time and wasted effort.

You could also consider drafting a RFC or design doc and gathering feedback before implementation. Large features and refactors often benefit from this level of planning.

**preferable**

> I started working on this, and I noticed it could be achieved in ways x, y, z. Which do you think is the best? Here are pros/cons why I think X is better than Y and Z…

## Keep Your Diffs Precise

The goal of any PR should be to modify the required code with surgical precision. This means:

- Generally the PR should contain one commit.
- Do not add unnecessary changes such as refactors or unplanned features.
- Ensure your diff is as small and surgically precise as possible

There are a number of great benefits we receive if we follow this guideline:

- The smaller the PR, the faster we can review it. This saves us all valuable time.
- The smaller the diff, the less chance it has of causing regression issues. Again, that saves time for not only devs but QA team, PM, etc.

## Use the PR Itself To Document Questions & Code Smells

Instead of asking big questions in slack, open a draft MR and methodically piece together your well-articulated question in the context of the code itself.

Code smells that are **necessary** for an implementation should be thoroughly documented and commented.

- If a line of code appears not to make any sense but it is necessary, leave a comment in the codebase
- If the implementation you have chosen is “moderately smelly” it greatly helps to leave a note explaining your implementation as a comment in the PR. This saves the reviewer a lot of time as they won’t have to guess what the submitter’s thought process and reasoning for the implementation was.

## Add Replays/Screenshots

If your PR includes style/design changes, it is helpful for the reviewer if the submitter shows proof that the changes are satisfactory. In many cases, simple screenshots are fine.

Make it easy for your reviewer. Include a before/after screenshot for styling changes.

In some cases, including a replay can be more useful as viewers can inspect the css directly.
