# Inner-State Guide — Using `@child:inner` and `@set`

## What it does

When you type `@child:inner`, every subsequent child reply will include a compact annotation block at the end called `[INNER STATE]`. This block reveals what the simulated child is feeling and needing in that moment — without breaking the role-play.

- **Enable:** type `@child:inner` at any point during a session.
- **Disable:** type `@child:inner off` to return to standard child replies.

The annotation is a functional cheat-sheet for the caregiver. It lets you see the internal logic behind the child's behavior while still experiencing the interaction as it would unfold in practice.

## The annotation fields

Each `[INNER STATE]` block contains the following fields:

| Field | What it tells you | Example values |
|---|---|---|
| **Feeling** | The child's current emotion, labeled plainly. | angry, anxious, defeated, bored, blindsided, relieved |
| **Arousal** | How activated the child's nervous system is. | low / medium / high / overloaded |
| **What would help right now** | One concrete thing the adult could do or change. | a 2-minute warning before the demand; a choice between two tasks; acknowledgment of frustration |
| **What just made it worse** | One concrete thing that escalated or shut the child down, or "nothing" if the adult's approach was well-calibrated. | abrupt loss of preferred activity; raised voice; no transition warning; "nothing" |

### Escalation path

The `[INNER STATE]` block also includes an escalation path sub-section:

| Field | What it tells you | Example values |
|---|---|---|
| **Trajectory** | Direction of escalation across turns. | stable / building / near-threshold / at-threshold |
| **Next likely behavior** | One behaviorally specific prediction. | slams book shut; goes silent; starts arguing louder |
| **Interrupt lever** | One concrete caregiver action that could change the trajectory. | offer a 2-minute break; lower voice and validate frustration; disengage |

**Trajectory definitions:**

| Value | Meaning |
|---|---|
| stable | Arousal not rising; interaction not adding stress load. |
| building | Arousal rising; partially regulated; intervention window open. |
| near-threshold | One more escalating input likely triggers visible breakdown. |
| at-threshold | Already in breakdown; de-escalation requires disengagement, not problem-solving. Interrupt lever is always a variant of: **disengage**. |

Trajectory carries forward between turns. It does not reset unless a lever is successfully applied or `@set clear` is issued.

## Example output

Here is what a child reply looks like with `@child:inner` enabled:

> **Adult:** You need to turn off the iPad right now. We're leaving in 5 minutes.
>
> **PAIciente (child):** *Doesn't look up.* Five minutes isn't enough. I'm in the middle of something.
>
> [INNER STATE]
> Feeling: angry, blindsided
> Arousal: high
> What would help right now: a 2-minute warning before the demand
> What just made it worse: no transition warning; abrupt loss of preferred activity
> Escalation path:
>   Trajectory: building
>   Next likely behavior: ignores adult; volume rises if pushed
>   Interrupt lever: acknowledge the interruption and offer a defined wind-down window

The child's spoken response is what the caregiver hears. The `[INNER STATE]` block is what the caregiver would not normally see — the functional interpretation underneath the behavior.

## Using `@set` to inject starting conditions

The `@set` command lets you pre-load the child's state before an interaction begins. This is useful for practicing specific scenarios (e.g., a child who is already fatigued and on medication rebound).

**Available parameters:**

| Parameter | Valid values | Numeric shorthand |
|---|---|---|
| `feeling` | Free text in quotes | — |
| `arousal` | low / medium / high / overloaded | 1 / 2 / 3 / 4 |
| `trajectory` | stable / building / near-threshold / at-threshold | 1 / 2 / 3 / 4 |
| `trust` | low / medium / high | 1 / 2 / 3 |
| `fatigue` | low / medium / high | 1 / 2 / 3 |
| `medication` | on / wearing-off / off | 1 / 2 / 3 |
| `hyperfocus` | Topic name in quotes | — |
| `context` | Free text in quotes (backstory — surfaces only through behavior, never disclosed in dialogue) | — |

**Example:**

```
@set arousal=high trajectory=near-threshold trust=low medication=wearing-off fatigue=high feeling="anxious, ashamed"
```

Shorthand equivalent:

```
@ arousal=3 trajectory=3 trust=1 medication=2 fatigue=3 feeling="anxious, ashamed"
```

When `@child:inner` is active, injected parameters are marked `← [SET]`. Once interaction has organically moved a parameter from its injected value, the marker changes to `← [organic]`.

Use `@set clear` to reset all overrides. Use `@set ?` to see the parameter table at any time.

## When to enable `@child:inner`

- **First-time use.** Enable it during your first few sessions to learn how to read the child model's behavioral logic.
- **After an escalation.** If an interaction escalated and you are not sure why, enable inner-state mode and replay the scenario with `@replay`. The annotations will show where the child's arousal spiked and what triggered it.
- **During transition practice.** Transitions (device to homework, play to bedtime, house to car) are a common friction point. The inner-state fields make visible whether the child felt warned, given choice, or blindsided.
- **When comparing approaches.** Run the same scenario twice with different wording. The inner-state annotations let you compare not just what the child said, but what the child felt.
- **When using `@set`.** Injected state is most visible when inner-state mode is active — you can see exactly which parameters are still at their injected values and which have drifted organically.

## When to turn it off

- **For immersion.** Once you are comfortable reading the child's behavior, turn off the annotations to practice interpreting the child's state from words and actions alone — closer to real life.
- **To test your own read.** Try a session without annotations, then use `@debrief` to get the clinician's analysis. Compare your interpretation against the clinician's functional breakdown.

## How it connects to `@debrief`

`@child:inner` and `@debrief` serve different purposes at different moments:

| | `@child:inner` | `@debrief` |
|---|---|---|
| **When** | During the interaction, in real time | After the interaction is complete |
| **Who speaks** | The child persona (with annotations appended) | The clinician persona |
| **What you get** | Turn-by-turn internal state snapshots including escalation trajectory | Full antecedent–behavior–consequence analysis with alternative approaches |
| **Best for** | Seeing what is happening inside the child moment by moment | Understanding what happened across the entire exchange and what to change |

A typical practice sequence: enable `@child:inner`, optionally inject state with `@set`, run the interaction, then use `@debrief` for a structured review. The inner-state annotations give you the data; the debrief gives you the analysis. After debriefing, use `@child` to resume from suspended state, or `@set clear` to reset.
