# Per-coin engineering records

Each coin has a **dedicated home** for chronology, testing, hashes and outstanding release gates. Cross-coin RandomX implementation details belong under [randomx/](../randomx/README.md); shared policy belongs under [standards/](../standards/README.md).

| Coin | Engineering record | Distinguishing requirements |
|---|---|---|
| TAOX / TAO Revival | [TAOX](TAOX/README.md) | Historic Scrypt chain, experimental gated RandomX |
| Europa (ERA) | [ERA](ERA/README.md) | Preserve historical monetary schedule; ALCE is only a proposal |
| Zeus (ZUS) | [ZUS](ZUS/README.md) | Both Proof of Work **and** Proof of Stake; aggregate reward accounting |
| Hopium (HOPE) | [HOPE](HOPE/README.md) | Prospective capped-supply safeguards, no retrospective changes |
| XNUVA | [XNUVA](XNUVA/README.md) | Existing RandomX and wallet/game-treasury dependencies |
| AMLToken Revival (ABTC precursor) | [AMLToken Revival](AMLToken-Revival/README.md) · [test register](AMLToken-Revival/tests.md) | **STASIS**: historical SHA256d chain recovery; NOT a current RandomX migration |

**Required entries for every coin:** history, source/binary hashes, chronological checkpoint references, completed tests, outstanding tests, release blockers, recovery/rollback and reviewer sign-off. Use [evidence templates](../evidence/README.md) and the [shared checklist](../randomx/checklist.md).

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

