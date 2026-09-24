# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->
I am a newer open-source contributor who is investigating an issue before
attempting to change the code. When I comment, I want to distinguish clearly
between what I observed, what I tested, and what I only suspect. Readers should
expect reproducible details and conclusions that stay within the evidence I
have collected.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->
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

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->
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