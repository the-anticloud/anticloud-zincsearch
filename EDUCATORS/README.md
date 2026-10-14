# Educators — ZINCSEARCH

**Project:** ZINCSEARCH  
**Category:** SEARCH_ENGINES  
**Upstream:** https://github.com/zincsearch/zincsearch.git  
**Pinned commit:** `c72e6ee64229b45117dad52d9aa67cb5ff6a289f`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `7ccbdd69f06d8b2fe429fdf0b65a9d068c5c3552a1d33c7b4d9e965ab913cd3b`  
**Date:** October 2026

## Teaching with ZINCSEARCH

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `7ccbdd69f06d8b2fe429fdf0b65a9d068c5c3552a1d33c7b4d9e965ab913cd3b` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
