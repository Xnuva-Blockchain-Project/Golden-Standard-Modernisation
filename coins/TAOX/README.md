# TaoX / TAO Revival — engineering register

**Status:** EXPERIMENTAL; not release approved, and RandomX mainnet activation is disabled. Do not change the existing live Tao Revival chain.

**Source:** [Tao development branch](https://github.com/Xnuva-Blockchain-Project/Tao/tree/modernisation/taox-consolidated-full-source)
**Baseline commit:** `3eb33acd901cb28392258c168d87ee0e70261076` (CP25X, 23 November 2026)

## Chronological development history

| Date | Checkpoints | Recorded milestone | Qualification scope |
|---|---|---|---|
| 21–22 Nov 2026 | CP102–137J | Modular PoW, historical replay and legacy UTXO investigation | See v1.16 archive §§16.6A,16.8–16.9; negative regression still open |
| 22–23 Nov 2026 | CP24T–25F | Contextual RandomX recovery, reindex and wrong-seed fixture | Isolated experimental chain |
| 23 Nov 2026 | CP25J–25N | Genuine G/H 35-block P2P sync and malicious-header rejection | Local P2P laboratory, not presync/redownload adversarial qualification |
| 23 Nov 2026 | CP25O–25U | Backup restoration, mature coinbase spend, confirmation and restart persistence | Disposable Node J only |
| 23 Nov 2026 | CP25V–25W | Repeatable checks and local evidence report | Report content remains on operator machine |
| 23 Nov 2026 | CP25X | 8 local source commits pushed to development branch | No mainnet changes, no release |

## Verified identifiers and integrity records

| Artifact | Identifier / digest | Meaning |
|---|---|---|
| Committed source baseline | `3eb33acd901cb28392258c168d87ee0e70261076` | Git commit SHA-1, **not** binary checksum |
| Node J confirmed block 35 | `a41f9de0ac03b8f393faeb5ef937f097104c481070be3a706578898dc5a400ba` | Regtest block hash |
| Payment confirmed in block 35 | `861240eeb5a636bd899918e27909a5d6ee6deaba67985c2652a39d2700db002a` | Regtest transaction ID |
| Original wallet backup | SHA-256 `4994ed6bed1787b7d465cf8fc912ed7e49bdf396fe60c4edba2ed89a7a33b2d3` | CP25W reports checksum matched; never publish wallet file |
| CP25W local qualification report | SHA-256 `a6ddc061be0481896719b113a3115a547d8a8739ba8def9047f2cdcc73aecd47` | Local-only report, not uploaded to this public repository |
| Historical block 34 tip | `194b97ca6382447b00dc5cbee88f36675adcfdc5132bdb0b80c4c50e6f1b558e` | Regtest reference |

**Operator-local report:** `~/taox-release-qualification/taox-cp25w-20261123T143729Z.txt`. This path is a pointer, not an uploaded evidence bundle. The three uncommitted wallet source files (`addresses.cpp`, `spend.cpp`, `wallet.h`) are intentionally not in the pushed commit.

## Completed / outstanding tests

See [the 35-item RandomX register](../../randomx/checklist.md). It distinguishes reported PASS from O / blocked. The major remaining gates are real adversarial P2P presync/redownload; future-block propagation; wallet changes and reorg cases; full historic Tao chain and UTXO/wallet equivalence; clean release builds, 24–48h soak, rollback and independent review.

## Release decision

**HOLD.** Experimental regtest successes do not justify mainnet RandomX activation. Any future activation requires a separately approved forward-only consensus plan.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

