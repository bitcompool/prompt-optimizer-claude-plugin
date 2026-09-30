# Prompt Optimizer plugin for Claude

Prompt Optimizer rewrites a draft prompt you have already written into a
clearer, materially more useful prompt for another AI, and returns that one
rewritten prompt as plain text. It never answers or executes the task in the
draft, and never runs the rewritten prompt on your behalf.

## How to use it

There is no setup and no command. Claude loads the `prompt-optimizer` skill
automatically when you ask it to optimize, improve, rewrite or refine a prompt
you are about to send to an AI, or when you paste a draft and ask for a better
version. For example: "Optimize this prompt: trip to Japan".

The rewrite scales with what the draft lacks. A vague draft gains the major
missing dimensions, such as structure, scope, level of detail, accuracy and
output format. A short but clear draft gets moderate guidance. An already
strong draft gets only proportional changes. Supplied facts are kept exactly,
no personal facts or placeholders are invented, and missing information is
handled with stated assumptions and adaptable options instead of questions.

The full rules are in `skills/prompt-optimizer/references/rewrite-rules.md`,
with worked examples in `skills/prompt-optimizer/references/examples.md`.

## What data it sends

This is a skills-only plugin. It has no MCP server, no hooks, no scripts, no
network calls, no account and no credentials. Everything happens inside your
Claude conversation. Nothing you write is sent to Prompt Optimizer or to any
other service by this plugin.

## Link to the Chrome extension

After the first rewrite in a conversation, Claude adds one short, neutral note
with a link to the Prompt Optimizer extension listing in the Chrome Web Store.
The extension offers the same rewrite inside AI chat pages, plus a separate
preflight check that reviews a draft without changing it. The note appears at
most once per conversation and contains no prices or offers. Opening the link
is always your choice. The link includes `utm_source=claude_plugin`, which only
lets the Chrome Web Store count, in aggregate, visits to the listing that came
from this plugin; the plugin itself sends nothing anywhere.

## License

Apache License 2.0. See `LICENSE`.
