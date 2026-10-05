# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

<!-- What gets read, in what order, before any check is graded, and
what to note down from each part while reading. A complete procedure
decides the order (issue first? repro evidence first?) and says why
the order matters for the checks that come later. -->
1. In eval mode, read the issue context first to understand the reported problem and any constraints or maintainer direction that the plan should respect. In live mode, read `scope.md` first as required by the skill, then read the issue thread.

2. Read the reproduction evidence before reading the candidate plan. Record the specific behavior that was reproduced, the steps or inputs that produced it, and any evidence that limits what can reasonably be claimed about the cause.

3. Read the candidate plan from beginning to end. Note the stated diagnosis, in-scope and not-in-scope boundaries, files or areas to be changed, implementation approach, test plan, risks, unknowns, and any recorded deviations.

4. Read the candidate plan comment after the plan. Note what cause, implementation work, validation approach, or other commitments the comment communicates to maintainers.

5. Read the repo-facts block and thread highlights in eval mode, or the applicable repository contribution documentation and maintainer comments in live mode, before grading communication-related checks.

6. Do not grade any check until the initial read is complete. Reading the reproduction evidence before the plan prevents the plan's explanation from influencing the interpretation of what was actually reproduced.


## Evidence gathering

<!-- For each evidence family your rubric's checks name, the concrete
gathering move: which part of the package (or, live, which page or
thread location per your evidence guide) to pull the fact from, and
what to record. A complete procedure leaves no check whose evidence an
executor would have to hunt for. -->
1. For the diagnosis check, record the candidate plan's stated cause and the specific behavior demonstrated by the reproduction evidence. Compare the two and note whether the evidence supports, contradicts, or does not establish the stated cause.

2. For the scope check, record the plan's in-scope statement, not-in-scope statement, named files or areas, and proposed implementation work. Note any planned work that does not directly support the reproduced issue.

3. For the executability check, record the files or areas the plan identifies, the implementation approach, the intended order of work when provided, and any dependencies or unknowns that could prevent someone from starting.


## Check execution

<!-- How one check runs against gathered evidence: in what order the
checks execute, what an executor does when evidence for a check is
genuinely absent, and when a check may be graded without re-reading
the whole package. A complete procedure makes two executors grade the
same package the same way. -->
1. Execute the rubric checks in this order: Diagnosis grounded in reproduction, Scope is bounded, Plan is executable, Test plan is decisive, Risks and unknowns are honest, and Plan comment matches the plan and thread.

2. For each check, use only the evidence source named by that rubric row and the corresponding guidance in `references/evidence-guide.md`.

3. Compare the gathered evidence directly with the check's pass condition. Grade the check `pass` only when the evidence satisfies the stated condition.

4. Grade the check `fail` when the available evidence shows that the pass condition is not satisfied.

5. Grade the check `unclear` when the required evidence is genuinely absent or insufficient to determine whether the pass condition is satisfied. Do not fill missing information with assumptions.

6. Record one concise evidence line for every check identifying the fact, comparison, or quote that determined the grade.

7. Do not grade based on writing quality, formatting, length, confidence, or general impression. Apply the rubric to the plan's actual diagnosis, scope, executability, test plan, honesty, and communication.

8. A check may be graded without rereading the entire package when the necessary evidence was already recorded during evidence gathering. Reopen the relevant package section if the recorded evidence is insufficient.


## Verdict assembly

<!-- How the per-check grades become the final accept or reject:
apply your rubric's verdict rule, state how unclear grades enter it,
and say what gets quoted in the output for the deciding check. A
complete procedure produces the same verdict from the same grades,
every time. -->
1. After every rubric check has been graded, apply the verdict rule from `rubric.md`.

2. Accept the package only if every required check receives `pass`.

3. Reject the package if any required check receives `fail`.

4. Treat `unclear` as `fail` for required checks because the rubric requires enough evidence to verify that the plan is ready to post and build from without guessing.

5. Preferred checks, if any are added later, do not change the final verdict.

6. In the output, include every check's name, grade, and one evidence line explaining what determined the grade.

7. When the verdict is `reject`, make sure the evidence for the failing or unclear required check clearly identifies why the package was held.

8. Produce the final verdict as exactly `accept` or `reject` and follow the JSON output format required by `SKILL.md`.