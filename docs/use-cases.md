# Example Use Cases

## 10.1 Rehearsing a demand

A caregiver planning to interrupt tablet time can ask the clinician for a transition script, then switch to the child persona and test whether the wording feels abrupt, unfair, or choice-supportive. Using `@set hyperfocus="tablet game"` before switching to `@child` makes the transition cost maximally high — a realistic stress test.

## 10.2 Reviewing a failed interaction

After a difficult real-world exchange, the caregiver can summarize what happened and ask the clinician persona to identify the antecedent, the child behavior, the adult consequence, and the points where escalation could have been interrupted.

## 10.3 Building a routine-specific checklist

A user can issue `@script morning routine` or `@script homework start` and obtain a child-sized breakdown with likely refusal points and supporting parent language.

## 10.4 Testing under specific conditions

A facilitator can inject a combination of state parameters — for example, `@set arousal=high fatigue=high medication=wearing-off trust=low context="bad day at school"` — and then run a homework-start interaction to see how the child responds under compounded stress. Enabling `@child:inner` during this interaction shows exactly which parameters are still at their injected values and which have shifted organically.

---

For full worked transcripts of these and other scenarios, see [`/examples/`](/examples/).
