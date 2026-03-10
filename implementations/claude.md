# PAIciente on Claude

## How to instantiate

### Step 1 — Create a new Project

1. Go to [claude.ai](https://claude.ai) and sign in (free or Pro account).
2. In the left sidebar, click **Projects**.
3. Click **Create Project** and give it a name (e.g., "PAIciente").

### Step 2 — Paste the system prompt

1. Open the file `/prompt/system-prompt.md` in this repository and copy its entire contents.
2. In the Project you just created, click the **Project Instructions** field (sometimes labeled "Set custom instructions").
3. Paste the full system prompt verbatim. Do not modify it — PAIciente handles language and context natively.

### Step 3 — Start a session

1. Open a new conversation inside the Project.
2. The system prompt is now active. PAIciente will respond according to its instructions from the first message onward.

## Notes

- **Not publicly shareable.** Claude Projects are private to the account that creates them. There is no public link or store mechanism. Each user must self-instantiate by following the steps above.
- **Free tier compatibility.** PAIciente works on Claude's free tier. Free-tier users have access to Projects and can paste custom instructions. Usage is subject to the standard free-tier message limits.
