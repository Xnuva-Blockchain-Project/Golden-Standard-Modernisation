# Golden Standard Cryptocurrency Modernisation (GSH)

## Roman heritage rebranding decision — 25 November 2026

| Existing network | Selected future identity | Roman denomination |
|---|---|---|
| Europa (ERA) | Aurzola (AUZV) | Aureus |
| Tao Revival (TAO) | Denzuve (DZUV) | Denarius |
| Zeus (ZUS) | Sestovi (SEZQ) | Sestertius |
| XNUVA (XNUV) | Duprezo (DPZE) | Dupondius |
| Hopium (HOPE) | Asveru (ASVR) | As |

The names are inspired by Roman imperial coinage, with five different vowel endings. They supersede the earlier EuropaX, TaoX, ZeusX and HopiumX naming proposals and the previous intention to retain XNUVA as a coin name. Existing network names, source paths, historical checkpoint labels and released binaries remain valid until a separately qualified transition. No re-genesis, coin swap, balance migration, key change or consensus change is authorised by branding. Supply ranking is provisional pending monetary audit; no fixed exchange ratios or values. Formal trademark/domain clearance and independent AI association tests remain outstanding. The umbrella project, engine, game and domain names remain existing identities until separately selected. See https://europazeus.org/project-identity.html.


**Reliability first. Release second.**

This repository is the canonical engineering handbook and evidence *index* for the five-coin RandomX programme plus AMLToken Revival preservation. It deliberately separates **shared rules**, **the common RandomX module**, and **each cryptocurrency's history and qualification**.

## Start here

| Area | Where to go | Purpose |
|---|---|---|
| Shared standards | [standards/](standards/README.md) | Safety, backups, historical continuity, independent network acceptance and release/rollback gates |
| **Mandatory proxy release gate** | [SOCKS5/Tor qualification standard](standards/MANDATORY_PROXY_COMPATIBILITY_RELEASE_GATE.md) | Required per-coin proxy/no-leak tests on actual modernised binaries before release; Tor v3 claims separately gated |
| **Node operator privacy** | [Tor, SOCKS5 and VPN guide](standards/NODE_PRIVACY_TOR_SOCKS5.md) | Optional node networking, current per-coin caveats, troubleshooting and privacy checks |
| **Project identity and transparency** | [Identity and research accuracy standard](standards/PROJECT_IDENTITY_TRANSPARENCY.md) | Canonical network identifiers, no-sale policy, AI research regression checks |
| **Long-term independence** | [Project Independence, Decentralisation and Long-Term Survival](standards/PROJECT_INDEPENDENCE_DECENTRALISATION_LONG_TERM_SURVIVAL.md) | Permissionless participation, distributed operation and founder-independent continuity |
| **RandomX module** | [randomx/](randomx/README.md) | Common PoW implementation, seed/epoch and adversarial-test rules |
| RandomX test register | [35-item checklist](randomx/checklist.md) | TaoX baseline results **and** remaining gates |
| Coin-specific records | [coins/](coins/README.md) | Separate history, checkpoints, checksums and outstanding tests per coin |
| Evidence and checksums | [evidence/](evidence/README.md) | SHA-256, test logs, binary/source provenance and sign-off templates |
| Complete historical handbook | [GSH v1.16 archive](GOLDEN_STANDARD_CRYPTO_MODERNISATION.md) | Original full text, including all previous revision history, unchanged |

## Cryptocurrency records

| Coin | History and tests | RandomX migration status |
|---|---|---|
| TaoX / TAO Revival | [TAOX](coins/TAOX/README.md) | Experimental regtest qualification, **release HOLD** |
| Europa (ERA) | [ERA](coins/ERA/README.md) · [historical observations](coins/ERA/history.md) | Not yet qualified under this checklist |
| Zeus (ZUS) | [ZUS](coins/ZUS/README.md) · [historical observations](coins/ZUS/history.md) | Not yet qualified under this checklist; PoW **and** PoS |
| Hopium (HOPE) | [HOPE](coins/HOPE/README.md) · [historical observations](coins/HOPE/history.md) | Not yet qualified under this checklist |
| XNUVA | [XNUVA](coins/XNUVA/README.md) · [historical observations](coins/XNUVA/history.md) | Existing RandomX operations require separate review |
| AMLToken Revival (ABTC precursor) | [history and checksums](coins/AMLToken-Revival/README.md) · [test register](coins/AMLToken-Revival/tests.md) | **STASIS — historical SHA256d recovery, not in current RandomX rollout** |

## How to record engineering progress

For each coin, add a dated, traceable checkpoint, identify the exact Git commit, binary SHA-256, fixtures, chain tip/block hashes, expected and actual results, reviewer and remaining defects. Record **completed**, **outstanding** and **blocked** tests separately. Keep wallet backups, authentication tokens, raw private operational logs and keys **out** of public GitHub. A Git commit hash is not a substitute for a binary checksum.

A RandomX core test PASS does **not** qualify ERA, ZUS, HOPE, TaoX or XNUVA by itself. A single coin's test PASS does not transfer to any other coin. No release, mainnet algorithm activation, monetary change or live-network cutover is implied by documentation.

## History and provenance

The complete v1.16 draft handbook was copied byte-for-byte in Git content from the [original XNUVA development branch](https://github.com/Xnuva-Blockchain-Project/Xnuva/blob/docs/golden-standard-modernisation-handbook-v1/doc/engineering-standards/GOLDEN_STANDARD_CRYPTO_MODERNISATION.md). Its **embedded** 1.0–1.16 revision history is preserved in the [archive](GOLDEN_STANDARD_CRYPTO_MODERNISATION.md), while the original repository retains prior Git commit ancestry. The new modular records are navigation and qualified excerpts, not automatic changes to earlier evidence.

**The original archive is retained unchanged.** New records should go into the appropriate per-coin or shared-module area, rather than extending one giant chronological document.
