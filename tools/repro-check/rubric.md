# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Environment recorded | Reproduction report environment section, setup commands, version output, and repo facts when available | Pass if the package identifies enough environment information for another contributor to recreate the setup, including the relevant software/runtime version and repository state or commit when those affect reproduction | required |
| Reproduction steps complete | Reproduction report steps, commands, inputs, and setup instructions | Pass if the steps are ordered and specific enough for another contributor to follow without needing to infer a missing command, input, setup action, or navigation step that is necessary to reach the reported behavior | required |
| Evidence matches the issue | Reproduction report output, screenshots, logs, or other attached evidence read against the issue description | Pass if the evidence demonstrates the same behavior described by the issue rather than an adjacent, different, or merely suspected problem | required |
| Outcome stated honestly | Reproduction report conclusion and evidence | Pass if the report clearly states whether the issue was reproduced, not reproduced, or only partially reproduced, and does not claim a stronger result than the supplied evidence supports | required |
| No unsupported root-cause claim | Reproduction report analysis and evidence | Pass if claims about the cause of the behavior are either supported by evidence in the package or clearly identified as hypotheses rather than established facts | required |
| Repo conventions respected | Claim comment, reproduction comment, scope.md, voice-guide.md, and applicable repository contribution guidance | Pass if the proposed comment follows the repository's expected contribution style and course house rules, including posting original evidence and avoiding promises or claims that exceed what was demonstrated | required |


## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->
Accept a reproduction package only if every required check passes.

Reject the package if any required check fails.

Treat `unclear` as `fail` for required checks because a reproduction package should contain enough evidence for another contributor to verify the result without guessing.

Preferred checks, if added later, do not affect the verdict.