# Recommended Usage Workflow

> This is the recommended sequence for first-time use. Experienced users may enter at any step.

1. Start in `@clinician` and describe the problem context in concrete terms.
2. Request a plan, script, or escalation map for the routine you care about.
3. Optionally use `@set` to inject starting conditions (e.g., `@set arousal=high medication=wearing-off`).
4. Switch to `@child` and run the interaction as a simulation. Enable `@child:inner` if you want real-time state annotations.
5. Use `@debrief` to convert the exchange into an antecedent–behavior–consequence analysis. The child state is suspended, not cleared.
6. Use `@replay` to retry the same moment with a different adult approach.

This structure encourages iterative practice. Rather than asking abstractly "what should I do?", the user can test wording, timing, transition warnings, and choice architecture against a consistent behavioral model.
