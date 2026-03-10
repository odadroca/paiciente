Version: 1.0 | Last updated: 2026-03-09

# Design Notes

## Unique instruction set: documented behavior

The distinctive value of PAIciente lies in the combination of interaction rules rather than in any single clinical concept. The documented rule-set can be summarized as follows.

| Instruction family | Documented behavior | Practical consequence |
|---|---|---|
| Language handling | Replies in the language used by the user and translates the main subject matter while leaving control commands intact. | The interface remains natural for multilingual caregivers without breaking the command syntax. |
| Persona toggles | The active mode is controlled explicitly by slash commands rather than inferred silently. | The user always knows whether they are talking to the child model or the analyst. |
| State continuity | Conversation context is preserved and may be summarized on demand through `/status`. | Repeated sessions can build on earlier trials rather than resetting every turn. |
| Child realism | The child persona models defiance, shutdown, distraction, and gradual compliance instead of instant obedience. | The user can see the natural consequence of poor phrasing or abrupt transitions. |
| Clinical structure | The clinician persona always separates observed facts, hypotheses, and recommendations. | Interpretation is less likely to be confused with evidence. |
| Boundaries | The system avoids diagnosing users or children and stays within the scope requested. | It supports practice and reflection without overclaiming clinical authority. |
| Task scaffolding | When asked how to complete a task, the clinician decomposes the task into child-sized steps and predicts refusal points. | Advice is operational rather than generic. |
| Session review | Replay and debrief functions support counterfactual testing of different adult approaches. | The user can compare approaches instead of relying on intuition alone. |

## Design rationale

### 6.1 Why start in clinician mode

Starting in clinician mode lowers the chance that the conversation becomes an unstructured role-play. It first establishes facts, task demands, transition constraints, and the adult's goal before the user tests a live interaction.

### 6.2 Why the child persona is intentionally inconvenient

A useful simulation must preserve friction. If the child persona responded as an obedient script target, the user would never see which adult behaviors reliably trigger refusal, argument, or shutdown. The model therefore treats defiance as stress-responsive and context-dependent rather than malicious.

### 6.3 Why the clinician tone is blunt

The clinician persona avoids cheerleading because emotionally charged family routines often require precise error analysis. A vague, overly supportive style can conceal the functional role of adult escalation, unclear expectations, or unrealistic time assumptions.

### 6.4 Why commands matter

The command vocabulary creates explicit mode shifts. This is important because role-play, meta-analysis, and script generation are different tasks with different output requirements. PAIciente keeps those tasks separated instead of blending them.
