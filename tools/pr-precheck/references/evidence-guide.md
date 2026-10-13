# Evidence guide: where evidence lives in a PR package

<!--
THIS IS THE PART YOU WRITE (third week running: the map stays in your
hands). Your tool uses this guide as its map: for every kind of
evidence a rubric check names, this file says WHERE to find it in a PR
package and WHAT GOOD LOOKS LIKE when you do.

The four families below are the harness's failure categories under
the names the eval README uses: plan fidelity = silent-drift, test
evidence = not-tested, diff quality = unreviewable, standards and
comms = standards-wall. A package that fails none of them is a
clear-accept. Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the plan-context block's scope pair and test
  plan, the candidate PR's diff, commits, description, or
  test-evidence section, the repo-facts block's template asks and
  stated policy). In live mode (where in your working copy and on
  GitHub: your plan.md and its deviation notes, your branch's diff,
  your draft title and description, your captured test output, the
  repo's PR template and CONTRIBUTING.md).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("every changed file falls inside the
  plan's stated boundary or a deviation note") over adjectives ("the
  diff is clean").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts three ways: your
procedure says WHEN to gather each family, this guide says WHERE, and
your SKILL.md says the tool reads both. Write the map you wish your
executor had.
-->

## Plan fidelity (harness category: silent-drift)

<!-- Where the plan states its scope, boundary, and deviation notes,
and where the diff shows what actually changed. What it means for a
diff to match the plan, for an honest deviation to re-tie a mismatch,
and what silent drift looks like in each direction (more than the
plan, or less with no note). The description's fidelity claims read
against the diff live here too: a description claiming more or less
than the diff delivers is silent drift, not a comms problem. -->

**Where it lives:**

- **Eval mode:** Read the issue and the plan-context block, including its reproduction evidence, planned implementation, scope boundaries, excluded work, and any documented deviations. Compare these against the candidate PR's unified diff, changed files, title, and description.
- **Live mode:** Read the issue thread, the posted implementation plan in `plan.md` (including `## Deviations`), and the committed branch changes shown by `git diff main...HEAD`. Compare the proposed title and description in `pr_draft.md` against the diff and plan.

**What good looks like:**

Every material modification in the diff implements the planned change or an explicitly explained deviation that remains relevant to the issue. Planned work that was not completed is accurately disclosed rather than silently omitted.

The PR description accurately represents the implementation and does not claim functionality, changed behavior, or completion beyond what the diff supports.

Silent drift occurs when the diff adds unplanned work, omits promised work without explanation, or contradicts the PR's description. Documenting an unrelated change does not automatically make that change appropriate.

## Test evidence (harness category: not-tested)

<!-- Where the PR shows its proof: the test-evidence section's
before/after against the plan's test plan and the reproduction's own
steps, and the outcome of the repo's own checks or suite. What
decisive looks like (an observable behavior named, the expected-after
stated, the checks' outcome visible) next to "tests pass". -->
**Where it lives:**

- **Eval mode:** Read the original reproduction evidence and test plan in the plan-context block. Compare the expected behavior and planned verification steps against the candidate PR's test-evidence section. Use the repo-facts block to identify required repository checks.
- **Live mode:** Read the Unit 2 reproduction evidence from the issue thread or the instructor's house reproduction pack, and the test plan in `plan.md`. Compare these against the before/after output and check results recorded in `test_evidence.md`. Consult the repository's PR template and `docs/CONTRIBUTING.md` for required checks.

**What good looks like:**

The evidence identifies the behavior being tested, the relevant commands or steps, and an observable result. Where applicable, before/after evidence demonstrates that the behavior changed in the expected way, using the original reproduction or an equivalent test of the same behavior.

Applicable repository checks have recorded outcomes. Failed, unavailable, or inapplicable checks are reported accurately, with relevant explanations.

A generic statement such as "all tests pass" is not sufficient evidence by itself. An honestly reported failure or limitation is not automatically disqualifying, but disclosure does not establish an unverified success or override a requirement that a check must pass.


## Diff quality (harness category: unreviewable)

<!-- Where the change itself lives: the unified diff and the commit
list. What a reviewable change looks like (the fix visible, nothing
unrelated riding along) and the debris tells: debug leftovers, dead
code, commented-out blocks, formatting churn, drive-by edits. -->
**Where it lives:**

- **Eval mode:** Examine the candidate PR's unified diff and commit list. Compare changed files and hunks with the planned scope and the issue being addressed.
- **Live mode:** Examine `git diff main...HEAD` and the branch's relevant committed history. Compare the changes against the implementation scope and deviations documented in `plan.md`.

**What good looks like:**

The diff contains the modifications needed to implement the planned fix and any necessary supporting changes. The purpose of each substantive change can be understood in relation to the issue.

The diff does not contain unrelated refactors, accidental files, debugging statements, abandoned experiments, commented-out code, or substantial unnecessary formatting changes that distract from the fix.

Multiple commits or files do not automatically make a PR unreviewable. The deciding factor is whether the actual changes are relevant, understandable, and within the intended scope.

## Standards and comms (harness category: standards-wall)

<!-- Where the repo states its asks (the repo-facts block's PR
template sections, contributing instructions, and stated policy,
including AI-use disclosure) and where the PR honors them: the
stated sections filled with real content, the disclosure present,
explicit maintainer direction in the thread engaged. What compliant
looks like next to boilerplate or a visibly ignored ask. (Whether
the description's claims match the diff is plan fidelity, above.) -->
**Where it lives:**

- **Eval mode:** Read the repo-facts block for PR template requirements, contribution instructions, stated testing requirements, and AI-use policies. Read the issue context and thread highlights for applicable maintainer instructions. Compare these requirements against the candidate PR's title, description, and reported evidence.
- **Live mode:** Read `.github/PULL_REQUEST_TEMPLATE.md`, `docs/CONTRIBUTING.md`, the issue thread, and applicable repository policies. Compare the requirements against `pr_draft.md` and `test_evidence.md`. Also consult `scope.md` for course-specific rules and `voice-guide.md` for personal writing rules, keeping voice feedback separate from the rubric verdict unless the rubric explicitly requires otherwise.

**What good looks like:**

The PR satisfies the repository's applicable contribution requirements. Mandatory template sections contain meaningful information, the issue is referenced when required, and any required AI-use disclosure accurately explains how AI contributed to the work.

The description responds to relevant maintainer instructions and communicates limitations or deviations without misleading the reviewer. It does not substitute generic boilerplate for information specifically required by the repository.

Do not invent requirements that the repository does not state. A missing PR template or absent AI policy is not itself a violation. Whether the description's implementation claims match the actual diff is evaluated under Plan fidelity rather than treated solely as a communication issue.