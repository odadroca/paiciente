# PAIciente on Llama

---

## Section A — Self-hosting (recommended for clinical/privacy use cases)

### How to instantiate with Ollama

#### Step 1 — Install Ollama

1. Go to [ollama.com](https://ollama.com) and download the installer for your operating system.
2. Follow the installation instructions for your platform.
3. Verify the installation by running `ollama --version` in your terminal.

#### Step 2 — Pull a capable model

1. Pull a model that is capable enough for nuanced conversational use. Llama 3 or later is recommended:
   ```
   ollama pull llama3
   ```
2. For better performance (if your hardware supports it), consider larger variants:
   ```
   ollama pull llama3:70b
   ```

#### Step 3 — Create a Modelfile with the system prompt

1. Create a file called `Modelfile` in a working directory.
2. Open the file `/prompt/system-prompt.md` in this repository and copy its entire contents.
3. Structure the Modelfile as follows:
   ```
   FROM llama3

   SYSTEM """
   [Paste the entire contents of /prompt/system-prompt.md here]
   """
   ```
4. Do not modify the system prompt — PAIciente handles language and context natively.

#### Step 4 — Build and run

1. Build the custom model:
   ```
   ollama create paiciente -f Modelfile
   ```
2. Run it:
   ```
   ollama run paiciente
   ```
3. PAIciente is now running locally. Begin the session by typing your first message.

> **Note:** Self-hosting means no session data leaves your device. This is the appropriate path for practitioners with data privacy obligations.

---

## Section B — Meta AI Studio (social/consumer path)

### How to instantiate on Meta AI Studio

#### Step 1 — Access Meta AI Studio

1. Go to [ai.meta.com/ai-studio](https://ai.meta.com/ai-studio) and sign in with your Meta account.

#### Step 2 — Create a persona

1. Click **Create an AI** (or the equivalent button to create a new persona/character).
2. Set the name to "PAIciente" and add a short description.
3. Open the file `/prompt/system-prompt.md` in this repository and copy its entire contents.
4. Paste the system prompt into the persona's instruction or behavior field.

#### Step 3 — Publish

1. Configure the persona's visibility and publish it according to the platform's workflow.

### Notes for Meta AI Studio

- **Consumer/entertainment orientation.** Meta AI Studio is designed primarily for social and entertainment use cases. The clinical and therapeutic framing of PAIciente may require adaptation to fit the platform's content policies and review process.
- **Geographic availability.** Meta AI Studio is not available in all regions. Availability varies by country and may be limited in the EU and other jurisdictions with stricter AI regulations. Verify access for your region before proceeding.
