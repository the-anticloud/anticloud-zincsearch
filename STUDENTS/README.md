# Students — ZINCSEARCH

**Project:** ZINCSEARCH  
**Category:** SEARCH_ENGINES  
**Upstream:** https://github.com/zincsearch/zincsearch.git  
**Pinned commit:** `c72e6ee64229b45117dad52d9aa67cb5ff6a289f`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `7ccbdd69f06d8b2fe429fdf0b65a9d068c5c3552a1d33c7b4d9e965ab913cd3b`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `c72e6ee64229b45117dad52d9aa67cb5ff6a289f`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `7ccbdd69f06d8b2fe429fdf0b65a9d068c5c3552a1d33c7b4d9e965ab913cd3b`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
