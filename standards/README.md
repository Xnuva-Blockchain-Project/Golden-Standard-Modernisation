# Shared engineering standards

This area defines universal release gates for every coin, miner, wallet, node, and treasury integration. It is independent of any one consensus implementation.

## Optional node privacy for the public

For beginner-friendly Tor, SOCKS5 proxy and VPN setup, per-coin compatibility warnings, and independent leak-testing requirements, see the [public node privacy guide](NODE_PRIVACY_TOR_SOCKS5.md). **No coin has been declared Tor-qualified merely because its source advertises proxy settings.**

## Project Independence, Decentralisation and Long-Term Survival

The permanent [long-term independence standard](PROJECT_INDEPENDENCE_DECENTRALISATION_LONG_TERM_SURVIVAL.md) sets a 16-point per-coin checklist for reproducible builds, permissionless nodes, monetary integrity, infrastructure independence, successor maintainers and founder-absence testing. It is a **new engineering obligation, not a claim that any coin has already qualified**.

## Mandatory release gates

- Preserve genesis, historical blocks, balances, signing formats, and wallet recovery.
- Pin and verify source SHA, build flags, binary SHA-256, chain tip, network parameters and original backups.
- Qualify historical replay, deterministic issuance, independent P2P acceptance, invalid block rejection and wallet spendability.
- Record evidence for miner/staker rewards, maturity, fees, reorgs and any dependent game treasury.
- Prove restart and interrupted recovery, independent node operation, 24–48h monitored stability, clean build and rollback.
- Treat a missing gate or blocked test as a release blocker, including activation planning.

See the [full v1.16 baseline](../GOLDEN_STANDARD_CRYPTO_MODERNISATION.md) for the exact requirements (especially sections 1–15). Future updates should be maintained in modular documents with clear change history; keep the frozen v1.16 source for provenance.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

