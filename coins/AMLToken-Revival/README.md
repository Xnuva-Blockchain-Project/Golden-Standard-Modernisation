# AMLToken Revival (historical native ABTC precursor) — engineering register

**Project classification:** **STASIS / HISTORICAL PRESERVATION** — not an active migration, live replacement-chain launch, or approved first software release. A deliberate pause of approximately six weeks was recorded on **14 September 2026**. This document records the last reviewed September 2026 evidence; the **current operating status of public nodes has not been rechecked**.

**Authoritative repository:** [Xnuva-Blockchain-Project/AMLToken-Revival](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival)  
**Project source of truth:** [README](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/README.md) and [public evidence register](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/EVIDENCE_REGISTER.md) (historical snapshot of 14 September 2026).

## Identity and preservation covenant

The project concerns the **original native AMLToken / ABTC precursor blockchain**. It is **not** a revival or validation of the later AML Bitcoin product, its advertised proprietary biometric/AML/KYC technology, or an unrelated token using ABTC. The historical legal and marketing context is addressed by the source project's [scope and terminology](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/SCOPE_AND_TERMINOLOGY.md).

**Non-negotiable rule: Same genesis. Same historical ledger. Same ownership.** No invented re-genesis, synthetic balances, rewritten historic transactions, or mining a replacement production history to bypass missing authentic blocks.

## Chronological project history and evidence

| Date | Workstream | Last documented finding | Qualification boundary |
|---|---|---|---|
| Original client / 2017–2018 | Native AMLToken v1.3.0 identity | Bitcoin-Core-derived C++ client; mainnet genesis and original SHA256d PoW reproduced | Not proof of advertised later AML Bitcoin features |
| Prior to 14 Sep 2026 | Reconstruction and wallet continuity | Preserved Windows/Linux artefacts inspected; original 2018 Berkeley DB wallet recognised by historical client | Does not prove every holder's complete present balance |
| 14 Sep 2026 | Historical chain recovery | Authenticated original genesis through block **175168**; same tip and chainwork on three project-controlled hosts | Snapshot is **not** asserted final historical network tip or independent third-party reproduction |
| 14 Sep 2026 | Networking investigation | Original `PeerAllowed()` / 13-entry authorized-peer table and five direct call sites documented | Historically observed gate; revival must not recreate privileged peer access |
| 14 Sep 2026 | Public discovery / archival infrastructure | Two walletless, non-mining discovery nodes reported operational on separate networks | **Historical report only**; present-day node availability not verified |
| 14 Sep 2026 | Public documentation | Technical preview, holder guidance and independent reproduction challenge published | Not a functional new-chain launch |
| 14 Sep 2026 | Preservation checkpoint / pause | Planned ~six-week pause recorded; continuation deliberately deferred | **STASIS**; no resumed development inferred |
| 17 Sep 2026 | Independent source mirror | Operator reported Git bare mirror at `/mnt/storage1/github-mirror/Xnuva-Blockchain-Project/AMLToken-Revival.git` and `git fsck --full` PASS | Mirror state reported at that time; not recently reverified |

## Chain identity and forensic checksums

Full values and provenance: [chain identity](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/CHAIN_IDENTITY.md), [evidence register](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/EVIDENCE_REGISTER.md) and [independent reproduction](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/INDEPENDENT_REPRODUCTION.md).

| Item | Recorded value | Classification |
|---|---|---|
| Mainnet genesis | `00000000230d6b389555e80e4523a32343531448ddd15fbc29c0fdc11dbb1538` | Chain block hash, not file checksum |
| Last authenticated snapshot height | `175168` | Historical block height |
| Snapshot tip | `000000008be329b7f5186e61c86367ece62db781374cc7c4fee46ba296b40025` | Chain block hash |
| Snapshot chainwork | `00000000000000000000000000000000000000000000000000048f2b9dfa1d51` | Consensus cumulative work |
| Mainnet message magic | `0d 1c 81 52` | Historical network identifier |
| Default P2P port | `23247` | Historic node setting |
| Original consensus PoW | `SHA256d` | **No RandomX migration has been approved** |
| Bitcoin Core upstream baseline candidate | `e278f86c536921032e8288625dc5f3af610f2ec8` | Upstream Git commit, not complete original AML source |
| Clean reconstruction source used in replay | `8b821d120b6331cb9ac83c764863e032f567b776` | Source commit recorded in historical reproduction evidence; complete source publication outstanding |
| Authenticated `blk00000.dat` | SHA-256 `77b005775f3d87429571a52b491aeadd0787b3350b3b96249fb1a169964cbf03` | Archived raw-block file integrity |
| Original Windows `AMLToken-Qt-1.3.0.exe` | SHA-256 `39cc74896e0fc6ebf313fe8a880be6f74466f8f4314fdff889a73053c23297dd` | Preserved binary |
| Original Windows ZIP package | SHA-256 `476036079d4999124ac1e120ec400589d012a907abfb38c072930e7ef9669abb` | Preserved package |
| Original Linux `AMLToken-Qt` | SHA-256 `61c61988ef5e672ab3aeaa2dba9410f161907433a96c0755cd6484e78d6089d4` | Preserved binary |
| Reconstruction `bitcoind` | SHA-256 `28bf755af53c784b3ab47d7838c65952d6a97031d103006cf58f893edb4f1aae` | Historical test build |
| Reconstruction `bitcoin-cli` | SHA-256 `5ca9888fbfd9002fe88d0e441a729f1e5c333c573bb7ff8ef47312b42417bfc0` | Historical test build |

These hashes are **transcribed from the source project's documented evidence**, not freshly recomputed from archived binaries or blocks in this GSH maintenance session. Keep original file snapshots immutable, and compare new builds to the correct revision—not to unrelated binaries.

## Completed historical tests and open gates

See [status checklist](tests.md). In brief, documented project-controlled PASS includes genesis identity, original wallet-format recognition, authenticated 175168-block historical snapshot and triple-host full reindex. Mandatory gates still open: recovery or proper disposition of later authentic history, public clean reconstruction-source and block-data package, unaffiliated reproduction, audited unrestricted networking, wallet balances and complete end-to-end continuation tests.

**RandomX classification: NOT APPLICABLE TO CURRENT STASIS.** If an eventual revival decides to evaluate RandomX, that is a **new separately governed forward-only consensus proposal**, not a continuation of the presently documented SHA256d recovery. The shared [RandomX checklist](../../randomx/checklist.md) must not retroactively relabel the historic work.

## Resumption rules

1. Verify integrity and current state of archived Git refs, binaries, raw blocks, wallets (privately) and mirror before changing anything.
2. Confirm whether any authentic continuation after height 175168 has been discovered, preserving candidate data read-only until independently validated.
3. Publish/reconcile exact clean reconstruction source and safe public chain artefacts for third-party replay; original source evidence states this is incomplete.
4. Obtain independent third-party reproduction and a second historical-ledger/state comparison before further revival qualification.
5. Plan mining, open peer connectivity, wallets, transaction and restart checks in disposable environments; never relaunch by manufacturing history.
6. Require explicit operator decision to leave stasis. Do not schedule RandomX integration or release merely because other coins are modernising.

**Release decision: HOLD / STASIS.** No current live network status or release-readiness claim.
