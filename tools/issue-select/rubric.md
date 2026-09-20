# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer activity | Repo facts: last 5 default-branch commits and maintainer first-response sample; issue comments when available | Pass if there is evidence of recent human maintainer activity: at least one non-bot default-branch commit within 90 days of the capture date OR a maintainer response in the response sample or issue thread within 30 days of the relevant post | required |
| Repository in use | Repo facts: archived flag, latest release, and last push to any branch | Pass if the repository is not archived and has either a release or a push within the last 12 months | required |
| Newcomer-sized scope | Issue body and Comments section | Pass if the issue describes one coherent, implementable task with enough settled direction for a contributor to begin work. Multiple related fixes or implementation steps may still pass when they address one clearly diagnosed bug or behavior. Fail if the issue is an umbrella/tracking task, an open-ended codebase-wide effort, a pure usage/support question, has an unresolved product/design decision that must be settled before implementation, or has a long history of design debate or abandoned attempts without a settled implementation direction. | required |
| Availability | Repo facts: assignees and linked PRs; Comments section for claim comments, abandonment/unassignment messages, or mentioned PRs | Pass if there is no current assignee, open linked PR, or clearly active contributor implementation. Historical claims, closed PRs, abandoned/unassigned claims, and old expressions of interest do not count as active. | required |
| Contribution policy | Repo facts: contribution policy; CONTRIBUTING.md, AI policy files, or templates in live mode | Pass if AI-assisted contribution is allowed when the contributor reviews, understands, tests, or takes responsibility for the work. Fail if the repository categorically refuses AI-generated contribution content such as code or documentation with no allowed human-reviewed assistive path. | required |



## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
Accept an issue only if every required check passes.

Reject the issue if any required check fails.

Treat `unclear` as `fail` for required checks because a first contribution
should have enough evidence to verify that it is suitable.

Preferred checks, if added later, do not affect accept or reject. They are
used only to rank issues that have already been accepted.