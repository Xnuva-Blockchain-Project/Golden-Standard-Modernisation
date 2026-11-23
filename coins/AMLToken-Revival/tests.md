# AMLToken Revival — completed versus outstanding qualification

**Baseline:** project source documents dated 14 September 2026. `H` = historically documented project-controlled PASS (not freshly repeated or independently audited in this GSH), `O` = open or not demonstrated, `D` = deferred while in stasis. Proof-of-work remains SHA256d. A historical three-host replay does **not** constitute unaffiliated third-party reproduction.

| ID | Test or control | Status | Supporting source / limitation |
|---|---|---|---|
| AB-01 | Original v1.3.0 runtime genesis matches recovered binary | H | [Chain identity](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/CHAIN_IDENTITY.md) |
| AB-02 | Original network magic, port, header and SHA256d fingerprint | H | Chain identity; recovered-from-binary evidence |
| AB-03 | Original Windows/Linux artefacts retained and checksummed | H | [Evidence register](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/EVIDENCE_REGISTER.md) |
| AB-04 | Historical Berkeley DB wallet recognised by original client | H | Evidence register; historical-client compatibility only |
| AB-05 | Authentic historical blocks 0–175168 full reindex | H | [Historical recovery](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/HISTORICAL_CHAIN_RECOVERY.md) |
| AB-06 | Consistent height/tip/chainwork on three project-operated hosts | H | [Independent reproduction](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/INDEPENDENT_REPRODUCTION.md); not third-party |
| AB-07 | Historic authorized-peer control mechanism inspected | H | [Network control evidence](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/HISTORICAL_NETWORK_CONTROL_EVIDENCE.md) |
| AB-08 | Two independent-network discovery nodes were serving snapshot | H | [Public discovery node record](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/PUBLIC_DISCOVERY_NODE.md); 2026-09-14 only |
| AB-09 | Authentic block history beyond height 175168 found/validated | O | Current authenticated snapshot may not be final historical tip |
| AB-10 | Exact clean reconstruction source published for independent replay | O | [Reproduction package](https://github.com/Xnuva-Blockchain-Project/AMLToken-Revival/blob/main/docs/INDEPENDENT_REPRODUCTION.md); tracked in issue #3 |
| AB-11 | Historical raw block data durably published for outsiders | O | Same issue #3; do not substitute description for actual data |
| AB-12 | Unaffiliated third party independently reindexed and validated | O | Three project-run hosts are not independent |
| AB-13 | Open/decentralized peer handshake and relay end-to-end | O | Documented architecture/policy not equivalent to final broad interoperability |
| AB-14 | New block mined and independently accepted on a properly gated continuation | D | No replacement production mining |
| AB-15 | Holder wallet balances, reward maturity, normal spending, reorg | D | No demonstrated comprehensive revival-chain wallet release qualification |
| AB-16 | Restart, crash/recovery and sustained 24–48h operation for release candidate | D | Stasis; no new-release test run |
| AB-17 | External audit, packaging, reproducible release, rollback and signoff | D | Release HOLD |
| AB-18 | RandomX migration and new consensus activation | D | **Not part of the present revival or stasis commitment** |

## Integrity and evidence rules

The precise historic file checksums and source identifiers are in [README](README.md); link to original artefact/chain records and never fabricate freshly verified SHA256 outputs. **Hold new qualification while in stasis**. When work resumes, add dated entries instead of rewriting the archived findings. Protect wallet.dat, all private keys and RPC credentials.

**Status: PAUSED — PRESERVE, DO NOT RELEASE.**
