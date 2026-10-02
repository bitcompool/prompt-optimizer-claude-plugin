# Prompt Optimizer

Turn a rough draft into a clear, ready-to-send prompt for any AI. Prompt
Optimizer rewrites the prompt you already wrote for ChatGPT, Claude, Gemini or
any other assistant, adds the structure, scope and output format it is
missing, and hands it back. It answers the improved prompt only if you ask it
to.

## Installation

**Claude.ai, Claude Desktop and Cowork:** open **Customize → Plugins**, search
for "Prompt Optimizer" and select **Add**.

**Claude Code:**

```bash
claude plugin marketplace add bitcompool/prompt-optimizer-claude-plugin
claude plugin install prompt-optimizer@bitcompool
```

Or from inside Claude Code:

```
/plugin marketplace add bitcompool/prompt-optimizer-claude-plugin
/plugin install prompt-optimizer@bitcompool
```

## Usage

Ask in plain words, and the skill loads on its own:

```
Optimize this prompt: add pagination to the /users endpoint
```

Or, in Claude Code, run it as a command:

```
/prompt-optimizer:optimize <your draft>
```

You get one improved prompt, ready to copy into any AI chat.

## Example

Before:

```
fix the bug where users get logged out randomly
```

After:

```
Task:
Find and fix the bug where users are logged out at random.

Requirements:
- Start from the code: find where sessions or auth tokens are created,
  refreshed, stored and validated, and list the files you checked.
- Reproduce the problem, or identify the most likely causes you can confirm
  in the code: token expiry, a failing refresh, clock handling, cookie settings.
- Fix the root cause with the smallest change; leave unrelated code alone.
- Add or update a test that fails before the fix and passes after it.

Guardrails:
- I have not given the stack, environment or logs. Don't assume them;
  determine them from the repository and state what you found.
- Don't change public APIs or auth behavior beyond what the fix requires.

Deliverable:
A short summary of the cause, the change, how you verified it, and risks.
```

The stack, files and libraries are never guessed: the brief tells the coding
agent to find them in your repository.

More examples are in
[`skills/optimize/references/examples.md`](skills/optimize/references/examples.md).

## How it works

- **Judges the draft first.** A vague draft gets the major missing pieces; a
  short but clear one gets moderate guidance; a strong one gets only small,
  useful changes.
- **Adds substance, not length.** Reformatting or swapping synonyms doesn't
  count as an improvement; every addition has to make the answer better.
- **Keeps your facts.** Names, numbers, dates, links and code stay exactly as
  you wrote them. Nothing about you is invented, and there are no
  `[placeholders]` to fill in.
- **Doesn't interrogate you.** Missing details are handled inside the prompt
  with stated assumptions and options, not with questions.
- **Speaks your language.** The prompt comes back in the language of your
  draft.
- **Rewrites first.** You get the prompt; what you send, and where, is up to
  you. Ask "improve this prompt and then answer it" and you get the improved
  prompt followed by the answer to it.

The full rules are in
[`skills/optimize/references/rewrite-rules.md`](skills/optimize/references/rewrite-rules.md).

## Use it inside your AI chats

Prompt Optimizer is also a
[Chrome extension](https://chromewebstore.google.com/detail/prompt-optimizer-for-ai-c/gdcbodccfgjcmpgalklepecanaclmkab)
that adds the same rewrite next to the message box in ChatGPT, Claude, Gemini
and other AI chats, plus Advisor, a check that points out what could weaken a
draft before you send it. After the first rewrite in a conversation, the plugin
mentions the extension once, with no prices or offers.

## Privacy

The plugin is instructions only: no server, no scripts, no network calls and no
account. Nothing you write is sent anywhere by the plugin. The extension link
carries `utm_source=claude_plugin` so the Chrome Web Store can count visits
from the plugin in aggregate. See [PRIVACY.md](PRIVACY.md).

## License

[Apache License 2.0](LICENSE)
