# Shared engineering standards

This area defines universal release gates for every coin, miner, wallet, node, and treasury integration. It is independent of any one consensus implementation.

## Optional node privacy for the public

For beginner-friendly Tor, SOCKS5 proxy and VPN setup, per-coin compatibility warnings, and independent leak-testing requirements, see the [public node privacy guide](NODE_PRIVACY_TOR_SOCKS5.md). **No coin has been declared Tor-qualified merely because its source advertises proxy settings.**

## Mandatory SOCKS5 proxy compatibility for future modernisations

Every modernised node release must pass the [proxy compatibility release gate](MANDATORY_PROXY_COMPATIBILITY_RELEASE_GATE.md): a real SOCKS5 P2P connection, independent peer validation, no silent direct-P2P fallback when the proxy is configured, restart/recovery and evidence-linked sign-off. Tor v3 peer/onion functionality is separately qualified before it can be advertised. **These are future release requirements; current clients have not been independently proxy-qualified.**

## Project Independence, Decentralisation and Long-Term Survival

The permanent [long-term independence standard](PROJECT_INDEPENDENCE_DECENTRALISATION_LONG_TERM_SURVIVAL.md) sets a 16-point per-coin checklist for reproducible builds, permissionless nodes, monetary integrity, infrastructure independence, successor maintainers and founder-absence testing. It is a **new engineering obligation, not a claim that any coin has already qualified**.

## Independent software development and release ownership

Adopted 2026-11-25: after each qualified transition, maintain independent project code, versioning and releases, with selective upstream security backports rather than routine Bitcoin Core rebases. See [GS-LS-001, section 6](PROJECT_INDEPENDENCE_DECENTRALISATION_LONG_TERM_SURVIVAL.md#6-independent-software-evolution-and-release-ownership). Existing release gates, chain continuity and transition scope remain unchanged.

## Deferred source identity and architectural independence — Transition Release 2

Adopted 2026-11-26: complete the first transition releases of all five cryptocurrencies before implementing systematic internal source rebranding. See [GS-LS-001, section 7](PROJECT_INDEPENDENCE_DECENTRALISATION_LONG_TERM_SURVIVAL.md#7-source-identity-and-architectural-independence--transition-release-2) for the four-phase roadmap, migration scope, compatibility safeguards and per-coin qualification requirements. This is a deferred roadmap, not authorisation to rename current Transition Release 1 sources. Preserve upstream attribution and all existing release gates.

## Mandatory website deployment and recovery

Adopted 2026-11-27: [GS-WEB-001 — Website deployment and recovery](WEBSITE_DEPLOYMENT_RECOVERY.md) establishes W01–W12 for all project websites and applicable production integrations. **No verified backup — no deployment. No verified rollback procedure — no deployment.** Preserve the actual hosted baseline outside the public root and in an independent recovery copy; never rely on hosting trash or confuse development source with hosting-ready artifacts. Existing release gates remain in force.

## Autonomous infrastructure recovery and read-only explorers

Added 2026-11-24 following the EZHScan five-chain deployment. Apply these requirements to node-dependent services (explorers, miners, treasury workers and other scheduled integrations) without changing consensus:

- Inventory persistent services, timers and dependencies. Verify boot enablement and runtime state separately; socket activation and timer-triggered oneshot services need not themselves be enabled.
- Boot ordering is not readiness. Handle temporarily unavailable nodes, renewed authentication credentials, lost encrypted links and downstream service outages with bounded retry/backoff; preserve explicit operator pauses. Classify integrity failures separately and quarantine conflicts rather than weakening checks.
- Use least-privilege service identities and private authenticated transport. A client RPC allowlist is not equivalent to daemon-side authorization. Keep secrets outside the webroot and repository; immediately rotate exposed credentials and verify rejection of old credentials.
- Resume from the last committed, verified chain anchor. Never automatically rewind or accept divergent history to recover availability. A standby must independently pass genesis, tip and anchor checks; redundant node sources do not by themselves make the indexing worker redundant.
- Public read-only services must distinguish indexed data from the live chain, flag stale/incomplete coverage and never label partial address accounting or net issuance as verified balances or circulating supply. A functioning API is not evidence of independent consensus validation.
- Preserve rollback and protected staging. Require actual controlled restart/reboot, outage recovery, continuity verification and 24–48h monitored stability before full operational sign-off. Boot configuration alone is not recovery qualification.

**EZHScan evidence scope:** initial ingestion from all five networks, public PHP endpoints and persistent startup configuration were operator-reported (P). Actual reboot/outage recovery, sustained stability, complete historical accounting, security closure and standby failover remain open (O). No cryptocurrency release or modernisation gate is satisfied by explorer deployment.

## Project identity and transparency

See the [project identity and transparency standard](PROJECT_IDENTITY_TRANSPARENCY.md) for canonical blockchain identifiers, public no-coin-sales disclosures and AI research accuracy regression checks. Source-declared identifiers must be distinguished from live-node verification.

## Common graphical wallet splash standard

Adopted 2026-11-25 for Denzuve (DZUV), Aurzola (AUZV), Sestovi (SEZQ), Asveru (ASVR) and Duprezo (DPZE). Use the [existing XNUVA splash renderer](https://github.com/Xnuva-Blockchain-Project/Xnuva/blob/ea8c780bd4d8423a6e415c69df260a76f760c8b0/src/qt/splashscreen.cpp) as the visual and behavioural reference: 960 × 540 logical canvas (16:9), coin-specific artwork and identity, consistent XNUVA Blockchain Project attribution, dynamic binary version and network label, and readable live startup/progress messages in a bottom-left status panel. Preserve startup cancellation and shutdown behaviour. Keep artwork source and provenance with the project; avoid stale hard-coded versions, misleading network labels and inherited third-party coin artwork.

Use logical coordinates consistently and verify high-DPI scaling, text fit, missing-art fallback, normal and isolated-test network labels, loading progress, cancellation and clean shutdown on each coin's actual candidate. Adapt the reference where required for toolkit compatibility or correctness; copying code or a successful compilation does not establish visual or functional qualification. This is a presentation standard, not permission to modify consensus, migrate wallets or deploy to production. All existing release gates remain in force.

## Modular localisation and branding preservation

Adopted 2026-11-25. Maintain reusable localisation infrastructure in the independent [Localisation repository](https://github.com/Xnuva-Blockchain-Project/Localisation), with common language catalogues, coin-owned presentation identity and coin-specific extensions. Pin reviewed module versions for independent reproducible offline builds. Retain Qt TS/QM compatibility, inherited attribution, contexts, disambiguation, placeholders and language-specific plural forms. Reject conflicting keys and unreviewed translations; use correctly branded English fallback. Never perform blind runtime substitution. Identity metadata is presentation-only and must not control consensus, monetary arithmetic, wallet serialization, network ports or payment URI handling.

Use Princeps (singular) and Principes (plural) for the smallest denomination across the five future branded clients, without altering denomination arithmetic or issuance. Preserve historical identifiers and legitimate upstream attribution. Separate branding commits from functional changes, and retain verified local and remote recovery points.

The Denzuve foundation is experimental: 11 foundation checks reported PASS, 100 inherited catalogues retained, 15 changed GUI keys mapped with 804 old-key matches and zero reported collisions. The generator, migration, schema and catalogue validation, Qt integration and runtime localisation qualification remain open. The standalone repository was populated at [9241b8e8969961217a688b46176518cc9c2470a0](https://github.com/Xnuva-Blockchain-Project/Localisation/commit/9241b8e8969961217a688b46176518cc9c2470a0) (K17H1, 2026-11-25; evidence status P). All 100 inherited catalogue SHA-256 checks passed against committed Git objects, 11/11 standalone foundation checks passed, 113 new files were published, and local and remote commit identifiers matched. Original licences and Denzuve's existing translation pipeline were preserved. Both local working trees were reported clean. This is a preservation baseline, not a qualified localisation module. Do not treat shared-module results as per-coin release qualification.

Complete the rebrand before the final registered regression run; repeat all relevant component and application tests on the exact candidate, including previously passing tests. No release or mainnet activation before all existing gates are satisfied.

## Historical cryptographic identity and inherited regression adaptation

Added 2026-11-25 following Denzuve K19A–K19C. Mandatory for each coin's transition; evidence from Denzuve is not transferable qualification.

- Inventory historical signed-message domains, serialization, address and WIF prefixes, compression flags and wallet formats from preserved legacy source and binaries. Presentation rebranding must not change these protocol constants. Independently verify message hashes, compact signatures and recovered public keys; test wrong-domain and altered-message rejection and actual legacy executable interoperability. Never infer historical identity from upstream branding.
- Qualify independent reference implementations against established vectors before adapting fixtures. Preserve private scalars, public-key hashes, scripts and compression flags; use only public synthetic keys in published fixtures. Test cryptographic provider availability against known digest vectors without changing global machine configuration.
- Preserve negative parser semantics: a foreign prefix must not mask an intended threshold, whitespace, script-size, nesting or checksum rejection. Preserve valid and deliberately invalid checksum distinctions and independently check script payloads, Merkle roots and control blocks. Review serialization and error selection at runtime.
- Separate supported-network address policy from generic script recognition and consensus activation. Retain inherited vectors and explicitly account for unsupported networks/features; verify native-prefix rejection where appropriate. Do not enable witness, snapshot or other features merely to satisfy upstream tests. Preserve raw cryptographic coverage.
- Derive test fixtures from native subsidy, maturity, difficulty and contextual proof-of-work rules. Preserve production block-creation guards, historical chain ancestry and RandomX seed selection. Never substitute block identifier hashes for contextual proof-of-work hashes, lower chainwork requirements or suppress failures merely to obtain green tests.
- Recover complete failure logs and classify root causes before patching. Preserve exact diffs, dependency pins, original executable hashes and recovery manifests. Separate source preparation from executed regression evidence. Repeat all registered tests and relevant component/adversarial checks on the final exact candidate. Record exclusions and unresolved failures; no release or activation while gates remain open.

Denzuve evidence (P): historical TaoCoin message domain differed from inherited Bitcoin domain; independently reproduced the inherited compact signature, generated a historical-domain vector and verified cross-domain discrimination. The source restoration and fixture corrections remain uncompiled. Historical binary interoperability, runtime parser behavior and all other release gates remain open. Original compiled candidate: 131 PASS / 25 FAIL / 1 SKIPPED of 157 registrations.

## Mandatory release gates

- Preserve genesis, historical blocks, balances, signing formats, and wallet recovery.
- Pin and verify source SHA, build flags, binary SHA-256, chain tip, network parameters and original backups.
- Qualify historical replay, deterministic issuance, independent P2P acceptance, invalid block rejection and wallet spendability.
- Record evidence for miner/staker rewards, maturity, fees, reorgs and any dependent game treasury.
- Prove restart and interrupted recovery, independent node operation, 24–48h monitored stability, clean build and rollback.
- Treat a missing gate or blocked test as a release blocker, including activation planning.
- Require independent evidence for mandatory SOCKS5 proxy compatibility (PX-01–PX-22) on the exact modernised release-candidate binary.

See the [full v1.16 baseline](../GOLDEN_STANDARD_CRYPTO_MODERNISATION.md) for the exact requirements (especially sections 1–15). Future updates should be maintained in modular documents with clear change history; keep the frozen v1.16 source for provenance.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

