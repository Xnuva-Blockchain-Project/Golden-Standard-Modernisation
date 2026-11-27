# GS-WEB-001 — Website deployment and recovery standard

**Adopted: 27 November 2026. Mandatory.**

**Reliability first. Release second. Recovery always.**

## 1. Scope and authority

Applies to all XNUVA Blockchain Project websites, including EuropaZeus.org, EZHScan.com, Bull-v-Bear.com and ExchangeTrade.com, and future web applications. The backup, provenance and rollback principles also apply to databases, nodes, miners, wallets, treasury services and other production integrations. Existing component-specific qualification and release gates remain mandatory. This standard does not authorise any production deployment, consensus change or service restart.

**No verified backup — no deployment. No verified rollback procedure — no deployment.**

## 2. Mandatory checkpoints W01–W12

| ID | Requirement | Required evidence |
|---|---|---|
| W01 | Identify actual production file and directory, active entry point, dependencies and environment. | Document root, active filename, deployment layout, relevant runtime version and existing access restrictions; redact private details in public records. |
| W02 | Before replacement, preserve the exact hosted working file outside the public document root. | Timestamped recovery copy, SHA-256 comparison with original, permissions and ownership recorded. Back up all affected files and configuration; where data/schema changes are involved, take an appropriate consistent database backup. |
| W03 | Preserve a separate independent local or protected off-host recovery copy. | Verify checksum, readability, access and recovery procedure. Do not rely solely on the same hosting account, provider snapshots or the cPanel trash bin. Keep sensitive material private. |
| W04 | Identify the correct source branch, commit and hosting-ready artifact. | Source and artifact identifiers, packaging steps and hashes; distinguish development source from deployed files. |
| W05 | Compare proposed changes against the actual working production baseline. | Reviewed diff; cosmetic/navigation changes must not modify backend logic, dependencies, database identifiers or service configuration. Stop on unexpected differences. |
| W06 | Validate syntax, dependency paths, runtime and configuration compatibility. | Relevant PHP lint or equivalent, package checks and compatibility evidence. Preserve private bootstrap, least privilege and staging authentication. |
| W07 | Test in protected staging or equivalent isolated hosting-compatible environment before deployment wherever possible. | Functional results against exact candidate; if staging is unavailable, document the limitation, alternative checks and explicit operator approval before proceeding. No waiver of backup or rollback. |
| W08 | Deploy only the approved files. | Exact manifest, checksums and ownership/mode preservation; use atomic replacement where supported. Do not relax permissions or overwrite unrelated assets, live data or configuration. |
| W09 | Verify actual live functionality, not merely appearance. | HTTP status, expected page and assets, navigation, relevant search/API and data freshness, error logs and unaffected services. Compare before/after. Never infer worker health from page rendering alone. |
| W10 | Restore the previous verified version immediately if deployment verification fails. | Pre-agreed rollback steps, verified recovery source, restored hash and functional checks. If recovery fails, stop further changes, escalate and use a known safe fallback; never disguise stale data as current. |
| W11 | Preserve the verified deployed version in source control and record deployment provenance. | Commit-pinned hosting-ready file or reproducible packaging recipe and deployed checksum, with evidence and rollback reference. Never publish secrets, private configuration, keys, credentials or raw sensitive logs. |
| W12 | Complete appropriate sustained operational observation. | Before/after service and freshness evidence; 24–48 hours for node-dependent and treasury operational qualification under existing standards. Record failures, delayed data and open gates; a cosmetic change does not qualify underlying infrastructure. |

W01–W07 are pre-deployment gates; W10 rollback readiness must also be demonstrated before W08. A failed or missing mandatory gate blocks release or sign-off. Record W07 limitations rather than claiming unexecuted tests passed.

## 3. Incident lesson — EZHScan, 27 November 2026

Operator reported HTTP 500 after replacement of the public PHP homepage. The repository audit identified that the supplied file was from an older staging source rather than the hosting-adapted package. The latter requires a private bootstrap outside the public root and relative public URLs. The operator reported that the previous file was not recoverable from the hosting trash bin. No verified independent copy of the exact pre-change hosted file had been established for that replacement.

Recovery used the preserved deployment branch and original cPanel packaging rules to rebuild the homepage, retaining existing dependencies and explorer functionality. The operator subsequently supplied screenshots showing the page and new navigation/identity labels rendering (P). The HTTP error log was not independently inspected; the deployment-path mismatch is a likely cause, not a confirmed runtime diagnosis. All five network cards showed scanner delay; live ingestion, search/API function and sustained worker operation were not independently qualified by those screenshots (O). No claim of backend recovery or full release qualification is made.

The lessons are mandatory: a trash bin is not a versioned backup; source control is not proof of the exact hosted baseline; capture independent recovery copies before overwriting; separate visual changes from backend changes; verify live functionality and background freshness. Never weaken filesystem permissions to facilitate an upload.

## 4. Checkpoint record

Record date UTC, operator/reviewer, scope, baseline and candidate commit/hash, protected backup references, rollback verification, expected and actual results for W01–W12, deployment time, observation window, defects and final decision. Use the shared GSH P/V/O/B/N/A notation. Keep operational secrets and sensitive recovery locations out of public evidence. Preserve the last known working version independently of the replacement.

**Revision history:** 2026-11-27 — initial adoption following website deployment incident and operator approval.
