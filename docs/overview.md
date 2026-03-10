# Overview

## 1. Purpose and scope

PAIciente is designed for caregivers, parents, guardians, teachers, and clinicians who want a structured way to rehearse difficult interactions with a child who presents with ADHD-related executive-function difficulty and oppositional behavior.

It serves three practical functions:

- **Simulation:** a user can speak to a child persona and observe how a specific adult approach is likely to land.
- **Analysis:** a user can switch to a clinician persona that decomposes what happened behaviorally.
- **Tooling:** the clinician persona can generate scripts, checklists, escalation maps, and task breakdowns.

The intended scope is narrow by design. It is a simulation and documentation aid, not a substitute for therapy, diagnostic assessment, or emergency response.

## 2. High-level architecture

PAIciente operates through two explicitly switchable personas and a small command vocabulary. The active persona determines both tone and response format.

### 2.1 Core mode controls

| Command | Function | Notes |
|---|---|---|
| `/clinician` | Activates the clinician persona. | Default at conversation start. |
| `/child` | Activates the child persona. | Used for live role-play. |
| `/child:inner` | Adds an inner-state annotation after the child reply. | A compact cheat-sheet for the caregiver. |
| `/child:inner off` | Removes the inner-state annotation. | Returns the child persona to standard output. |
| `/status` | Reports the active persona and conversation context so far. | Useful for long sessions. |

### 2.2 Review and planning controls

| Command | Function | Notes |
|---|---|---|
| `/replay` | Re-runs the last child interaction using a new adult approach. | Supports deliberate practice. |
| `/debrief` | Switches to clinician mode for analysis of the previous exchange. | Focuses on antecedent, behavior, and consequence. |
| `/script [task]` | Produces a parent script and a visual checklist for a named task. | Example: homework, leaving the house, bedtime. |
| `/escalation-map [scenario]` | Maps likely escalation paths and de-escalation forks. | Useful for transition-heavy or high-conflict routines. |

> **Why the two-persona structure matters.** One persona lets the user practice the interaction itself. The other persona converts the interaction into a behavioral case formulation with alternatives. The value comes from switching back and forth, not from either mode in isolation.
