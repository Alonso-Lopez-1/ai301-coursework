---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

<!--
THIS IS THE PART YOU WRITE, and it is the last one: the frame itself.
Weeks 1 through 3 handed you a working SKILL.md and you filled the
files behind it; this week the frame ships as headings, and you write
what it says. The frontmatter above and the section headings below are
fixed (CONTRACT.md's layout rule); the instructions under each heading
are yours. Write instructions to the tool, in the imperative, the way
weeks 1-3's frames spoke to you: what to read, in what order, what to
refuse, what to emit. Your executor in the rotation is the test: a
frame gap they hit (cannot tell what the tool reads, or how a verdict
gets assembled) is a missing sentence here.

One section is not yours: the JSON schema in "Verdict and output" is
reproduced from CONTRACT.md verbatim and may not be altered. Your
words decide everything around it.
-->

## The question

<!-- State, in your words, the one question this tool answers and what
a PR package is: what artifacts it contains and what they are read
against. CONTRACT.md fixes the question; your frame has to say it so
the tool cannot wander into grading something else. -->
Answer exactly one question for exactly one PR package: is it ready to submit? Compare the candidate title, description, commits, diff, and test evidence with the issue and posted implementation plan. Execute the components of this skill; do not answer based on intuition or evaluate multiple packages at once.


## Inputs and modes

<!-- Define both modes. Live mode: name every input (your plan.md with
its deviation notes, your branch's diff, your draft PR title and
description, your test evidence, your issue), where each comes from,
and what a house-chain student reads instead. The branch's diff is
everything the branch changes relative to the repo's default branch:
`git diff main...HEAD` (three dots), run from the working copy, is
the command that produces it; name the source that concretely. Eval
mode: state that the bundle is the whole world, nothing is fetched,
and every check runs with the full verdict rule. -->
**Live mode:** Evaluate the student's issue URL/thread, `plan.md` including `## Deviations`, committed branch changes from `git diff main...HEAD` (three dots), relevant commit history, `pr_draft.md` title and description, and `test_evidence.md` including Unit 2 before/after reproduction and the repo checks. Consult `.github/PULL_REQUEST_TEMPLATE.md`, `docs/CONTRIBUTING.md`, and applicable issue-thread instructions. For a house-chain student, substitute the instructor-provided issue, plan, reproduction pack and working branch. Do not assume uncommitted edits appear in the PR diff.

**Eval mode:** Grade exactly one supplied practice package. Its issue context, plan-context, diff, commits, test-evidence, description and repo-facts blocks are the entire evidence universe. Do not fetch GitHub data, read local files, or supplement gaps from other sources. Execute every rubric check with the full verdict rule.


## The scope seam (live mode only)

<!-- Tell the tool when to read scope.md, what to do with the rules it
finds there, what to refuse, and what to do when the scope's repo line
is an unfilled placeholder. State that eval mode ignores scope.md
entirely. CONTRACT.md names the required behavior; your frame has to
instruct it. -->
Read `scope.md` before anything else in live mode. Enforce its repository boundary and applicable house rules. If its Repo line is an unfilled placeholder, stop without grading and instruct the student to fill it with their section's Path Review repository. Refuse to grade an out-of-scope repo; never guess the repo. Ignore `scope.md` completely in eval mode.

## The voice seam (live mode only)

<!-- Tell the tool when to read voice-guide.md, which outgoing text it
gates (the PR title and description), how to report a broken rule, and
why it never changes the verdict on its own. State that eval mode
ignores it entirely. -->
Read `voice-guide.md` and compare the proposed PR title and description against its rules. Report any specific broken rule with the offending phrase and suggested adjustment. A voice violation by itself does not change the rubric verdict unless a rubric check expressly reads it. Ignore the voice guide entirely in eval mode.

## Component reads

<!-- Tell the tool how the pieces connect: rubric.md defines the
checks and the verdict rule, references/evidence-guide.md maps where
each evidence family lives, procedure.md is executed as written. Say
what the tool does when the procedure is silent on a step (report the
gap, never improvise around it) and what it does when rubric.md or
procedure.md has no content (the refusal rule, stated as an
instruction). -->
Read `rubric.md` for exact checks, evidence, pass conditions, weights and verdict rule; read `references/evidence-guide.md` for where each evidence family lives; execute `procedure.md` for read order, evidence gathering, check execution and verdict assembly. Preserve names and check order. Report procedural gaps instead of inventing steps. If the rubric has no substantive checks or the procedure has no substantive steps, refuse grading and name the empty component.

## Verdict and output

<!-- State the binary verdict space (accept means submit, reject means
hold) and instruct the tool to end its reply with the fenced JSON
block below, valid and last, with nothing after it. The schema is
CONTRACT.md's, verbatim; do not edit it. -->

The only final verdicts are `accept` (submit) and `reject` (hold). Show a concise per-check summary with evidence, then end the completed grading response with the following fenced JSON block, valid and last, with nothing after it. Preserve this schema exactly:

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```


## Grading discipline

<!-- Write the standing rules the tool grades under: evidence first,
grade the thing not the polish, the rubric decides, the procedure
decides how, and how unclear grades are treated when the rubric's
verdict rule is silent. CONTRACT.md states each as a guarantee; your
frame has to make them instructions. -->
- Evidence first: every grade must cite a decisive fact or quote, not a feeling.
- Grade actual behavior and compliance, not length, formatting or persuasive tone.
- The rubric decides WHAT counts; the procedure decides HOW to assess it. Do not silently revise either during a run.
- Read the original observed issue and reproduction separately from the author's explanation; do not present unverified causes as established.
- Treat `unclear` as directed by the rubric; when silent, an unverifiable required condition fails for verdict purposes.
- An honestly disclosed shortfall is not automatically disqualifying, but disclosure alone cannot replace proof of an asserted result or excuse an explicit requirement.
- Live-only scope and voice rules must never contaminate eval-mode evidence.