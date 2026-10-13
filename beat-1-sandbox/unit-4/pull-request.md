# Unit 4 — Test and Submit

Path: `beat-1-sandbox/unit-4/pull-request.md`

Record of the pull request you opened against the Path Review repo, and of the evaluation
runs that produced `eval-run.txt`. This file is graded at the path above; a copy kept
anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your pull request

**Pull request**

https://github.com/codepath/pathreview-ai301-fa26-s3/pull/198

**Branch**

`reproduce-issue-63`

## Eval iterations

**Run history**

- Run 1: **16/20** 
- Run 2: **20/20** 

**Package analysis**

`pkg-03` — **Rubric verdict: reject. Gold label: reject.** The candidate Starship PR claimed to implement the posted plan exactly, but its diff also introduced a `resolve_symlinks` configuration option and rewrote the truncation helper, despite the plan's boundary excluding a configuration change. The Plan fidelity check rejects material unplanned additions, even when the central fix itself is plausible. The decisive distinction is the **diff compared against the accepted plan**, not the confidence of the PR description.

**Check rationale**

Verbatim check from `tools/pr-precheck/rubric.md`:

> | Plan fidelity | Candidate diff's changed files and behavior against the plan-context scope, exclusions, intended implementation, issue, and documented deviations | All material changes serve the issue and fit the planned boundary or explicitly explained deviations; significant omissions are accurately disclosed. Unexplained additions or omissions fail. Disclosing unrelated drive-by changes does not make them in scope. | required |

This check is required because a PR can correctly implement its main fix while quietly introducing additional changes or omitting promised work. Comparing actual changed files and behavior against the plan's boundaries catches such drift, including the changes in `pkg-03`. Its wording also permits an explained, issue-relevant deviation without allowing disclosure alone to excuse unrelated edits. I cannot verify whether this precise wording was revised between the two reported evaluation attempts.

**Trade-offs**

Making Plan fidelity a required check favors a narrowly reviewable PR over approving every technically plausible addition. It changes the outcome for a package such as `pkg-03`: the symlink fix may address the issue, but the extra configuration option and helper rewrite still require rejection under the recorded plan. The trade-off is that useful adjacent improvements may need a separate PR or an explicitly documented, issue-relevant deviation. This is intentional; the PR being evaluated is the implementation of a *specific agreed plan*, rather than a general opportunity to improve surrounding code. No `--only` canary rerun or specific post-run rubric revision is claimed because neither is documented in the available record.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/pr-precheck/`.
