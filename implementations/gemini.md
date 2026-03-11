# PAIciente on Gemini
---
### Sandbox link:
* Platform constraint: user must be logged with 1 google account:
  https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing

---
## How to instantiate

### Step 1 — Create a Gem

1. Go to [gemini.google.com](https://gemini.google.com) on a **desktop browser**. (Gem creation is not available on the mobile app as of this writing.)
2. Sign in with your Google account (free tier is sufficient).
3. In the left sidebar, click **Gem manager** and then **Create Gem**.

### Step 2 — Paste the system prompt

1. Set the **Name** to "PAIciente".
2. Open the file `/prompt/system-prompt.md` in this repository and copy its entire contents.
3. Paste the full system prompt into the **Instructions** field. Do not modify it — PAIciente handles language and context natively.
4. Click **Save**.

### Step 3 - OPTIONAL - Share via link

1. Open your saved Gem and click the **Share** button.
2. Set the sharing permissions (Google Drive-style: "Anyone with the link" or restricted).
3. Copy the share link.


## Notes

- **Free tier compatibility.** Gem creation and usage is available on Gemini's free tier. No paid subscription is required.
- **Desktop only for creation.** Gems must be created at gemini.google.com in a desktop browser. Once created, they can be used on mobile.
- **Context window limit on free tier.** The free tier has a context window of 32,000 tokens. Extended multi-turn sessions (long therapeutic conversations) may hit this limit, at which point earlier parts of the conversation will be dropped from context. Users engaged in longer sessions should be aware that continuity may degrade.
- **EU/PT availability.** Users in the EU and Portugal access Gemini through the consumer app (gemini.google.com), not through the API. All instructions above apply to the consumer app path.
