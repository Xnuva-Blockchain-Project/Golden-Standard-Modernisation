# RandomX — shared modular PoW qualification

RandomX is the common *engineering module* to be qualified for the five-coin programme. This section describes its reusable interface tests; actual network consensus is still coin-specific. XNUVA already has RandomX-related operations, which must be reviewed rather than treated as automatically compatible with the new engine.

## Module contract and regression boundaries

1. Pin module repository, commit, supported toolchains, build flags and vendored dependency SHA-256 hashes.
2. Confirm hash determinism, light/full mode parity, memory allocation/failure cleanup, cache/VM lifecycle, thread safety and resource limits.
3. Require contextual block header/seed and epoch selection with no implicit network activation.
4. Test algorithm transition at heights activation-1, activation, activation+1 and seed epochs; validate wrong-seed, wrong-target, overflow and malformed headers.
5. Verify mining nonce exhaustion, job cancellation, chain-tip changes and fallback error handling.
6. Exercise context across `submitblock`, block import, `-reindex`, restart, P2P headers, presync and redownload.
7. Prove real independent peer sync and rejection of malicious headers; instrument DoS and CPU/memory exhaustion paths.
8. Keep every coin's original chainparams, difficulty, coinbase/PoS, money supply and wallet rules independent of the PoW module.
9. Release the module only after its own security review; qualifying the engine does **not** qualify the integrating coin.

See [the canonical 35-item migration checklist](checklist.md) and the [coin records](../coins/README.md). The source for the common code is [Xnuva-RandomX-Engine](https://github.com/Xnuva-Blockchain-Project/Xnuva-RandomX-Engine), subject to separately verified version pinning; this document does not claim the engine repository's present code is fully qualified.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

