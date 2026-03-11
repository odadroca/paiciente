# PAIciente on ChatGPT

---
### Sandbox link:
* It works without platform login - free-tier restricts will be applied, but it works fairly well
  https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0


---
## How to instantiate

### Step 1 - Create a Custom GPT

1. Go to [chatgpt.com](https://chatgpt.com) and sign in with a **Plus or Pro** account. (Custom GPT creation requires a paid subscription.)
2. Click your profile icon in the bottom-left corner and select **My GPTs**.
3. Click **Create a GPT**.

### Step 2 - Paste the system prompt

1. In the GPT editor, switch to the **Configure** tab.
2. Set the **Name** to "PAIciente" and add a short description.
3. Open the file `/prompt/system-prompt.md` in this repository and copy its entire contents.
4. Paste the full system prompt into the **Instructions** field. Do not modify it — PAIciente handles language and context natively.
5. Under Capabilities, disable Code Interpreter, DALL-E, and Web Browsing unless you have a specific reason to enable them.

### Step 3 - OPTIONAL - Publish to the GPT Store

1. Click **Save** and select **Publish to > Everyone**.
2. The GPT will be reviewed and listed in the GPT Store.
3. Share the public link with users.

## Notes

- **Creating GPTs requires Plus or Pro.** Free-tier users cannot create Custom GPTs - but can use the sandbox:
	- **Free-tier users can access the GPT Store.** Anyone with a free ChatGPT account can use a published GPT via its store link — they do not need a paid subscription to *use* it.
	- **Multi-turn session rate limits on free tier.** Free-tier users are subject to stricter rate limits (messages per hour/day). Extended sessions may be interrupted by rate limiting. The user will need to wait and resume.
