# 01 — Project Status Update

> **Historical project report.** This report describes the project status documented on 16 May 2026. The historical NewGen L1 V1 source was published separately on 18 November 2026 under proprietary terms for source inspection.
>
> [Current Status](../status/current-status.md) · [V1 source, license and evidence](https://github.com/newgen-engine/newgen-l1-v1/tree/41f6557c45b87c7d9195b84166d4fed2d10077bd)

## What this report is

This report describes what had been built, the regression validation underway and the scope of the project’s public claims in May 2026.

This is a status and positioning document, not a launch announcement.

## Why this update matters

By May 2026, NewGen had moved beyond initial construction. The project was in final regression validation following hardening work across follower access, reputation, policy configuration, E2 admission, and packaging.

## Project scope

NewGen is structured as three explicitly separated but connected ecosystems:

- **NewGen L1** — the canonical blockchain layer
- **E2 Compute Hub** — the commissioned compute coordination layer
- **NewGen AI** — the proprietary AI and intelligence layer

These ecosystems are connected, but they do not share the same role or the same authority.

- **NewGen L1** remains the canonical source of truth.
- **E2 Compute Hub** performs bounded commissioned work and does not promote local execution state to canonical truth on its own.
- **NewGen AI** provides interaction and bounded orchestration, and is designed to become a future demand layer for the compute ecosystem while remaining constrained by explicit system boundaries and pending final model training.

<a name="current-maturity-by-ecosystem"></a>

## Maturity by ecosystem in May 2026

The three ecosystems were at different stages of public readiness.

### NewGen L1

NewGen L1 is not presented as a generic blockchain. It is the canonical foundation of the broader NewGen system.

Its public-facing role includes:

- canonical state
- finality anchoring and settlement
- governance
- adaptive economic behavior
- reputation logic
- explicit authority over what becomes canonical

**Public maturity in May 2026**

- core runtime already built
- repeatedly tested in local/lab/server environments
- multi-thousand-block runs already completed internally
- follower-node access and public-mode behavior under regression validation after hardening
- not presented as a public mainnet yet

### E2 Compute Hub

E2 Compute Hub is not presented as a generic orchestrator. It is the commissioned compute coordination layer of the NewGen ecosystem.

Its public-facing role includes:

- commissioned workload execution
- bounded off-chain job handling
- controlled worker participation
- reputation-aware worker selection
- L1-based admission boundaries
- explicit separation from canonical chain authority

**Public maturity in May 2026**

- coordinator and worker flows had been built
- controlled job execution tests had been completed internally
- validation focused on canonical L1-based worker eligibility, admission, receipts, and job lifecycle behavior
- E2 is not yet presented as a complete public decentralized cloud marketplace.

### NewGen AI

NewGen AI is not presented as a thin assistant layer. It is a proprietary intelligence system being built in-house.

Its public-facing role includes:

- conversational interaction
- tool use
- bounded orchestration
- future AI product demand for the compute ecosystem

Its internal stack already includes foundational proprietary components such as:

- tokenizer program
- run engine
- controlled data/token pipeline
- backend/frontend application layer
- chat plumbing and application shell

**Public maturity in May 2026**

- backend and frontend application layers were operational in private tests
- chat, session, authentication, database, and application shell flows had been tested
- dataset and token preparation and model-building infrastructure were in place
- full model training and final answer-quality evaluation were pending
- NewGen AI is not being presented as a finished public AI model yet

<a name="current-validation-phase"></a>

## Validation phase in May 2026

The project was validating the following areas after the hardening work.

- follower node package and public-mode boot behavior
- L1 peer stability and local reputation behavior
- L1 → E2 canonical worker eligibility
- E2 worker admission and job lifecycle
- AI application shell, backend/frontend flow, and verified fail-closed behavior
- public documentation alignment

The purpose was to check for regressions in the systems already built.

## Communication posture

In May 2026, the project was aligning public updates with documented maturity, scope, and availability.

NewGen public material should distinguish clearly between:

- systems already built and tested internally
- systems currently being regression-tested
- roadmap directions
- features not yet publicly available

## What this report does not claim

This report does not claim:

- that NewGen is a public mainnet
- that public tests are currently open to everyone
- that all three ecosystems are at the same public-readiness stage
- that E2 is already a complete public decentralized cloud marketplace
- that revenue sharing is already live
- that the final NewGen AI model has already been fully trained and evaluated
- that all internal architecture details are public
- that sensitive source code or operational procedures will be published
- that this report exhaustively describes the full internal scope of the project

## Publication note

The May 2026 publication policy kept the following material out of the public documentation repository.

- source code
- private validator/runbook material
- sensitive implementation details
- private endpoints or credentials
- raw logs containing unsafe operational information
- internal deployment procedures

The historical L1 V1 source was published in a separate repository on 18 November 2026 under proprietary terms for technical inspection. [Source inspection terms](https://github.com/newgen-engine/newgen-l1-v1/blob/41f6557c45b87c7d9195b84166d4fed2d10077bd/LICENSE.txt)
