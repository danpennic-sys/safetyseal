# SafetySeal

**Local-first safety inspection, toolbox talk, and incident evidence logger and QuantumGuard sealer for field operators.**

Offline. Deterministic. Pay once. Compatible with QuantumGuard CONTRACT-v1 and the Operator Pages suite.

## Why SafetySeal?

Field operators and contractors face liability when safety incidents, inspections, or toolbox talks are disputed or incomplete. SafetySeal captures the safety event (inspection results, attendance, hazards noted, corrective actions, media hashes) in the field, then seals it into a client- or auditor-verifiable QuantumGuard evidence bundle.

- No SaaS. No subscription. Runs completely offline after key setup.
- Clients, GCs, or auditors verify the pack with the free QuantumGuard verifier (`qg verify` or HTTP).
- Pairs with FieldSeal/JobSeal for job evidence, CloseSeal for close-out, PunchListSeal for deficiencies.
- Exports simple CSVs for records or Chaser import.

## Quick Start

```bash
# Optional but recommended for real Ed25519 signatures
pip install cryptography

python3 src/safetyseal.py --demo
python3 src/safetyseal.py --event samples/inspection-001.json --out sealed.json
```

Verify the output with the QuantumGuard CLI (from the quantumguard repo):

```bash
qg verify sealed.json
```

Expected verdict: PASS (when using real cryptography).

## What you can sell

| SKU       | Price | Includes                                      |
|-----------|-------|-----------------------------------------------|
| Operator  | $79   | CLI + HTML logger + key setup guide + 1-year email support |
| Command   | $199  | + batch mode + templates + reseller rights for client packs |
| Agency    | $499  | + white-label HTML + design partner onboarding |

Purchase / access: danpennic@gmail.com

Source remains free under Apache-2.0 OR MIT. Commercial Operator Pack sold separately.

## Stack Fit

- Python CLI (same family as FieldSeal, JobSeal, etc.)
- Emits QuantumGuard CONTRACT-v1 bundles (Ed25519, deterministic hashing)
- Local key storage (PEM)
- Optional static HTML/JS logger for browser use (see static/)
- Ready for integration with the Operator Pages suite

## License

Apache-2.0 OR MIT
