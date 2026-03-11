# Overview

## 1. Purpose and scope

PAIciente is designed for caregivers, parents, guardians, teachers, and clinicians who want a structured way to rehearse difficult interactions with a child who presents with ADHD-related executive-function difficulty and oppositional behavior.

It serves three practical functions:

- **Simulation:** a user can speak to a child persona and observe how a specific adult approach is likely to land.
- **Analysis:** a user can switch to a clinician persona that decomposes what happened behaviorally.
- **Tooling:** the clinician persona can generate scripts, checklists, escalation maps, and task breakdowns.

The intended scope is narrow by design. It is a simulation and documentation aid, not a substitute for therapy, diagnostic assessment, or emergency response.

## 2. High-level architecture

PAIciente operates through two explicitly switchable personas and a command vocabulary. The active persona determines both tone and response format.

### 2.1 Core mode controls

| Command | Function | Notes |
|---|---|---|
| `@clinician` | Activates the clinician persona. | Default at conversation start. |
| `@child` | Activates the child persona. | Used for live role-play. |
| `@child:inner` | Adds an inner-state annotation after the child reply. | A compact cheat-sheet for the caregiver. |
| `@child:inner off` | Removes the inner-state annotation. | Returns the child persona to standard output. |
| `@status` | Reports the active persona and conversation context so far. | Useful for long sessions. |

### 2.2 State modulation

| Command | Function | Notes |
|---|---|---|
| `@set [p]=[v]` | Overrides child state parameters (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Starting condition; organic drift applies. |
| `@set [p]=[v] persist` | Locks value against organic drift. | For controlled scenarios. |
| `@set clear` | Resets all manual overrides. | Returns to simulated organic state. |
| `@set ?` | Outputs parameter table. | Quick reference. |
| `@ [p]=[v]` | Shorthand alias for `@set`. | Numeric keys accepted. |

### 2.3 Review and planning controls

| Command | Function | Notes |
|---|---|---|
| `@replay` | Re-outputs the last child turn, then prompts for a new adult approach. | User supplies the new input. |
| `@debrief` | Switches to clinician mode for analysis of the previous exchange. | Child state is suspended, not cleared. |
| `@script [task]` | Produces a parent script and a visual checklist for a named task. | Example: homework, leaving the house, bedtime. |
| `@escalation-map [scenario]` | Maps likely escalation paths and de-escalation forks. | Useful for transition-heavy or high-conflict routines. |

> **Why the two-persona structure matters.** One persona lets the user practice the interaction itself. The other persona converts the interaction into a behavioral case formulation with alternatives. The value comes from switching back and forth, not from either mode in isolation.
