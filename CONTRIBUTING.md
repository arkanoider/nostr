# Contributing

##  Contribution Workflow

The codebase is maintained using the "contributor workflow" where everyone
without exception contributes patch proposals using "pull requests". This
facilitates social contribution, easy testing and peer review.

To contribute a patch, the workflow is a as follows:

  1. Fork Repository
  2. Create topic branch
  3. Commit patches

In general commits should be atomic and diffs should be easy to read.
For this reason do not mix any formatting fixes or code moves with actual code
changes. Further, each commit, individually, should compile and pass tests, in
order to ensure git bisect and other automated tools function properly.

When adding a new feature, thought must be given to the long term technical
debt.
Every new feature should be covered by unit tests where possible.

When refactoring, structure your PR to make it easy to review and don't
hesitate to split it into multiple small, focused PRs.

Commits should cover both the issue fixed and the solution's rationale.
These [guidelines](https://chris.beams.io/posts/git-commit/) should be kept in mind.

To facilitate communication with other contributors, the project is making use
of GitHub's "assignee" field. First check that no one is assigned and then
comment suggesting that you're working on it. If someone is already assigned,
don't hesitate to ask if the assigned party or previous commenters are still
working on it if it has been awhile.

## Deprecation policy

Where possible, breaking existing APIs should be avoided. Instead, add new APIs and
use [`#[deprecated]`](https://github.com/rust-lang/rfcs/blob/master/text/1270-deprecation.md)
to discourage use of the old one.

Deprecated APIs are typically maintained for one release cycle. In other words, an
API that has been deprecated with the 0.10 release can be expected to be removed in the
0.11 release. This allows for smoother upgrades without incurring too much technical
debt inside this library.

If you deprecated an API as part of a contribution, we encourage you to "own" that API
and send a follow-up to remove it as part of the next release cycle.

## Unwrap and expect

Usage of `.unwrap()` or `.expect("...")` methods is allowed **only** in `examples` or `tests`.

## Peer review

Anyone may participate in peer review which is expressed by comments in the
pull request. Typically reviewers will review the code for obvious errors, as
well as test out the patch set and opine on the technical merits of the patch.
PR should be reviewed first on the conceptual level before focusing on code
style or grammar fixes.

### Terminology

Concept ACK - Agree with the idea and overall direction, but haven't reviewed the code changes or tested them.

utACK (untested ACK) - Reviewed and agree with the code changes but haven't actually tested them.

tACK (tested ACK) - Reviewed the code changes and have verified the functionality or bug fix.

ACK - A loose ACK can be confusing. It's best to avoid them unless it's a documentation/comment only change in which case there is nothing to test/verify; therefore the tested/untested distinction is not there.

NACK - Disagree with the code changes/concept. Should be accompanied by an explanation.

## Coding Conventions

Use `make check` to format code and check the code before committing.
This is also enforced by the CI.

## Going further

You may be interested by Jon Atacks guide on [How to review Bitcoin Core PRs](https://github.com/jonatack/bitcoin-development/blob/master/how-to-review-bitcoin-core-prs.md)
and [How to make Bitcoin Core PRs](https://github.com/jonatack/bitcoin-development/blob/master/how-to-make-bitcoin-core-prs.md).
While there are differences between the projects in terms of context and
maturity, many of the suggestions offered apply to this project.