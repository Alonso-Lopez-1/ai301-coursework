# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Diagnosis grounded in reproduction | Candidate plan diagnosis read against the repro-evidence block and issue context | Pass if the plan's stated cause follows from the behavior demonstrated by the reproduction evidence and does not contradict, ignore, or replace that evidence with an unsupported explanation. | required |
| Scope is bounded | Candidate plan scope statement, not-in-scope statement, named files or areas, and issue context | Pass if the plan describes one coherent change that addresses the reproduced problem and clearly limits what will not be changed. Fail if it introduces unrelated refactors, migrations, redesigns, documentation work, or other changes that are not necessary to address the diagnosed problem. | required |
| Plan is executable | Candidate plan files or areas, approach, implementation steps, and stated unknowns | Pass if another contributor could begin implementing the change from the plan without needing to ask the author what file or area to inspect, what behavior to change, or what general implementation approach to take. | required |
| Test plan is decisive | Candidate plan test plan read against the repro-evidence steps and observed behavior | Pass if the test plan reuses or directly maps to the reproduced behavior and states an observable expected result that would demonstrate the fix worked. Fail if it only says to run tests, verify the fix, or otherwise provides no specific expected outcome. | required |
| Risks and unknowns are honest | Candidate plan risks, unknowns, assumptions, and any deviation notes | Pass if uncertainty that could affect the implementation is stated as an uncertainty rather than presented as established fact, and any known limitation or deviation is recorded instead of silently ignored. | required |
| Plan comment matches the plan and thread | Candidate plan comment read against the candidate plan, issue thread or thread highlights, repo-facts block, and applicable contribution guidance | Pass if the comment accurately summarizes the diagnosis, intended change, and validation approach contained in the plan, does not promise work outside the plan, and respects explicit maintainer direction and repository contribution conventions. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->
Accept a plan package only if every required check passes.
Reject the package if any required check fails.
Treat unclear as fail for required checks because a plan should contain enough evidence and implementation detail for another contributor to determine whether it is ready to post and build from without guessing.
Preferred checks, if added later, do not affect the verdict.
