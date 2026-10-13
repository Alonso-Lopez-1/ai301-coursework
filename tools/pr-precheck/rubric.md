# Rubric: is this pull request ready to submit?

<!--
THIS IS THE PART YOU WRITE (fourth week running; this is the rubric's
final form in the sandbox). Your frame in SKILL.md executes whatever
checks you define here, via your procedure.md. It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the diff read against the plan's scope, the test
     evidence read against the plan's test plan, the description read
     against the diff, the repo-facts block's template asks) or a
     location from your references/evidence-guide.md. "The PR" is not
     a source; "the diff's changed files read against the plan's
     stated boundary" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself
     (does the diff fall inside the plan plus its deviation notes? is
     the claimed evidence observable?), never the write-up's shape
     (how long the description is, how many commits there are).
     Structure-shaped checks are what make graders disagree with
     themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (submit) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. State the `unclear`
   treatment explicitly: the frame here is YOUR SKILL.md, so a rubric
   that stays silent is only covered if your frame's grading
   discipline says what happens (the contract's own default is that
   an unverifiable claim fails).

Cover what actually gets bad PRs submitted. The failure families the
lecture named ARE the harness's scoring categories, same names as the
eval README: silent drift (the diff silently does more or less than
the posted plan, or the description claims fidelity the diff
contradicts), not tested (the evidence proves nothing observable, or
the repo's own checks were never run), unreviewable (debris or
unrelated hunks bury the change), and standards wall (the repo's
stated template and disclosure asks are ignored). Your evidence
guide's four headings map onto these one to one (plan fidelity =
silent drift, test evidence = not tested, diff quality =
unreviewable, standards and comms = standards wall), and the category
floor is scored on exactly these names plus clear accept. A rubric
that ignores a category will fail the eval packages built around
that category. And remember the honest-outcome
rule, fourth week running: a PR that honestly discloses a shortfall
can be ready; a rubric that equates "less than everything" with
"hold" fails the set.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Plan fidelity | Candidate diff's changed files and behavior against the plan-context scope, exclusions, intended implementation, issue, and documented deviations | All material changes serve the issue and fit the planned boundary or explicitly explained deviations; significant omissions are accurately disclosed. Unexplained additions or omissions fail. Disclosing unrelated drive-by changes does not make them in scope. | required |
| Description accuracy | Candidate PR title and description, including Changes and Notes, compared with the unified diff, plan and deviation notes, and test evidence | Claims about implementation, remaining work, and results agree with what the diff and evidence establish. No meaningful change or limitation is silently misrepresented. | required |
| Reproduction evidence | Plan-context test plan and issue reproduction evidence compared with candidate test-evidence before/after commands, outcomes, and relevant code path | Evidence identifies the behavior tested, how it was tested, and observable outcome relevant to the planned fix. Before/after results demonstrate the claimed change where applicable; any absent or inconclusive result is disclosed without claiming an unproved fix. A generic 'tests pass' assertion alone fails. | required |
| Repository checks | Repo-facts required commands and contribution rules compared with recorded candidate test-evidence outputs | Each applicable repository check has a recorded, observable result, or a specific, credible explanation for why it could not run. Failure or no-tests-ran is reported accurately and is not automatically disqualifying unless repository policy requires success; silently omitted checks or unsupported success claims fail. | required |
| Diff quality | Unified diff and commits compared with issue and planned implementation boundary | Changes are relevant and reviewable, without unrelated hunks, accidental artifacts, debug output, abandoned or commented-out code, or substantial needless formatting churn. Necessary supporting edits pass. | required |
| Repository standards | Repo-facts template asks, stated contribution and AI policies, issue-thread instructions, compared with candidate title and PR description | Applicable mandatory template sections and disclosures are substantively addressed, including AI-use disclosure where required; explicit maintainer instructions are respected. Boilerplate that evades a requirement fails. | required |



## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

Grade every check `pass`, `fail`, or `unclear` based on the named evidence. `pass` means the pass condition is established; `fail` means the evidence demonstrates a violation or required omission; `unclear` means the supplied evidence is insufficient to determine whether the condition holds.

Return `accept` only if every required check passes. Return `reject` if any required check fails or is unclear; for verdict purposes treat `unclear` as fail. Preferred checks, if later added, never alter the verdict. Do not treat an honestly disclosed shortfall as an automatic rejection: evaluate whether the underlying check is satisfied, whether evidence establishes the claimed outcome, and whether any applicable repository requirement requires more. Do not give a free pass to missing proof merely because its absence was acknowledged.