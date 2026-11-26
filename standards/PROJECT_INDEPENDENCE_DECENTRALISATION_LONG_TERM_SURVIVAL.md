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

## 6. Independent software evolution and release ownership

**Adopted:** 25 November 2026  
**Status:** Standing engineering policy; implementation and qualification remain open.

The modernised upstream foundation is a starting point, not a permanent release roadmap. Following each cryptocurrency's qualified transition release, the XNUVA Blockchain Project will maintain its own software lineage, architecture, roadmap and release cycle rather than routinely replacing or rebasing its codebase onto successive Bitcoin Core releases.

This policy applies to Denzuve (DZUV; TAO Revival), Aurzola (AUZV; Europa), Sestovi (SEZQ; Zeus), Asveru (ASVR; Hopium) and Duprezo (DPZE; XNUVA) as their respective modernisations mature. AMLToken Revival remains subject to its existing stasis mandate.

1. **Own the release lifecycle.** Maintain project-controlled source repositories, review processes, release branches, changelogs, tags and independent version numbering. Adopt a documented major/minor/patch convention appropriate to each coin. Software version numbers do not themselves activate consensus changes. Preserve historical Git ancestry, upstream copyright notices, licences and attribution.
2. **Follow an independent roadmap.** Develop features and architectural improvements according to each network's requirements, not merely because an upstream release introduces them. Prefer small, auditable changes over wholesale source replacement; divergence must have a documented engineering purpose.
3. **Remain security-conscious upstream consumers.** Monitor Bitcoin Core and relevant dependency security advisories, fixes and support lifecycles. Assess applicability promptly, selectively backport or adapt relevant patches, record upstream commit provenance and review interactions with local consensus and wallet behaviour. Document justified non-applicability, deferrals and mitigations. Independence must not mean isolation or abandonment of security maintenance.
4. **Share reusable technology deliberately.** Maintain the XNUVA RandomX Engine as a versioned common module. Extract additional shared components only when their interfaces, compatibility and tests justify it. Pin exact dependency revisions, document source overrides and reconcile them with committed build definitions before release. A shared-module PASS never substitutes for per-coin qualification.
5. **Protect existing networks and holders.** Retain legitimate genesis, historical blocks, balances, signing formats, spendability and existing monetary/consensus rules unless a separately reviewed, expressly authorised forward activation is required. Never reset a chain or force a coin swap merely to introduce new software or branding.
6. **Qualify every independent release.** Apply all existing GSH gates to the exact candidate: clean reproducible build, source and binary provenance, historical validation, applicable adversarial and consensus tests, independent P2P acceptance, wallet restoration and spendability, rewards and treasury integration where applicable, proxy qualification, restart/recovery, monitored stability and rollback. Publish outstanding blockers honestly.

### Transition boundary

Denzuve Transition Release 1 is the initial practical milestone for this direction. Its current modernisation baseline is derived from Bitcoin Core 31.1; the objective is to establish a qualified, independently maintainable foundation first. Do not expand the current transition scope merely to increase divergence. The proposed independent versioning sequence (for example 1.0.0, 1.0.1, 1.1.0, 2.0.0) is illustrative until the actual release version is approved and recorded. No public release, new dependency pin, mainnet activation or production deployment is authorised by this policy.

### Ongoing maintenance evidence

For each independent release, record the project version and tag, source ancestry and exact commit, pinned dependencies and build flags, upstream security review and selected patch provenance, local modifications and compatibility impact, candidate checksums, per-coin GSH test outcomes, unresolved defects, rollback instructions and release sign-off. All implementation and qualification claims remain subject to the existing P/V/O/B/N/A evidence rules.

**Standing rule:** Build on upstream knowledge, maintain our own software, and release only what we can independently verify.

## 7. Source identity and architectural independence — Transition Release 2

**Adopted:** 26 November 2026  
**Status:** Deferred roadmap policy; implementation and qualification open (O).  
**Scope:** Denzuve (DZUV), Aurzola (AUZV), Sestovi (SEZQ), Asveru (ASVR) and Duprezo (DPZE). AMLToken Revival remains in stasis.

### Agreed programme phases

| Phase | Objective | Entry / completion boundary |
|---|---|---|
| 1 — Functional modernisation | Complete Denzuve Transition Release 1, including presentation rebranding, modular RandomX and localisation, and all existing GSH gates. | Current priority; no expansion into wholesale internal renaming. |
| 2 — Five-coin modernisation | Complete and separately qualify Transition Release 1 for the remaining four cryptocurrencies while preserving their existing networks. | All five first transition releases must be completed before Phase 3 implementation begins. |
| 3 — Source identity and architectural independence | Transition Release 2: systematically migrate inherited Bitcoin-specific internal naming and rationalise project-owned architecture, starting with Denzuve as the reference implementation. | Separate authorised development branches, reviewed inventory, migration plan and per-coin qualification. |
| 4 — Independent software evolution | Maintain project-owned architecture, versioning, release cycles and reusable modules; selectively review and port applicable upstream security improvements. | Standing long-term policy under section 6. |

### Transition Release 2 scope and safeguards

- Inventory inherited Bitcoin-named directories, source files, internal namespaces, CMake targets, generated headers, test executables, developer tooling, package metadata and obsolete branding references. Examples include bitcoin_node, bitcoin_wallet, bitcoin_common, test_bitcoin and bitcoin-build-info.h. These are examples to audit, not an unconditional rename list.
- Prefer neutral names for genuinely shared components and coin-specific identities where appropriate. Preserve legitimate technical references to Bitcoin, all upstream Git ancestry, copyright notices, licences, attribution and security-fix provenance.
- Classify every proposed rename as internal-only, external interface, persistent data or protocol-critical. Preserve genesis, chain history, balances, keys, monetary policy, signature domains, address/WIF prefixes, network magic, transaction/block serialisation, wallet database formats and consensus rules. Do not rename persistent data directories, RPC interfaces, configuration keys, service names or payment identifiers without a separately reviewed compatibility and migration plan.
- Separate mechanical renames from behavioural changes; prohibit indiscriminate global replacement. Preserve qualified baselines, exact diffs, dependency pins, backup manifests and rollback instructions. Audit include paths, build graphs, tests, scripts, localisation, packaging and platform integrations.
- Compare pre/post-rename behaviour with fixed cryptographic and consensus vectors, historical replay, wallet migration/recovery, independent peer interoperability, mining/staking and treasury tests where applicable. Run clean reproducible builds, complete regression inventories, proxy and restart/recovery tests, and 24–48-hour monitored stability on each exact release candidate. Explain any exclusions and obtain independent review and explicit release approval.
- Treat the Denzuve implementation as a reusable methodology, not transferable proof of qualification. Record each coin's evidence and sign-off independently.

**Standing scope rule:** Transition Release 1 remains focused on functional reliability and qualification. Internal source-identity migration is deferred until all five modernisations have completed their first transition releases. This roadmap does not authorise any current source edits, production deployment, consensus activation or public release.

**Evidence policy:** This standard adds obligations and tests; it does **not** certify any project or authorise deployment, monetary-policy change, consensus fork, new coin issuance or production cutover. All existing GSH reliability/release gates remain applicable.
