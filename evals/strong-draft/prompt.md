---
description: "Strong draft keeps every supplied fact."
tags: [trigger, coding]
runs: 2
max_turns: 6
allowed_tools: [Read, Glob, Grep, Skill]
---

Improve this prompt: In the repo, the CSV export in src/export/csv.ts drops rows whose `note` field contains a newline. Reproduce with tests/fixtures/multiline.csv, fix the quoting so RFC 4180 is respected, keep the public exportCsv(rows, opts) signature unchanged, add a regression test, and run `pnpm test`.
