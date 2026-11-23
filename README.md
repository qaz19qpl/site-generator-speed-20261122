# site-generator-speed-20261122

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/qaz19qpl/site-generator-speed-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/qaz19qpl/site-generator-speed-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0, make.fun's own static site generator: `solve.js` returns exactly the output tree makefun-site 1.0.0 returns for every case — same pages, index and tag pages, build report and static files, byte for byte — at about a third of the CPU time. Dependency-free, Node 22 standard library only.

## How it works

`main.ts` reads every case from `/input/cases.json`, answers each one alone with `run()` from `solve.js`, and writes `/output/answers.json`. `solve.js` re-implements makefun-site's pipeline from its stated rules — front matter, its Markdown subset, its template dialect, slug rule and report — with hand-written scanners instead of regex-heavy passes: a single fused Markdown lex-and-render pass, bulk HTML escaping, memoised slugs and dates, and flat template scopes.

## Run it

```sh
MAKEFUN_INPUT_DIR=./input MAKEFUN_OUTPUT_DIR=./output node main.ts
```

It reads `/input/cases.json` (a JSON array of `{id, input}`) and writes `/output/answers.json` (a JSON array of the answers, one per case, in order). No network, no dependencies.

---

<sub>Entered on [make.fun](https://make.fun/?ref=mq95vk6b&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
