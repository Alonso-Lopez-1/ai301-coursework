# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

<!-- Where the environment record lives, and what a sufficient one
looks like against the issue's stated target. -->

**Where it lives:** In an eval bundle, look at the issue context for any
environment or version requirements and at the reproduction report for the
reported operating system, runtime or dependency versions, repository state,
commit, configuration, and setup details. The repo-facts block may provide
repository information that can be compared with the report. In live mode,
compare the issue thread and repository documentation against the environment
described in the student's draft reproduction comment.

**What good looks like:** The package identifies the environment details that
can affect the reported behavior and gives enough information for another
contributor to recreate the relevant setup. When the reporter's environment
differs from the environment named by the issue, the difference is stated
rather than silently treated as equivalent.

## Steps

<!-- Where the reproduction steps live, and what makes them followable
by a stranger, starting state to trigger. -->

**Where it lives:** In an eval bundle, look in the reproduction report for the
starting state, setup actions, commands, inputs, navigation steps, and the
action that triggers the behavior. Read the issue context as a reference for
what behavior the steps are intended to reproduce. In live mode, use the
student's draft reproduction comment together with any setup instructions in
the repository's README, CONTRIBUTING documentation, or other relevant project
documentation.

**What good looks like:** The steps begin from a recognizable starting state
and contain the necessary actions in an order another contributor can follow.
A reader should not need to guess a required command, input, setup action, or
transition in order to reach the reported result.

## Behavior shown

<!-- Where the artifacts live (output excerpts, logs, screenshots),
and what it means for an artifact to show the issue's behavior rather
than an adjacent one. -->

**Where it lives:** In an eval bundle, look at the reproduction report's
terminal output, logs, error messages, screenshots, test results, or other
artifacts and compare them directly with the behavior described in the issue
context. In live mode, inspect the evidence included or referenced by the
student's draft comment and compare it with the original GitHub issue rather
than relying only on the student's interpretation.

**What good looks like:** The artifact shows the same failure, output, state,
or other observable behavior that the issue describes. Evidence of a nearby
problem, a different error, or only the setup leading toward the issue does not
by itself establish that the reported issue was reproduced.

## Honesty

<!-- Where claims and their backing meet: how to tell a report that
says exactly what happened (including an honest cannot-reproduce) from
one that claims more than its evidence shows. -->

**Where it lives:** In an eval bundle, compare the reproduction report's
conclusion and any explanation of cause against its steps and artifacts. In
live mode, compare statements in the student's draft comment with the evidence
the comment provides and with the original issue thread.

**What good looks like:** The conclusion states only what the evidence
demonstrates. A successful reproduction says what behavior was observed, while
an unsuccessful or partial reproduction clearly says that the issue could not
be reproduced as described or was only reproduced under particular conditions.
Root-cause statements are presented as established facts only when the package
contains evidence supporting them; otherwise they are labeled as hypotheses or
left out.

## Comms

<!-- Where the words meet the repo: the claim comment against the
issue, the comments against the repo's stated templates and
contribution policy (including AI-use disclosure requirements), and
what specific-and-honest looks like next to boilerplate. -->

**Where it lives:** In an eval bundle, look at the claim comment and
reproduction report together with the issue context and any contribution-policy
information included in the package. In live mode, compare the student's draft
against the GitHub issue thread, repository templates, CONTRIBUTING
documentation, AI-use policies when present, the skill's scope.md, and
voice-guide.md.

**What good looks like:** The comment is specific to the issue and accurately
describes what the contributor intends to investigate or what they actually
observed. It follows repository and course rules, including any applicable
disclosure requirements, does not claim work that was not performed, and does
not make promises about fixes, deadlines, or causes that the available evidence
cannot support.
