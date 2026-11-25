# Denzuve (DZUV) / TAO Revival — engineering register

The earlier TaoX/TOAX branding is superseded as of 25 November 2026. Historical branch paths, checkpoint names and experimental evidence retain their original labels.

**Status:** EXPERIMENTAL; not release approved, and RandomX mainnet activation is disabled. Do not change the existing live Tao Revival chain.

**Canonical source:** [Denzuve development branch](https://github.com/Xnuva-Blockchain-Project/Denzuve/tree/modernisation/denzuve-transition-release-1) (since K12C, 25 November 2026)
**Historical source:** [Tao consolidated development branch](https://github.com/Xnuva-Blockchain-Project/Tao/tree/modernisation/taox-consolidated-full-source)
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

**Operator-local report:** `~/taox-release-qualification/taox-cp25w-20261123T143729Z.txt`. This path is a pointer, not an uploaded evidence bundle. At CP25X, the three wallet source files (`addresses.cpp`, `spend.cpp`, `wallet.h`) were intentionally excluded from that historical commit. Subsequent functional integration was preserved separately in the 25 November baseline below.

## 25 November 2026 — Denzuve development preservation

**Evidence status: P (operator-reported scoped results); release HOLD.**

| Checkpoints | Milestone / scope |
|---|---|
| 26DD-B–H | Isolated regtest mining, two local peers, maturity and payment, RandomX seed transition, wallet backup/restore and three registered RandomX tests reported PASS. Same physical host; wider adversarial and historical compatibility tests remain open. |
| 26DD-K1C | Functional integration preserved at [2c8e64f](https://github.com/Xnuva-Blockchain-Project/Tao/commit/2c8e64fc0aac35055f9f0a17f1a48404596e0a0e). |
| 26DD-K2–K9B | Branded executables, DZUV / Princeps display, config and storage separation, payment URI changes and isolated GUI-enabled compilation. Seven application binaries recorded. |
| 26DD-K10B | Fresh regtest daemon and RPC dispatcher, Denzuve subversion, default data directory, DZUV fee label, amount regression and clean shutdown reported PASS. Networking disabled; not independent network acceptance. |
| 26DD-K10C–K10G | Native test clock, genesis transaction, contextual Scrypt/RandomX mining, 20-block maturity and P2PKH address fixtures corrected; all six Qt test groups passed (21 Qt results including setup/cleanup, zero failures, 152.95 seconds). Fixed deterministic test-tip assertion restored and reproduced. |
| 26DD-K11A | Common 960 × 540 splash renderer implemented following XNUVA design standard. Not yet compiled or visually qualified; final artwork deferred after image generation failure. |
| 26DD-K11C | 50 files committed and pushed; operator verified local and remote SHA match, clean working tree, protected functional source and existing binary checksums. No production change or mainnet activation. |

**Current development branch:** [modernisation/denzuve-transition-release-1](https://github.com/Xnuva-Blockchain-Project/Denzuve/tree/modernisation/denzuve-transition-release-1)  
**Preserved source commit:** [df98de7b8d23420d37d358cdd5e7bc3fda200821](https://github.com/Xnuva-Blockchain-Project/Tao/commit/df98de7b8d23420d37d358cdd5e7bc3fda200821)  
**Pre-commit patch SHA-256:** `a7292b1aeecb18e2044b90666d5cca0c8e7f5de84128804a62009920b517ea3d`  
**Native 20-block test fixture tip:** `5a93a1067a38c3d0462e69d997a3b12b7dc7d1fd90f4bae91b58325900bb3e19`  
**Evidence pointers (operator-local, not uploaded):** K9B application binary manifest; K10G GUI test binary manifest and regression log; K11C pre-commit patch. Exact binary digests are not reproduced here. The GUI tests preceded the splash renderer changes: the final committed source has not undergone a clean build or full qualification.

**Dependency reproducibility blocker:** declared shared foundation pin `857841056ed939eeea4fd640463b54b6a5cd54af` differs from effective local override `546a21488dc3a03588094b4e9bdff6535534bcef`; underlying XNUVA source checkout `853a3171ece198f60b5125a16dca83d68a8f53c3`. Reconcile committed pins, remote availability and clean-build qualification before release.

**Next gates:** remaining user-facing branding and packaging, functional test harness adaptation and historical binary isolation, splash artwork and visual/high-DPI qualification, reproducible dependency pins, full core and adverse-condition regression, historical chain and legacy wallet continuity, independent peer acceptance, proxy tests, restart/recovery, sustained operation and rollback. Mainnet RandomX activation remains -1; regtest activation 2, epoch length 16. No public release authorised.

## 25 November 2026 — Independent repository consolidation (K12–K12C)

**Evidence status: P (operator-reported scoped PASS).** The new public [Denzuve repository](https://github.com/Xnuva-Blockchain-Project/Denzuve) is the canonical development destination. Both main and the transition development branch were populated at [734b201f022c86a445858f065048f337073f13f8](https://github.com/Xnuva-Blockchain-Project/Denzuve/commit/734b201f022c86a445858f065048f337073f13f8). Main is an experimental baseline, not an approved release.

- K12: independent project README committed; initial push rejected because of missing ancestral object.
- K12A/B: shallow clone identified and unshallowed from Tao; missing commit recovered, Git integrity checks passed; 167 reachable commits and 4,794 objects transferred without history rewriting. Unreachable dangling blobs reported, not integrity failures.
- K12C: local origin switched to Denzuve; tao-legacy retained for historical access. Both remote branch SHAs matched, working tree clean, all ten existing executable checksums matched, modernised source unchanged from K11C apart from repository documentation.
- Complete history bundle SHA-256: `5bb8ed907c6e7df39d92c398de9fa61690fcd7f7dd86a6a3d350449d9a3fbc30` (operator-local backup, not uploaded). Historical Tao development branch remains at K11C; no obsolete branch or tag mirroring, deletion or force push.
- No production deployment, mainnet activation, release tag or approved release. All remaining software and release qualification gates still apply. Local working directory and build paths retained for compatibility.

## 25 November 2026 — Dependency, graphical and localisation preservation (K15–K17F2)

**Evidence status: P (operator-reported scoped results); release HOLD.**

| Checkpoints | Milestone |
|---|---|
| K15A–E | Fresh dependency build reported with foundation pin `546a21488dc3a03588094b4e9bdff6535534bcef` and engine pin `853a3171ece198f60b5125a16dca83d68a8f53c3`, no local overrides; foundation 3/3, engine 107/107 and adapter selftest/wrong-seed discrimination reported PASS. This is component evidence, not node-level wrong-seed rejection or final reproducibility qualification. Seven application executables built before final rebranding. Preserved at [2420d10](https://github.com/Xnuva-Blockchain-Project/Denzuve/commit/2420d10e17d6df77bba932ba7c6f5ae3bfcb8931). |
| K16A–I | Graphical source integration, 11 modified files and 11 new assets, published at [278f800](https://github.com/Xnuva-Blockchain-Project/Denzuve/commit/278f8004128349fdaeb47486d9dc2d7a228b2d4b). Runtime, high-DPI and platform packaging qualification outstanding. |
| K17A–D | GUI, RPC and CLI presentation changes and four test message assertions reconciled; test logic preserved by reported AST comparison. Published at [d1c118f](https://github.com/Xnuva-Blockchain-Project/Denzuve/commit/d1c118ffe678092609605a69c7c293d91e4ee452). Functional tests not executed. |
| K17E–F | 100 inherited TS catalogues retained; 15 GUI source keys mapped, 804 old matches, zero collisions. Eight localisation foundation files created; 11/11 foundation checks reported PASS. Generator, catalogue migration and Qt integration outstanding. |
| K17F1–F2 | Both application and localisation commits published; operator reported matching local and remote SHA, clean working tree, unchanged protected source and artwork checksums. |

**Latest preserved development commit:** [032c97bc35ac8bb42fdfb05b7a48e9c2c5443bfa](https://github.com/Xnuva-Blockchain-Project/Denzuve/commit/032c97bc35ac8bb42fdfb05b7a48e9c2c5443bfa). The earlier dependency override blocker was addressed in the reported K15 laboratory; repeat clean dependency resolution on the final candidate. The independent [Localisation repository](https://github.com/Xnuva-Blockchain-Project/Localisation) exists but transfer and integration remain pending. See [shared localisation standard](../../standards/README.md#modular-localisation-and-branding-preservation).

**Next gates:** complete localisation, remaining compatibility references, packaging, documentation and branding audit; clean build and visual verification; full registered 157-test suite (plus outstanding component and additional release gates), historical replay, legacy wallet migration, independent peer and cross-machine acceptance, proxy qualification, sustained operation and rollback. Mainnet RandomX activation remains -1 (epoch 0); isolated regtest activation 2 (epoch 16). No production deployment, release or activation authorised.

## Completed / outstanding tests

See [the 35-item RandomX register](../../randomx/checklist.md). It distinguishes reported PASS from O / blocked. The major remaining gates are real adversarial P2P presync/redownload; future-block propagation; wallet changes and reorg cases; full historic Tao chain and UTXO/wallet equivalence; clean release builds, 24–48h soak, rollback and independent review.

## Release decision

**HOLD.** Experimental regtest successes do not justify mainnet RandomX activation. Any future activation requires a separately approved forward-only consensus plan.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

