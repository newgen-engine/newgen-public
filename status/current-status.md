# Current Status

## What this document is

This page describes the current public status of the NewGen project at a high level.

Its purpose is to clarify what exists today, what is currently being regression-tested, and what is not being claimed yet.

## Current project structure

NewGen is structured as three distinct but connected ecosystems:

- **NewGen L1**
- **E2 Compute Hub**
- **NewGen AI**

These ecosystems are connected, but they do not share the same role or the same authority.

- **NewGen L1** is the canonical source of truth.
- **E2 Compute Hub** performs bounded commissioned work and does not independently promote local execution state to canonical truth.
- **NewGen AI** provides interaction and bounded orchestration, and is designed to become a future demand layer for the compute ecosystem while remaining constrained by explicit system boundaries and pending final model training.

## Current phase

NewGen V1 is currently in **final regression validation** after recent hardening work across:

- follower access and packaging
- public-mode configuration
- peer reputation and rate-limit handling
- canonical worker eligibility
- L1 → E2 admission boundaries
- policy/config consistency
- E2 coordinator/worker validation

The project is no longer in early construction. Current work is focused on confirming that recent hardening changes did not introduce regressions across the already-built systems.

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

Current public maturity:

- core runtime already built
- repeatedly tested in local/lab/server environments
- multi-thousand-block runs already completed internally
- follower-node access and public-mode behavior currently being regression-tested after recent hardening
- not presented as a public mainnet yet

### E2 Compute Hub

E2 Compute Hub is the commissioned compute coordination layer of the project.

Its role includes:

- commissioned workload execution
- bounded off-chain job handling
- controlled worker participation
- reputation-aware worker selection
- L1-based admission boundaries
- explicit separation from canonical chain authority

Current public maturity:

- coordinator/worker flows are built
- controlled job execution tests have already been completed internally
- current validation focuses on canonical L1-based worker eligibility, admission, receipts, and job lifecycle behavior
- E2 is not yet presented as a public cloud marketplace or full decentralized Hetzner-like product

### NewGen AI

NewGen AI is a proprietary intelligence system being built in-house.

Its role includes:

- conversational interaction
- tool use
- bounded orchestration
- future AI product demand for the compute ecosystem

Current public maturity:

- backend and frontend application layers are operational in private tests
- chat plumbing, session/auth/database paths, and application shell have been tested
- dataset/token preparation and model-building infrastructure are prepared
- full model training and final answer-quality evaluation remain pending
- NewGen AI is not being presented as a finished public AI model yet

## Current validation focus

The current validation focus is not feature expansion.

The main areas being validated are:

- follower node package and public-mode boot behavior
- L1 peer stability and local reputation behavior
- L1 → E2 canonical worker eligibility
- E2 worker admission and job lifecycle
- AI application shell, backend/frontend flow, and verified fail-closed behavior

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
