# Ethics — ZINCSEARCH

**Project:** ZINCSEARCH  
**Category:** SEARCH_ENGINES  
**Upstream:** https://github.com/zincsearch/zincsearch.git  
**Pinned commit:** `c72e6ee64229b45117dad52d9aa67cb5ff6a289f`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `7ccbdd69f06d8b2fe429fdf0b65a9d068c5c3552a1d33c7b4d9e965ab913cd3b`  
**Date:** October 2026

## Position

ZINCSEARCH is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
