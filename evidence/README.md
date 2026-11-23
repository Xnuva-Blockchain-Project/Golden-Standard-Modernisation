# Evidence, checksums and audit templates

Each coin should store a **sanitised** evidence manifest, one entry per test and checkpoint, under its own folder. Preserve raw logs, wallet backups and credentials offline; never upload them to this public repository.

## Evidence entry template

~~~text
Coin / test ID / checkpoint:
Date (UTC) / operator / independent reviewer:
Outcome: V | P | O | B | N/A
Repository / branch / exact commit SHA:
Executable SHA-256 / module SHA-256 / toolchain:
Network / datadir label / isolation controls:
Pre-test block height / tip / seed / nBits:
Expected / actual observations:
Block hash / transaction ID / peer observations:
Input fixture SHA-256 and output log SHA-256:
Relevant source paths / test script revision:
Backup snapshot hash / recovery evidence (no secrets):
Defect reference / remediation commit / regression test:
Post-test height / tip / side effects:
Independent verification and sign-off:
Remaining dependencies / next test:
~~~

## Checksum convention

Use SHA-256 for binary, test fixture and log integrity, with human-readable filenames and a dated manifest. A Git commit SHA identifies source history and should **not** be presented as a SHA-256 binary verification. The chain block hash and txid are consensus identifiers, not substitutes for file checksums. Never publish wallets, passwords, cookies, raw RPC credentials or personally identifying infrastructure details. Mark absent hashes **NOT RECORDED** rather than inventing them.

**Status notation:** P = checkpoint-reported scoped PASS (review of underlying artefacts outstanding), V = independently verified and reviewed, O = open/not qualified, B = blocked/failed, N/A = independently justified and approved. Do not mark a test V solely from a conversation or copied log. Never transplant a pass from one coin to another.

