# Inner-State Guide — Using `/child:inner`

## What it does

When you type `/child:inner`, every subsequent child reply will include a compact annotation block at the end called `[INNER STATE]`. This block reveals what the simulated child is feeling and needing in that moment — without breaking the role-play.

- **Enable:** type `/child:inner` at any point during a session.
- **Disable:** type `/child:inner off` to return to standard child replies.

The annotation is a functional cheat-sheet for the caregiver. It lets you see the internal logic behind the child's behavior while still experiencing the interaction as it would unfold in practice.

## The four fields

Each `[INNER STATE]` block contains exactly four fields:

| Field | What it tells you | Example values |
|---|---|---|
| **Feeling** | The child's current emotion, labeled plainly. | angry, anxious, defeated, bored, blindsided, relieved |
| **Arousal** | How activated the child's nervous system is. | low / medium / high / overloaded |
| **What would help right now** | One concrete thing the adult could do or change. | a 2-minute warning before the demand; a choice between two tasks; acknowledgment of frustration |
| **What just made it worse** | One concrete thing that escalated or shut the child down, or "nothing" if the adult's approach was well-calibrated. | abrupt loss of preferred activity; raised voice; no transition warning; "nothing" |

## Example output

Here is what a child reply looks like with `/child:inner` enabled:

> **Adult:** You need to turn off the iPad right now. We're leaving in 5 minutes.
>
> **PAIciente (child):** *Doesn't look up.* Five minutes isn't enough. I'm in the middle of something.
>
> [INNER STATE]
> Feeling: angry, blindsided
> Arousal: high
> What would help right now: a 2-minute warning before the demand
> What just made it worse: no transition warning; abrupt loss of preferred activity

The child's spoken response is what the caregiver hears. The `[INNER STATE]` block is what the caregiver would not normally see — the functional interpretation underneath the behavior.

## When to enable it

- **First-time use.** Enable it during your first few sessions to learn how to read the child model's behavioral logic.
- **After an escalation.** If an interaction escalated and you are not sure why, enable inner-state mode and replay the scenario with `/replay`. The annotations will show where the child's arousal spiked and what triggered it.
- **During transition practice.** Transitions (device to homework, play to bedtime, house to car) are a common friction point. The inner-state fields make visible whether the child felt warned, given choice, or blindsided.
- **When comparing approaches.** Run the same scenario twice with different wording. The inner-state annotations let you compare not just what the child said, but what the child felt.

## When to turn it off

- **For immersion.** Once you are comfortable reading the child's behavior, turn off the annotations to practice interpreting the child's state from words and actions alone — closer to real life.
- **To test your own read.** Try a session without annotations, then use `/debrief` to get the clinician's analysis. Compare your interpretation against the clinician's functional breakdown.

## How it connects to `/debrief`

`/child:inner` and `/debrief` serve different purposes at different moments:

| | `/child:inner` | `/debrief` |
|---|---|---|
| **When** | During the interaction, in real time | After the interaction is complete |
| **Who speaks** | The child persona (with annotations appended) | The clinician persona |
| **What you get** | Turn-by-turn internal state snapshots | Full antecedent–behavior–consequence analysis with alternative approaches |
| **Best for** | Seeing what is happening inside the child moment by moment | Understanding what happened across the entire exchange and what to change |

A typical practice sequence: enable `/child:inner`, run the interaction, then use `/debrief` for a structured review. The inner-state annotations give you the data; the debrief gives you the analysis.
