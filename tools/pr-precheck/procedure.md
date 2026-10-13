# Procedure: how this tool grades a PR package

<!--
THIS IS THE PART YOU WRITE (second week running for the procedure).
Week 3 you wrote these steps for a plan package; this week the graded
object is a PR package, and the read that matters most is a
side-by-side: the diff against the plan, the evidence against the test
plan, the description against both. Your week-3 procedure is the
pattern; do not paste it unchanged, because its read order was built
for a different object.

Your rotation is the design brief again, and this week friction routes
three ways: a stall on WHAT to decide is a rubric gap, a stall on
WHERE to look is a procedure gap (this file), and a stall on what the
tool even reads or outputs is a frame gap (your SKILL.md). A complete
procedure lets someone who has never seen a PR package before grade
one exactly the way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
plan's scope pair before opening the diff, and list the files the plan
names" is a step; "understand the change" is a wish.
-->

## Read order

<!-- What gets read, in what order, before any check is graded, and
what to note down from each part while reading. A complete procedure
decides where the plan sits in the order (before the diff? before the
description?) and says why the order matters for the side-by-side
checks that come later. -->
1. Determine live or eval mode. In live mode read `scope.md` first and enforce its repository boundary. In eval mode use only the supplied bundle; fetch nothing.
2. Read issue context and reproduction evidence first. Record the observed failure, steps/inputs, expected behavior, and relevant maintainer constraints. In live mode use the issue thread and the student's Unit 2 reproduction (or the house reproduction pack). In eval mode use the corresponding bundle context and reproduction details if supplied.
3. Read the plan-context scope, exclusions, proposed implementation, and test plan; record documented deviations and their reasons. Do not infer a broader scope from the later diff.
4. Read the applicable repo-facts template, checks, policy, and thread requirements (or the live PR template, `docs/CONTRIBUTING.md`, and issue thread).
5. Read the candidate unified diff and commit list (live: `git diff main...HEAD` and relevant committed history). Record actual changed files and observable behavioral edits. Do not count uncommitted working-tree edits as part of the PR.
6. Read test evidence (live: `test_evidence.md`) and match commands and results to the original reproduction and plan's test plan.
7. Finally read the PR title and description (live: `pr_draft.md`), record factual claims, required template sections, disclosures, and stated limitations. Read claims last to avoid letting the description redefine what the implementation or tests prove. Do not grade until this initial read is complete.



## Evidence gathering

<!-- For each evidence family your rubric's checks name, the concrete
gathering move: which part of the package (or, live, which file, diff,
or page per your evidence guide) to pull the fact from, and what to
record. The load-bearing gathers this week are pairings: diff files
against plan scope, claimed evidence against the plan's test plan and
the repo's checks, description claims against diff contents. A
complete procedure leaves no check whose evidence an executor would
have to hunt for. -->
1. **Plan fidelity:** Construct a scope comparison: each substantive changed file/hunk and any planned but undelivered behavior, its plan or deviation reference, and whether it serves the issue. Record unexplained additions/omissions and unrelated changes separately.
2. **Description accuracy:** Match each material title/description claim to corresponding diff evidence and each testing claim to recorded results. Record contradictions and undisclosed limitations, without penalizing mere brevity.
3. **Reproduction evidence:** Pair the Unit 2 reproduction's steps and observed failure with the plan's expected-after behavior and the submitted before/after results. Record exact commands, outputs, outcome, and any explicit inability to reproduce or retest. Do not invent a before result when only an after result is provided.
4. **Repository checks:** List each applicable check from repo-facts or repository policy. Next to each, record the test-evidence command and observable result or a specific reason execution was impossible. Separate a failed or no-tests-ran result from a check that was never evidenced.
5. **Diff quality:** Inspect diff hunks and commits for debug statements, dead code, accidental generated files, unrelated refactors and formatting churn; record affected hunks and whether each edit is essential to the fix.
6. **Repository standards:** Match each mandatory PR-template ask, contributing rule, AI disclosure requirement, and specific maintainer direction with the actual PR response. Identify omissions or placeholder answers by name.

Use `references/evidence-guide.md` for the exact live and eval locations. If an evidence family cannot be located, report the location gap rather than inventing data or a replacement workflow.



## Check execution

<!-- How one check runs against gathered evidence: in what order the
checks execute, what an executor does when evidence for a check is
genuinely absent, and when a check may be graded without re-reading
the whole package. A complete procedure makes two executors grade the
same package the same way. -->
1. Execute all checks in rubric order: Plan fidelity, Description accuracy, Reproduction evidence, Repository checks, Diff quality, Repository standards.
2. For each, consult the exact evidence specified in its rubric row. Apply the written pass condition to the gathered facts; do not create additional checks or substitute general impressions.
3. Assign `pass` for demonstrated satisfaction, `fail` for an observed violation or required omission, and `unclear` when the evidence cannot determine satisfaction. Record a concise decisive fact, quote or comparison for each grade.
4. An honest disclosed shortfall is not a blanket failure or blanket pass. Determine whether the particular pass condition is satisfied and whether the repository actually requires successful execution.
5. Complete all checks even if one fails. Revisit a source only if gathered evidence is insufficient or contradictory; do not reread everything without a specific reason.
6. If the rubric or procedure is substantively empty, refuse grading. If a step is missing from this procedure, report the gap rather than silently improvising.



## Verdict assembly

<!-- How the per-check grades become the final accept or reject:
apply your rubric's verdict rule, state how unclear grades enter it,
and say what gets quoted in the output for the deciding check: the
check whose failure the verdict turned on. When more than one check
failed, your procedure picks which one gets quoted (first failing
required check in rubric order is a fine rule); nothing picks it for
you, so write the rule down. A complete procedure produces the same
verdict from the same grades, every time. -->
1. Apply the `rubric.md` verdict rule to all checks: accept only when every required check passes; reject for any required `fail` or `unclear`. Preferred checks do not affect the verdict.
2. On rejection, identify the first failing or unclear required check in rubric order as the primary deciding check, quote its decisive evidence, and also summarize all other grades.
3. On acceptance, summarize what evidence supports readiness, without exaggerating results. In live mode separately report violations of `voice-guide.md`; those affect the verdict only if a rubric check explicitly makes them decisive.
4. Emit a readable per-check summary and end with the exact fenced JSON block from `SKILL.md`/`CONTRACT.md`. Preserve check names, the `item`, `checks`, and `verdict` fields and the binary `accept`/`reject` space. Output nothing after that block.