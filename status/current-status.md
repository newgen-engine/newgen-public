# Current Status

Updated 19 November 2026. This update covers the historical NewGen L1 V1 source publication and the private-testnet observations available for inspection.

## Current project structure

NewGen is structured as three distinct but connected ecosystems:

- **NewGen L1**
- **E2 Compute Hub**
- **NewGen AI**

These ecosystems are connected, but they do not share the same role or the same authority.

- **NewGen L1** is the canonical source of truth.
- **E2 Compute Hub** performs bounded commissioned work and does not independently promote local execution state to canonical truth.
- **NewGen AI** provides interaction and bounded orchestration, and is designed to become a future demand layer for the compute ecosystem while remaining constrained by explicit system boundaries and pending final model training.

## V1 publication

The historical NewGen L1 V1 source and selected testnet evidence were published on 18 November 2026. The original project code is available for inspection under the terms in the V1 repository. Requests for coordinated network access go through [Chain Access](https://www.newgenengine.com/chain-access/).

[Inspect the V1 source](https://github.com/newgen-engine/newgen-l1-v1/tree/41f6557c45b87c7d9195b84166d4fed2d10077bd) · [Read the testnet evidence](https://github.com/newgen-engine/newgen-l1-v1/blob/41f6557c45b87c7d9195b84166d4fed2d10077bd/evidence/EVIDENCE_REPORT.md) · [Source inspection terms](https://github.com/newgen-engine/newgen-l1-v1/blob/41f6557c45b87c7d9195b84166d4fed2d10077bd/LICENSE.txt)

## Current public status

### NewGen L1

NewGen L1 is the canonical blockchain layer of the project.

Its role includes:

- canonical state
- finality anchoring and settlement
- governance
- adaptive economic behavior
- reputation logic
- explicit authority over what becomes canonical

### Private-testnet observations

| Observation | Height reported by A, B and C | Finalized height | What the records show |
| --- | ---: | ---: | --- |
| 8 October 2026 | 328,270 | 328,269 | Three original API captures report the same tip and finalized hash. |
| 16 November 2026, after restart | 328,559 | 328,558 | Selected fields from the restart transcript show the same tip and finalized hash on all three nodes in the later observation. |

The [evidence report](https://github.com/newgen-engine/newgen-l1-v1/blob/41f6557c45b87c7d9195b84166d4fed2d10077bd/evidence/EVIDENCE_REPORT.md) documents the capture methods, the October snapshot-export issue on node A and the limits of each observation.

### E2 Compute Hub

E2 Compute Hub is the commissioned compute coordination layer of the project.

Its role includes:

- commissioned workload execution
- bounded off-chain job handling
- controlled worker participation
- reputation-aware worker selection
- L1-based admission boundaries
- explicit separation from canonical chain authority

Private testing described in the [earlier project report](../reports/01-project-status-update.md):

- coordinator/worker flows are built
- controlled job execution tests have already been completed internally
- validation at the time focused on L1-based worker eligibility, admission, receipts and the job lifecycle
- E2 is not yet presented as a public cloud marketplace or full decentralized Hetzner-like product

### NewGen AI

NewGen AI is a proprietary intelligence system being built in-house.

Its role includes:

- conversational interaction
- tool use
- bounded orchestration
- future AI product demand for the compute ecosystem

Private testing described in the [earlier project report](../reports/01-project-status-update.md):

- backend and frontend application layers are operational in private tests
- chat plumbing, session/auth/database paths, and application shell have been tested
- dataset/token preparation and model-building infrastructure are prepared
- the report listed full model training and final answer-quality evaluation as pending
- NewGen AI is not being presented as a finished public AI model yet

## Earlier validation work

The [earlier project report](../reports/01-project-status-update.md) records the validation priorities at that stage. The June notes cover [multi-node operation and the wallet client](../evidence/001-l1-runtime-progress.md) and [Node B recovery from a clean database](../evidence/002-l1-nodeb-clean-db-snapshot-bootstrap.md).

## What is not being claimed yet

This page does not claim:

- that NewGen is a public mainnet
- that public tests are currently open to everyone
- that E2 is already a complete public decentralized cloud marketplace
- that revenue sharing is already live
- that the final NewGen AI model has already been fully trained and evaluated
- that all internal architecture details are public
- that sensitive source code or operational procedures will be published

## Publication posture

Public material is intentionally filtered.

This repository does not publish:

- source code
- private validator/runbook material
- sensitive implementation details
- private endpoints or credentials
- raw logs containing unsafe operational information
- internal deployment procedures

NewGen publishes only material that is useful, accurate, and safe to disclose.
