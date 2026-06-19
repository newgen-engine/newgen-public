# NewGen Public

Public documentation, project status, and technical updates for the NewGen ecosystem.

Official website: https://newgenengine.com

This repository does not publish source code.
It exists as the public-facing documentation and reporting layer for the project.

## What NewGen is

NewGen is being developed as three distinct but connected ecosystems:

- **NewGen L1** — the canonical blockchain layer
- **E2 Compute Hub** — the commissioned compute and data-center layer
- **NewGen AI** — the proprietary artificial intelligence layer

These ecosystems are connected, but they do not share the same role or the same authority.

- **NewGen L1** is the canonical source of truth.
- **E2 Compute Hub** performs bounded commissioned work through controlled participation and does not independently promote local execution state to canonical truth.
- **NewGen AI** provides interaction, reasoning, tool use, and bounded orchestration while remaining constrained by explicit system boundaries and reconciling to canonical chain state.

## Ecosystem overview

### NewGen L1

NewGen L1 is the canonical foundation of the project.

Its public-facing role includes:

- canonical state
- finality and settlement
- governance
- adaptive economic behavior
- reputation logic
- explicit public authority over what becomes canonical

### E2 Compute Hub

E2 Compute Hub is the commissioned execution, compute coordination, and distributed compute layer of NewGenEngine.

It is not only a generic workload orchestrator.

Its architecture is designed around:

- commissioned workload execution
- bounded off-chain job handling
- controlled participation and admission rules
- reputation-based worker selection
- execution through the most reliable eligible nodes
- verifiable execution records and runtime evidence
- explicit separation from canonical chain authority

E2 is also the foundation for a broader distributed compute ecosystem where qualified nodes can expose usable compute capacity through explicit capability, policy, reputation, and lifecycle rules.

The long-term direction includes Cloud Units, controlled instance access, GPU-capable workers, verifiable execution paths, runtime evidence, and decentralized compute coordination without removing canonical authority boundaries.

E2 can execute workloads and expose controlled compute surfaces, but NewGen L1 remains the canonical source of truth for finality, reputation, governance, and settlement-critical state.

### NewGen AI

NewGen AI is designed both as a general intelligent assistant and as an ecosystem assistant capable of interacting with blockchain, compute, and workflow systems across NewGenEngine.

Its architecture is designed around explicit authority boundaries between AI, compute, and canonical chain state.

The system is intended to support intelligent interaction, workflow assistance, tool usage, reasoning, and ecosystem coordination without automatically treating every AI output as canonical truth.

When required, important execution paths and ecosystem interactions can be checked, reconciled, and linked to verified state and certified execution flows inside NewGenEngine itself.

The long-term direction includes AI systems capable of operating across NewGen L1, E2 Compute Hub, and distributed compute infrastructure while remaining connected to verifiable execution and canonical state boundaries.

## Current public positioning

NewGen V1 is currently in final regression validation after recent hardening work across follower access, reputation, policy configuration, E2 admission, and packaging.

Current public maturity is not uniform across the three ecosystems:

- **NewGen L1:** core runtime already built and repeatedly tested in local/lab/server environments, including multi-thousand-block runs. Current work focuses on regression validation after final hardening.
- **E2 Compute Hub:** coordinator/worker flows are built and have completed controlled job execution tests. Current work focuses on validating canonical L1-based worker eligibility, admission, receipts, and job lifecycle behavior.
- **NewGen AI:** application/backend/frontend layers are operational in private tests. Dataset/token preparation and model-building infrastructure are prepared; full model training and final answer-quality evaluation remain pending.

## What this repository publishes

This repository is used to publish:

- current public project status
- technical updates
- architecture notes
- filtered public reports
- selected evidence and progress material

## Public evidence

Selected sanitized public evidence notes are published under:

* `evidence/001-l1-runtime-progress.md`
* `evidence/002-l1-nodeb-clean-db-snapshot-bootstrap.md`


## What this repository does not publish

This repository does **not** publish:

- source code
- sensitive implementation details
- internal operational material
- internal audit documentation
- deployment procedures
- internal operating procedures
- any material that would unnecessarily increase operational or security risk

## Publication approach

The material published in this repository is intentionally filtered for public release.

Not all internal components, implementation details, operating procedures, or security mechanisms are appropriate for public publication.
NewGen does not aim to publish everything. It aims to publish what is useful, accurate, and safe to disclose.

## Recommended reading path

Start with:

* `vision/newgenengine-thesis.md`
* `status/current-status.md`
* `reports/01-project-status-update.md`
* `evidence/001-l1-runtime-progress.md`
* `evidence/002-l1-nodeb-clean-db-snapshot-bootstrap.md`


