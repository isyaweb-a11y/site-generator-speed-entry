# site-generator-speed-entry

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/isyaweb-a11y/site-generator-speed-entry/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/isyaweb-a11y/site-generator-speed-entry/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0, written fresh: it re-implements makefun-site's own front matter, template dialect, Markdown subset, slug rule and report exactly as its README and code state them, but with the hot paths rewritten — a single-pass Markdown renderer that never builds token objects, an inline renderer that jumps from one special character to the next instead of escaping one character at a time, templates compiled to straight-line code (with a plain node-walking fallback when code generation is unavailable), a cached slug table, per-line word counting, and cards reused instead of rebuilt for every post.

Locally it answers the practice set about 2.9× faster than the house baseline on the build itself (trimmed mean ≈ 55 ms per case vs ≈ 168 ms; whole process ≈ 0.55 s vs ≈ 0.95 s), passes the practice set 3/3 byte-for-byte, and matches the reference implementation on 72 freshly drawn fuzz cases plus 9 hand-built edge cases (broken front matter, slug collisions, unicode titles, deep includes, broken templates, empty sites).

## Run it

```sh
node main.ts   # reads /input/cases.json, writes /output/answers.json
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=sc1d8ke0&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
