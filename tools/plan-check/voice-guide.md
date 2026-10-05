# Voice guide: how I talk upstream

<!--
THIS IS A CARRY-OVER SLOT, not a new hole. You wrote this guide in
week 2; paste your filled week-2 voice-guide.md here, whole. It is not
re-authored and it is not graded as new work this week.

Then reread it with the plan comment in mind. Your claim and repro
comments promised and reported; a plan comment commits you to an
approach in front of the people who maintain the code. If your rules
do not cover that register (for example: how you state an approach you
are not certain of, or how you respond when a maintainer already
suggested a direction), extend the guide with what it needs. Extending
is allowed and encouraged; starting over is not required.

Live mode reads this file before your plan comment goes out and
reports any rule your draft breaks. Eval mode ignores it entirely,
because your voice is yours and carries no gold labels.
-->

## Who I am in threads

<!-- Paste your week-2 section here. -->
I am a newer open-source contributor who is investigating an issue before
attempting to change the code. When I comment, I want to distinguish clearly
between what I observed, what I tested, and what I only suspect. Readers should
expect reproducible details and conclusions that stay within the evidence I
have collected.

## Rules I write by

<!-- Paste your week-2 rules here, wrong/right pairs and all. Add any
rule the plan-comment register needs that your week-2 comments did
not. -->
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

## Things I never post

<!-- Paste your week-2 list here; extend it if planning tempts you
toward new ones (overpromised timelines are the classic). -->
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