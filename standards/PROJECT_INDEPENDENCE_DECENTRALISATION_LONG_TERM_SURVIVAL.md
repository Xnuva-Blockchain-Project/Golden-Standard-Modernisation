# Project Independence, Decentralisation and Long-Term Survival

**Standard ID:** GS-LS-001  
**Status:** Adopted engineering principle; implementation and per-coin qualification **not yet verified**  
**Adopted:** 23 November 2026  
**Applies to:** TaoX/TAO Revival, Europa (ERA), Zeus (ZUS), Hopium (HOPE), XNUVA, and AMLToken Revival where compatible with its historical-preservation / stasis mandate.

> **A cryptocurrency should be able to outlive its founder, original developers, websites and infrastructure.** Its users should be able to inspect the rules, hold their own keys, independently validate the ledger, and keep the network operating without seeking permission from a central operator.

This is a long-term engineering and stewardship standard, **not** a claim that any current network has already met every requirement. The aim is genuinely permissionless participation, with predictable, public consensus-defined monetary rules. Consensus and governance decisions must not be unilaterally altered by a founder, state authority, exchange, single miner, infrastructure operator or institution. This is a design aspiration and an independently testable responsibility, not a guarantee against regulation, market forces, community-approved upgrades or governance capture.

## 1. Independence covenant

1. **No founder dependency.** The blockchain must not rely on the founder's continued presence, private credentials, hardware, personal funds or willingness to operate infrastructure.
2. **No permission to participate.** Ordinary users should be able to obtain the code, connect, validate, transact and run compatible nodes without an operator-issued whitelist or privileged central service. Any required security controls must be documented and justified.
3. **History and holder continuity.** Preserve each original genesis, legitimate chain, consensus-valid ownership, spendable keys and wallet recovery paths. No invented replacement history or discretionary balance allocations.
4. **Predictable monetary policy.** Publish exact issuance, fees, subsidy, staking, tail-emission or conditional-emission rules, including boundary tests. A founder or organisation must not have an undisclosed or unilateral minting mechanism. Future rule changes require explicit review, coordination and documented network acceptance, not covert inflation or forced chain rewrites.
5. **Publicly reproducible software.** Source, dependencies, build instructions, tests and hashes should allow others to rebuild and verify the binaries independently.
6. **Open maintenance.** Document how unrelated contributors can report vulnerabilities, submit patches, review releases and assume maintenance without possessing the founder's accounts.
7. **Independent operation.** Verify the chain can keep validating and propagating blocks/transactions without project-hosted nodes, seed services, websites, explorers, treasury bridges or centralized DNS.
8. **No false guarantees.** A network can be technically decentralised yet fail through economics, lack of maintainers, concentrated mining/staking, security failures or lack of adoption. Report these risks honestly.

## 2. Mandatory survival qualification checklist

Use **V** (independently reviewed evidence), **P** (checkpoint-reported scoped PASS), **O** (open), **B** (blocked), or **N/A** (justified and signed off). The **initial status for every coin is O unless supported by its own evidence**. Do not treat existence of a public GitHub repository or several project-controlled nodes as proof of decentralisation.

| ID | Requirement / practical test | Minimum qualifying evidence |
|---|---|---|
| LS-01 | Independent source retrieval and reproducible release build | Unaffiliated maintainer clones a pinned tag, builds, hashes and compares binaries/behaviour |
| LS-02 | Independent full node setup and chain validation | New participant obtains public instructions, syncs and matches authenticated tip/consensus without private access |
| LS-03 | Independent peer discovery and P2P operation | Multi-provider nodes discover peers and exchange blocks/transactions without founder-run seed dependence |
| LS-04 | Founder-infrastructure removal exercise | In a safe, isolated environment, disable project-controlled nodes/seeds/services and confirm independent nodes continue |
| LS-05 | No privileged membership or censorship gate | Source audit plus negative tests for whitelists, privileged peers, transaction/relay filtering and bypasses |
| LS-06 | Permissionless wallet and transaction use | Independent wallet can restore keys, receive, sign, broadcast and confirm a payment without operator approval |
| LS-07 | Mining and staking participation | Independent miners/stakers can join where supported, produce valid rewards, and have unrelated peers accept them |
| LS-08 | Monetary schedule and supply integrity | Public consensus vectors for subsidies, PoW/PoS rewards, tail/conditional issuance, supply limits and fees; no unilateral override |
| LS-09 | Distributed control and concentration disclosure | Document and periodically assess miner/staker distribution, reachable node diversity, critical infrastructure and upgrade authority |
| LS-10 | Source, binaries, releases and archival independence | Reproducible builds, published SHA-256 manifests, mirrored source and recoverable chain snapshots with provenance |
| LS-11 | Administrative and key succession | Written contributor/repository/release-key succession process, least privilege, revocation and recovery without publishing secrets |
| LS-12 | Sustainable maintenance and security response | Public contributing guide, vulnerability contact, build/test automation, dependency update policy and maintained issue triage |
| LS-13 | Operator-independent recovery and restart | Unaffiliated node performs cold start, backup restore, reindex and crash-recovery qualification |
| LS-14 | Economic sustainability after ordinary rewards | Tested realistic fee/reward incentives and threat model for declining or stopped subsidies, with PoS where applicable |
| LS-15 | Founder-absence endurance exercise | Monitored long-running independent network continues block validation, transactions and recovery without founding team action |
| LS-16 | Public status and honest uncertainty | Per-coin record shows dated PASS/FAIL/OPEN, exact code/binary/test environment, incidents and outstanding dependencies |

**Critical distinctions:** a small number of project-controlled nodes are *redundancy*, not necessarily decentralisation. Source publication is *inspectability*, not independent reproducibility. A stable test chain is *engineering evidence*, not a demonstrated long-term economic security model.

## 3. Coin-specific considerations

- **TAOX/TAO Revival:** preserve historical Scrypt chain and public legacy network; experimental RandomX may not activate on mainnet merely because regtest passes. Require independent relay, wallet and miners after any expressly authorised transition.
- **ERA:** separately assess any proposed ALCE conditional subsidies for deterministic reproducibility and the risk of inflationary discretion; no proposal alters the live monetary schedule without its own consensus process.
- **ZUS:** include both PoW miners **and** PoS stakers in independence, staking concentration, aggregate issuance and post-subsidy sustainability tests.
- **HOPE:** validate the exact supply and subsidy constraints; no retrospective cap or balance rewrite to satisfy a new policy.
- **XNUVA:** verify whether independently run RandomX nodes and wallets can operate without project infrastructure; internal game treasury is an application dependency and must not become a consensus/ownership authority.
- **AMLToken Revival (in stasis):** first protect authentic historical evidence. Do not manufacture a continuation or infer that previously operated archival nodes are currently available. Any future decentralised revival must independently validate later historical data and avoid reintroducing the documented historic privileged-peer mechanism.

## 4. Public evidence and succession record

Each coin should maintain a dated `long-term-survival.md` checklist linked from its own folder and fill the following fields as independently demonstrated, not from assumptions:

```text
Coin / status / review date:
Source branch + exact commit:
Reproducible build commands and independently measured binary SHA-256:
Published historical genesis/tip and snapshot integrity hash:
Independent node operators and providers (privacy-safe aggregate only):
Unprivileged P2P/transaction/mining or staking test evidence:
Critical founder-owned services and removal-test results:
Consensus supply/issuance policy and activation authority:
Release keys and administrative succession process (no secrets):
Sustainability assumptions / security / fee-and-reward assessment:
Open blockers, mitigations and retest dates:
Independent reviewer / release sign-off:
```

Keep raw credentials, private keys and personal details outside GitHub. Do not publish a map of exploitable infrastructure. Use defensible aggregate evidence where openness would compromise operational security.

## 5. Governance and legacy

This standard is intended to help future maintainers continue the project when its founder is no longer present. Its purpose is not to confer permanent authority on a founder, a foundation, a government, a listing exchange or this handbook.

**The ultimate test is whether ordinary users and independent maintainers can preserve, validate and operate the network themselves.**

**Standing rule:** *No single person should be indispensable to the survival of a genuinely decentralised cryptocurrency.*

**Evidence policy:** This standard adds obligations and tests; it does **not** certify any project or authorise deployment, monetary-policy change, consensus fork, new coin issuance or production cutover. All existing GSH reliability/release gates remain applicable.
