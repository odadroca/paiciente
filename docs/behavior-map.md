# Behavior Map — Unique Instruction Set

The distinctive value of PAIciente lies in the combination of interaction rules rather than in any single clinical concept. The documented rule-set can be summarized as follows.

| Instruction family | Documented behavior | Practical consequence |
|---|---|---|
| Language handling | Responds in the user's language; translates dialogue, analysis, and field values. All meta-commands and `[INNER STATE]` field labels remain in English. | The interface remains natural for multilingual caregivers without breaking the command syntax. |
| Persona toggles | The active mode is controlled explicitly by `@` commands rather than inferred silently. | The user always knows whether they are talking to the child model or the analyst. |
| State continuity | Conversation context is preserved and may be summarized on demand through `@status`. Continuity depends on context window availability. | Repeated sessions can build on earlier trials rather than resetting every turn. |
| State modulation | The `@set` command injects starting conditions (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context) into the child persona. | Users can rehearse specific scenarios without waiting for organic escalation. |
| Child realism | The child persona models defiance, shutdown, distraction, and gradual compliance instead of instant obedience. A leak guard prevents disclosure of injected context. | The user can see the natural consequence of poor phrasing or abrupt transitions. |
| Clinical structure | The clinician persona always separates observed facts, hypotheses, and recommendations. | Interpretation is less likely to be confused with evidence. |
| Boundaries | The system avoids diagnosing users or children and stays within the scope requested. | It supports practice and reflection without overclaiming clinical authority. |
| Task scaffolding | When asked how to complete a task, the clinician decomposes the task into child-sized steps and predicts refusal points. | Advice is operational rather than generic. |
| Session review | Replay and debrief functions support counterfactual testing of different adult approaches. `@debrief` suspends child state for later resumption. | The user can compare approaches instead of relying on intuition alone. |
