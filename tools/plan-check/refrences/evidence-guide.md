# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

<!-- Where the plan states its cause, and where the repro evidence
pins down the behavior that cause must explain. What it means for a
diagnosis to follow from the evidence rather than contradict or
ignore it. -->
**Where it lives:** In an eval bundle, look at the candidate plan's diagnosis or stated cause and compare it directly with the repro-evidence block and the issue context. The reproduction evidence is the main source for determining what behavior was actually observed and what the diagnosis must explain. In live mode, compare the diagnosis in `plan.md` with the student's posted reproduction comment on the issue and with the issue thread when additional context is needed.

**What good looks like:** The diagnosis explains the behavior that the reproduction evidence actually demonstrates and does not contradict or ignore that evidence. A cause should be treated as established only when the available evidence supports it; otherwise, uncertainty should be stated rather than replacing the reproduced behavior with an unsupported explanation.


## Scope

<!-- Where the plan bounds itself: the in-scope statement, the
not-in-scope line, the files or areas named. What one bounded change
looks like next to a drive-by rewrite. -->
**Where it lives:** In an eval bundle, look at the candidate plan's in-scope statement, not-in-scope statement, files or areas named, proposed approach, and issue context. Compare these sections to determine whether every planned change belongs to the same fix. In live mode, inspect the scope and named files or areas in `plan.md` and compare them with the reproduced issue and any explicit boundaries stated by maintainers in the issue thread.

**What good looks like:** The plan describes one coherent change tied to the reproduced problem and clearly identifies what will not be changed. The named files, areas, and implementation work should stay within that boundary rather than adding unrelated refactors, migrations, redesigns, documentation changes, or other while-I-am-here work.


## Executability

<!-- Where the plan says what will actually be done: files or areas,
approach, order of work. What it means for a stranger to be able to
start executing without asking the author anything. -->
**Where it lives:** In an eval bundle, look at the candidate plan's files or areas, implementation approach, order of work, and any stated dependencies or unknowns. These sections should explain where the change will occur and what the contributor intends to do there. In live mode, use the same sections in `plan.md`, together with repository structure or documentation when needed to understand the locations the plan names.

**What good looks like:** Another contributor should be able to begin implementing the change without asking the author where to start, what behavior to modify, or what general approach to take. The plan does not need to prescribe every line of code, but it must identify enough of the target area and implementation direction to make the first implementation step clear.


## Test plan

<!-- Where the plan says how success will be observed, and how that
maps onto the repro evidence's steps and artifacts. What a decisive
test plan names that a vague one does not. -->
**Where it lives:** In an eval bundle, look at the candidate plan's test plan and compare it with the repro-evidence block's steps, inputs, commands, artifacts, and observed behavior. In live mode, compare the test plan in `plan.md` with the student's posted Unit 2 reproduction evidence and any existing repository tests that exercise the same behavior.

**What good looks like:** The test plan re-runs the reproduced behavior or uses a check through the same real code path and states the expected result after the fix. It names an observable outcome that another contributor can verify. A statement such as run the tests, verify the fix, or make sure it works is not sufficient unless it also identifies the specific behavior and expected result that demonstrate success.


## Honesty

<!-- Where claims meet uncertainty: risks, unknowns, and deviations.
How to tell stated unknowns from false confidence, and where an
honest mid-build deviation gets recorded. -->
**Where it lives:** In an eval bundle, look at the candidate plan's risks, unknowns, assumptions, diagnosis language, and any deviation notes. Compare confident statements against the reproduction evidence and other package evidence to determine whether the certainty is justified. In live mode, inspect these sections in `plan.md`, including any deviations recorded after implementation begins.

**What good looks like:** Known facts are distinguished from assumptions or unresolved questions. Risks or implementation uncertainties that could affect the change are stated rather than hidden behind confident language. If the build later differs from the original plan, the deviation is recorded with what changed and why instead of silently allowing the implementation to drift from the plan.


## Comms

<!-- Where the words meet the thread and the repo: the plan comment
read against the issue's maintainer signals (thread highlights, or
the live thread) and against the repo-facts block's stated templates,
contributing asks, and contribution policy (including AI-use
disclosure requirements). What thread-aware looks like next to
boilerplate. -->
**Where it lives:** In an eval bundle, compare the candidate plan comment with the candidate plan, issue context, thread highlights, and repo-facts block, including contribution requirements or repository conventions. In live mode, compare the draft plan comment with `plan.md`, the live issue thread, maintainer comments, repository contribution documentation, applicable templates or AI-use requirements, `scope.md`, and `voice-guide.md`.

**What good looks like:** The plan comment accurately communicates the diagnosis, intended change, and validation approach that the plan actually contains. It responds to relevant maintainer direction and repository conventions, does not promise work outside the plan, and does not present uncertain causes or implementation details as established facts. The comment should be specific to the issue rather than generic boilerplate.