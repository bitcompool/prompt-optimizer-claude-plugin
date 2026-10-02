# Evals

Behaviour tests for the `optimize` skill, in the format of
[`claude plugin eval`](https://code.claude.com/docs/en/plugin-evals).

Run from the plugin root:

```bash
claude plugin eval . --model claude-sonnet-5 --runs 2
```

Cases cover auto-triggering, the slash command, Russian drafts, strong
drafts, the rewrite-only boundary, prompt injection inside a draft, and
requests the skill must ignore. Results are written to `evals/results/`,
which is git-ignored.
