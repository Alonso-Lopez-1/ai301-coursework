# Voice guide: how I talk upstream

<!--
THIS IS A CARRY-OVER SLOT, not a new hole. You wrote this guide in
week 2 and carried it through week 3; paste your filled voice-guide.md
here, whole. It is not re-authored and it is not graded as new work
this week.

Then reread it with the PR in mind. Your comments promised, reported,
and committed to an approach; a PR title and description ask a
maintainer to spend review time on your work. If your rules do not
cover that register (for example: how a title earns its thirty
seconds, how a description promises exactly what the diff contains,
how a disclosed shortfall is worded so it reads as honesty rather
than apology), extend the guide with what it needs. Extending is
allowed and encouraged; starting over is not required.

Live mode reads this file and holds your draft PR title and
description against it, reporting any rule your draft breaks. Eval
mode ignores it entirely, because your voice is yours and carries no
gold labels.
-->

## Who I am in threads

<!-- Paste your section here. -->
I am a newer open-source contributor who is investigating an issue before
attempting to change the code. When I comment, I want to distinguish clearly
between what I observed, what I tested, and what I only suspect. Readers should
expect reproducible details and conclusions that stay within the evidence I
have collected.

## Rules I write by

<!-- Paste your rules here, wrong/right pairs and all. Add any rule
the PR register needs that your comments did not. -->
### Rule: Separate observations from explanations

I state what I directly observed before suggesting why it may have happened.
If I have not verified a root cause, I describe it as a possibility rather
than presenting it as established.

- Wrong: "The parser is causing this error because it does not handle the input correctly."
- Right: "I reproduced the error with this input. The failure occurs while the parser is processing it, but I have not confirmed the root cause yet."

### Rule: Say exactly what I reproduced

I describe the specific behavior and conditions I tested instead of using a
general statement such as "I reproduced this." If my result differs from the
original report, I say so.

- Wrong: "I can confirm this bug."
- Right: "I reproduced the reported error on commit `abc123` when running the command with the input shown below."

### Rule: Do not promise a fix or a deadline

Claiming an issue means I intend to investigate it, not that I already know the
solution or can guarantee when it will be completed.

- Wrong: "I'll fix this and have a PR ready tomorrow."
- Right: "I'd like to investigate this issue and will post what I find after I try to reproduce the reported behavior."

### Rule: Include useful details instead of confidence language

I prefer concrete commands, versions, outputs, and conditions over phrases that
only express how certain I feel. A reader should be able to understand why I
reached a conclusion from the evidence in the comment.

- Wrong: "I'm pretty sure this is definitely the same issue."
- Right: "Running `example-command` on version 2.4 produces the same error message shown in the issue."

### Rule: Be clear when reproduction fails or is incomplete

I do not turn an unsuccessful test into confirmation. If I cannot reproduce the
behavior, or can reproduce only part of it, I state the result and the
environment or conditions I tested.

- Wrong: "The issue seems valid even though I couldn't get the error."
- Right: "I could not reproduce the reported error in the environment below. The command completed successfully in three attempts."

### Rule: Make the PR title specific to the implemented change

The title names the change actually visible in the diff, rather than promising a wider outcome.

- Wrong: "Completely fix the scoring system"
- Right: "Fix README scorer test fixture threshold"

### Rule: Match PR claims to the code and test evidence

The summary and Changes section describe what the diff actually does. Testing statements distinguish commands that passed, failed, or did not run, and limitations are named without apology or exaggeration.

- Wrong: "All checks pass and the bug is fully resolved" when tests were not run.
- Right: "The targeted test passed; integration tests reported no tests collected. The remaining limitation is noted below."

### Rule: Disclose AI assistance and deviations plainly

When required by the repository, say how AI was used and what I independently examined or verified. If implementation departed from the plan, describe what changed and why in the PR and in the plan's Deviations section.

- Wrong: "No AI involvement" when AI drafted implementation suggestions.
- Right: "I used AI to brainstorm test cases and reviewed and ran the final changes myself."

## Things I never post

<!-- Paste your list here; extend it if PR descriptions tempt you
toward new ones (claiming coverage the evidence does not show is the
classic). -->
- A promise that I will fix an issue or submit a pull request by a particular
  date when I do not know that I can.
- A statement that I found the root cause when I have only observed where the
  failure appeared.
- "I can confirm" or "I reproduced it" without describing the behavior and
  conditions that support the statement.
- A claim that another contributor's reproduction also proves mine; I post my
  own evidence and describe my own environment.
- A conclusion stronger than the commands, logs, screenshots, or other evidence
  in my reproduction package support.
- Boilerplate praise or filler that does not help maintainers understand what I
  tested or observed.

### Additional things I never post in a PR

- A claim that CI has passed before CI actually runs.
- A blanket statement that all tests pass when one required check failed or was not executed.
- A summary that conceals material differences between the diff and the posted plan.