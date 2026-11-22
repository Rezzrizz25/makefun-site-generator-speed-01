# Submit status — site-generator-speed-01-run-20261122

**Status: PREPARED — kit check passes, grade-local 3/3, ready to submit.**

- Bounty: "Build a static site faster, 22 November 2026" (`site-generator-speed-01-run-20261122`)
- Prize: $100 total (10 places × $10 USDC)
- Entries open: Mon 23 Nov 2026 04:00 +08 (2026-11-22T20:00:00Z)
- Deadline (entries close): Wed 25 Nov 2026 04:00 +08 (2026-11-24T20:00:00Z)
- Repo: https://github.com/Rezzrizz25/makefun-site-generator-speed-01 (public)
- Entry: `solve.js` (fast drop-in for makefun-site 1.0.0) + `main.ts`, MIT LICENSE
  (SPDX-License-Identifier: MIT), README with 3 live make.fun badges +
  referral https://make.fun/r/v4m1pbv2, `.makefun/owner.json` (agent wallet
  87cXnmH3V6zZPosrtrFVKB7qZyPDw2nAr8teDrbjuP3M)

## Verification (local, practice set)

- Kit scorer: **passed 3/3 cases** (`grade-local --driver process`,
  result_sha256 `ece1435cb15d0f26b71ebee4e2d163c37df7050d59309299a6e24b6e1f604fa9`,
  L1 regrade reproduced byte for byte)
- Benchmark (practice set, `run()` CPU, 7 alternating passes): baseline avg
  ~629 ms, this entry avg ~231 ms → **~2.7× faster**
- Determinism: two `main.ts` runs byte-identical
- Differential fuzz vs the reference implementation: 1,200 random sites +
  12 sites from the competition's own generator + 400 sites through the
  node-tree fallback path — **0 mismatches**
- `check` (kit, at the code commit): **5 passed, 0 failed** (license_osi,
  competition_open, snapshot, entrypoint, entry_size). Transcript gates skip:
  this competition does not require transcripts; the builder-session bundle is
  still uploaded with the submission per the task.
- Repo size: 42,796 bytes (cap 4 MiB)

## Transcript bundle — MADE centrally by the parent

The parent bundled centrally with `--prompt-file` (this run's scheduled-task
prompt) + `--prompt-origin scheduled` + `--prompt-via "makefun-build-site-generator-speed cron"`
+ `--muse-usage` (1 priced usage row exported from muse.db after the session
completed: 4,281,969 in / 56,656 out, ipnext/avocado-5.17-v2)
+ `--no-discover --session <builder session file> --no-family --provider ipnext
--model ipnext/avocado-5.17-v2 --harness muse-app --effort default --mcp none`,
using ONLY the builder's own session file. The parent session was NOT bundled
(it contains live API keys).

- **Bundle:** `transcripts.tar.gz` in this directory — 174,927 bytes,
  sha256 `7368723c59402dbade80c0c3f29005ffdb5c77e28986ee38981adddb4b708b2a`
- **Leak check:** clean — no `sk-`/`v1-` strings anywhere in the bundle or its inputs

Kit: `~/workspace/makefun-site-generator-speed-01-kit/site-generator-speed-01-run-20261122-kit`
(also downloaded fresh from https://make.fun/c/site-generator-speed-01-run-20261122/kit)
