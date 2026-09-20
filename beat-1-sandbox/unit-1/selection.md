# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/63

**Verdict output**

| Check | Grade | Evidence |
|---|---|---|
| Maintainer activity | `pass` | Last main commit was `2026-09-16` by human contributor `Aburke225` ("chore: track five more manifest entries…"), 4 days before the run date (`2026-09-20`), which is well within 90 days. |
| Repository in use | `pass` | `isArchived: false` and `pushedAt: 2026-09-16`, so the repository had a push within the last 12 months. No release is required because the push condition satisfies the rule. |
| Newcomer-sized scope | `pass` | One diagnosed bug with a clear reproduction: `test_readme_with_all_quality_signals` asserts `word_count > 100` against a ~51-word fixture. Running `pytest tests/unit/test_readme_scorer.py -q` produces `assert 51 > 100`. The issue is also labeled `good first issue` and `tier-1`. |
| Availability | `pass` | `assignees: []`, no linked PRs appear in the issue timeline, there are zero comments, and the repository has no PRs open or closed. |
| Contribution policy | `pass` | `docs/CONTRIBUTING.md` and `.github/PULL_REQUEST_TEMPLATE.md` contain no restrictions on AI, assistants, or generated code, so the policy check passes. |

  Accepted, and a good fit for your profile: it's a Python/pytest change in an unfamiliar codebase, requiring you to read the scorer's actual behavior
  to decide whether the fixture or the assertion is wrong — bounded, no core internals, no architecture. Note the PR template's checkbox about removing
  a seeded bug's @pytest.mark.xfail marker and any matching suppression in pyproject.toml; check whether this test carries one. Per the Path Review
  house rule, claim it in a comment even if classmates have too.

   {
     "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/63",
     "checks": [
       {"name": "Maintainer activity", "grade": "pass",
        "evidence": "Last default-branch commit 2026-09-16 by human Aburke225, 4 days before today (2026-09-20), within 90 days"},
       {"name": "Repository in use", "grade": "pass",
        "evidence": "isArchived: false and pushedAt 2026-09-16, a push within the last 12 months"},
       {"name": "Newcomer-sized scope", "grade": "pass",
        "evidence": "One diagnosed bug with repro: fixture has ~51 words but test asserts word_count > 100; labeled 'good first issue' and 'tier-1'"},
       {"name": "Availability", "grade": "pass",
        "evidence": "assignees: [], no linked PRs in the issue timeline, zero comments, and the repo has no PRs at all"},
       {"name": "Contribution policy", "grade": "pass",
        "evidence": "docs/CONTRIBUTING.md and .github/PULL_REQUEST_TEMPLATE.md contain no AI-contribution restriction; silence passes"}
     ],
     "verdict": "accept"
   }


**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
paste the output here, including the closing JSON block
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

agreement: 18/20 scored items  (bar: 18/20: PASS)

**Issue analysis**

For issue-19, my rubric returned reject, while the gold label was accept.
The run identified Newcomer-sized scope as the failed check. The issue says,
"There are two potential causes which should be fixed," and then lists multiple
possible changes, including making matchers faster, moving UI work off the
matching thread, and using multiprocessing. I interpreted that as more than one
bounded contribution, so my scope check rejected it. The gold label instead
treated those as related parts of one maintainer-diagnosed performance bug.

**Check rationale**

My current Newcomer-sized scope check says:

"Pass if the issue describes one coherent, implementable task with enough
settled direction for a contributor to begin work. Multiple related fixes or
implementation steps may still pass when they address one clearly diagnosed
bug or behavior. Fail if the issue is an umbrella/tracking task, an open-ended
codebase-wide effort, a pure usage/support question, has an unresolved
product/design decision that must be settled before implementation, or has a
long history of design debate or abandoned attempts without a settled
implementation direction."

I used this wording because I wanted to reject issues that are too broad or still
need major design decisions, while still allowing a bug to have several related
implementation steps. That distinction matters because a first contribution can
involve more than one code change without necessarily being an umbrella task.

**Trade-offs**

This check can still reject a reasonable issue when several related fixes make
the task look broader than it really is. issue-19 is an example: I treated its
multiple causes and suggestions as too much scope, while the gold label treated
them as one coherent performance problem. I accept that this stricter wording
may produce some false negatives in exchange for avoiding issues that are too
open-ended for a first contribution.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. Issue #63 fits my interests because it involves Python and pytest and requires
   me to understand existing behavior before making a small fix. It also looks
   bounded enough to complete within the available time without requiring a
   large architectural change.

2. The verdict correctly identified that the repository is active, the issue is
   unclaimed, and the task has a clear reproduction case. The rubric could not
   weigh how useful the issue would be for me personally, so I also considered
   whether it would give me practice reading unfamiliar test and scoring logic
   rather than only making a trivial text edit.

3. I expect the main difficulty to be understanding whether the test fixture or
   the assertion should be changed, and checking whether the seeded bug has an
   @pytest.mark.xfail marker or related suppression that also needs to be
   removed. Claiming the issue itself should be straightforward because the Path
   Review course rules allow classmates to work on the same issue.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
