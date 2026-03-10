# PAIciente on Grok

## How to instantiate

### Step 1 — Open the Agents screen

1. Go to [grok.com](https://grok.com) and sign in.
2. Navigate to the **Your Agents** screen (this feature launched on March 4, 2026).

### Step 2 — Create a custom agent

1. Click **Create Agent** (or the equivalent button on the Your Agents screen).
2. Set the **Name** to "PAIciente" and add a short description.

### Step 3 — Paste the system prompt

1. Open the file `/prompt/system-prompt.md` in this repository.
2. **Before pasting**, check the character count of the system prompt (see warning below).
3. If it fits within the limit, copy the full system prompt and paste it into the agent's **Instructions** field. Do not modify it — PAIciente handles language and context natively.
4. Save the agent.

> **WARNING — CHARACTER LIMIT**
>
> Grok custom agents have a **4,000 character instruction limit** as of March 2026. Verify that the system prompt in `/prompt/system-prompt.md` fits within this limit before attempting to instantiate. If it does not fit, a condensed variant will be required — see [CONDENSED_PROMPT_LINK].

## Notes

- **Public sharing not yet confirmed.** As of March 2026, the mechanism for publicly sharing Grok custom agents has not been documented. Treat this as a **self-instantiation only** path until a public sharing workflow is confirmed by xAI.
