# RandomX migration test register — baseline 23 November 2026

The following table is **copied from the GSH v1.16 section 16.11.1**. It records TAOX checkpoint-reported tests and known outstanding gates; it is not a claim of release approval. The statuses in this historical snapshot should not be silently changed: subsequent updates belong in the per-coin test logs with dates, commits and evidence.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

## Denzuve — historical TAOX baseline, performed vs outstanding

TAOX is the historical experimental label; the selected future public name is Denzuve (DZUV). Evidence below is preserved verbatim.

| ID | Mandatory test / assertion | TAOX status | Test evidence / exact boundary |
|---|---|---|---|
| CX-01 | Isolated development branch and exact commit pinned | P | CP25X; TaoX \`3eb33acd901cb28392258c168d87ee0e70261076\`; GitHub branch synced |
| CX-02 | No live-network activation, no historical re-genesis, preserve source chain | P | CP25V/W; mainnet RandomX activation = -1; no production deployment |
| CX-03 | Modular RandomX compiles/links and genuine daemon executes | P | CP133–137J and CP25-era build checkpoints; clean independent rebuild still O |
| CX-04 | Historical genesis, mainnet network magic and ancestry pinned | P (partial) | Prior TAO revival fixtures and 637-block replay; independent full-chain equality still O |
| CX-05 | Historical block replay and deterministic chainwork comparison | P (partial) | CP129–132, CP137J-AD–AI/AK–AS; legacy UTXO RPC crash/equivalence blocker remains O |
| CX-06 | Scrypt/legacy pre-activation block acceptance | P | Regtest height 1 and existing historical-block tests; full mainnet regression O |
| CX-07 | RandomX hash determinism, target boundaries, algorithm selection | P | CP25C–F, earlier module/PoW checks |
| CX-08 | RandomX seed epoch derivation and transition boundaries | P | Regtest seed transitions at heights 18 and 34; varied epochs/forks O |
| CX-09 | Wrong-seed target distinguishability and negative block rejection | P | CP25E/F, nonce 5, \`high-hash-contextual\` |
| CX-10 | Block mining, nonce exhaustion handling, difficulty checks | P (partial) | \`6dd311d\` nonce correction; CP25T real regtest mining; non-regtest difficulty transition O |
| CX-11 | RPC mined block accepted and readable after restart | P | CP25T/U; block 35 \`a41f9de0ac03b8f393faeb5ef937f097104c481070be3a706578898dc5a400ba\` |
| CX-12 | Normal raw-block import/reindex and restart | P | CP24T/U; CP25J source-node reconstruction |
| CX-13 | Out-of-order raw-block reindex (parent after child) | P | CP24Y/Z; \`-reindex\` proven, do not infer \`-loadblock\` recovery |
| CX-14 | Independent positive P2P header/block synchronisation | P | CP25J; G/H 35 matching blocks, epoch boundaries |
| CX-15 | Negative P2P \`headers\` message rejected and *not indexed* | P | CP25N; wrong-seed header \`50855023878f6f50f9cec160a0090f2f70a9b18282d2c445b2e4db0d33192406\`; misbehaving log |
| CX-16 | Presync low-work valid and malicious headers (including seed/ancestry) | O | Source path examined CP25H/I; adversarial real-P2P qualification not performed |
| CX-17 | Redownload valid and malicious headers; state isolation | O | Source path examined CP25H/I; dedicated P2P test not performed |
| CX-18 | P2P interrupted sync, peer churn, forks, reorgs, boundary mis-ordering | O | 35-block positive laboratory does not cover negative network dynamics |
| CX-19 | P2P DoS resilience, adversarial \`nBits\`, malformed/oversized messages | O | Network helper inspection alone is not acceptance evidence |
| CX-20 | Wallet receives coinbase rewards; immature vs mature accounting | P | CP25O/T: 34 rewards then block 35 maturity; 700/1000 before spend |
| CX-21 | Restored backup recovers wallet transactions and balances independently | P | CP25P; fresh Node J, 34 transactions, 700 trusted/1000 immature |
| CX-22 | Restored wallet and balances survive clean restart | P | CP25Q and CP25U |
| CX-23 | Signed spend of restored mature coinbase; mempool acceptance | P | CP25S; 1 TAOX transfer, explicit 2 sat/vB fee |
| CX-24 | Payment confirmed in a mined RandomX block; both wallets reconcile | P | CP25T; tx \`861240eeb5a636bd899918e27909a5d6ee6deaba67985c2652a39d2700db002a\`; block 35 |
| CX-25 | Mining subsidy plus collected transaction fees accounted | P | CP25T: receiver immature 50.00000450; sender maturity increment +50 |
| CX-26 | Confirmed payment and both wallets persist through restart | P | CP25U; sender 748.99999550 trusted / 950 immature, receiver 1 trusted / 50.00000450 immature |
| CX-27 | Legacy wallets/keys/addresses/change and unsupported-script safety | O | Three uncommitted wallet files require detailed review and independent compatibility fixtures |
| CX-28 | Wallet reorg, orphan coinbase, double spend, fee/change and rescan tests | O | One confirmed payment does not qualify reversals and edge cases |
| CX-29 | Production historical consensus, UTXO/balance and wallet parity | O | Legacy RPC crash previously identified; historical full-chain, independent ledger equivalence not signed off |
| CX-30 | Multi-node propagation of *newly mined* RandomX blocks | O | CP25J synced previously mined blocks; CP25T block 35 was mined on isolated Node J |
| CX-31 | Restart/recovery following interrupted import/network/database writes | O | Clean restart qualified; crash/power-loss/recovery not yet qualified |
| CX-32 | Sustained 24–48h multi-node operation and memory/CPU/resource monitoring | O | Stability gate outstanding |
| CX-33 | Clean reproducible release build, test-suite and supply-chain audit | O | Existing development builds are not clean release binaries |
| CX-34 | Wallet install/upgrade/uninstall/rollback, installer and documentation | O | Packaging, documented rollback and user recovery gates outstanding |
| CX-35 | Release evidence review, independent sign-off, activation/cutover plan | O | No first release or mainnet activation approved |

**Important interpretive boundaries:** wallet balances in these rows are experimental TAOX regtest values, not public balances; isolated source-node reindex, seeded RandomX mining and P2P network sync are distinct tests; \`-loadblock\` out-of-order ingestion did **not** establish recovery, while \`-reindex\` did. Existing positive P2P sync does not establish new-block relay. Some earlier legacy historical tests involved a separate mainnet-only laboratory: reconcile the exact commits and binary identities before merging evidence registers.


Other coins must start as unqualified under this specific migration checklist until their own evidence exists. Use [per-coin records](../coins/README.md).
