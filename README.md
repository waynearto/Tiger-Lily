# Architecture Guide

This guide explains how the 6185 ecosystem is structured and how repositories should evolve.

## Objectives

The architecture is intended to:

- keep responsibilities explicit
- reduce coupling
- support future applications
- preserve reusable logic
- maintain a clear governance layer

## Design Principles

### 1. One-way dependencies
Application and orchestration code should depend on shared logic, not the reverse.

### 2. Separation of concerns
User experience, orchestration, and domain logic must remain distinct.

### 3. Documentation-first
Architecture should be explained in docs before being implemented as code.

### 4. Shared logic is reusable
If logic may be used by multiple systems, it belongs in a shared layer.

### 5. Clear ownership
Every component should be traceable to a repository or domain owner.

## Repository Alignment

- `6185`: governance and standards
- `David.Orwell`: orchestration and automation
- `MoDuSRegister`: registry logic
- `datasets`: support data and reference content
- `shared`: reusable technical logic
- `Companion`: app layer

## Recommended Decision Process

When planning new work:

1. Determine whether it is ecosystem-wide, shared, domain-specific, or app-specific.
2. Place it in the corresponding repository.
3. Check whether the work violates existing boundaries.
4. Update documentation if responsibilities or architecture change.

## Summary

The architecture should remain modular, explainable, and reusable.

---

6) docs/onboarding/getting-started.md

```md
# Getting Started

This guide explains how to begin contributing to the David.Orwell repository and the wider ecosystem.

## Repository Map

- `6185`: architecture and governance
- `David.Orwell`: orchestration and automation
- `MoDuSRegister`: register logic
- `datasets`: canonical data and examples
- `Companion`: user-facing app
- `shared`: reusable technical logic

## Before You Start

Ask:
- Is this architecture work?
- Is this shared logic?
- Is this app-specific?
- Is this automation or orchestration?
- Is this data or domain logic?

## Recommended Reading Order

1. `README.md`
2. `docs/architecture/ecosystem-overview.md`
3. `docs/architecture/repository-boundaries.md`
4. `docs/architecture/dependency-flow.md`
5. `docs/architecture/architecture-guide.md`

## Contribution Guidance

- keep concerns separated
- avoid mixing orchestration with product UI
- prefer shared abstractions over duplication
- document architectural or responsibility changes

---

7) docs/standards/coding-standards.md

```md
# Coding Standards

This repository should follow a consistent and transparent coding standard.

## Core Expectations

- Write readable, explicit code
- Prefer clarity over cleverness
- Keep functions focused
- Separate concerns cleanly
- Document non-obvious decisions
- Avoid hidden cross-layer coupling

## Repo-Specific Guidance

### For David.Orwell
- keep orchestration logic explicit
- ensure workflows are observable
- prefer modular automation components
- avoid UI assumptions inside orchestration logic

### For shared code
- keep logic generic and reusable
- avoid product assumptions
- design for multiple consumers

### For app code
- keep product concerns separate from domain logic
- avoid embedding ecosystem governance rules inside UI surfaces

---

8) docs/workflows/development.md

```md
# Development Workflow

This document describes the expected contributor workflow.

## Typical Flow

1. Review the repository purpose and boundaries
2. Identify the correct repository for the work
3. Implement the change in the correct layer
4. Validate behavior and test coverage
5. Update documentation if architecture or responsibilities change
6. Submit for review

## Pull Request Expectations

- clear summary of intent
- minimal scope
- relevant tests
- documentation updates when necessary
- no hidden architectural drift

## Review Expectations

Reviewers should ask:
- Does this belong in this repository?
- Is the architectural boundary correct?
- Is the change adding reusable capability or duplicate logic?
- Has documentation been updated if needed?

---

9) docs/onboarding/repository-map.md

```md
# Repository Map

This map helps contributors understand how the ecosystem is organized.

```text
6185
├── standards
├── governance
├── architecture
├── documentation
└── process

David.Orwell
├── orchestration
├── automation
├── workflow execution
├── agent logic
└── system coordination

MoDuSRegister
├── registry logic
├── domain utilities
├── operational functions

datasets
├── reference data
├── validation examples
├── canonical data sources

shared
├── models
├── networking
├── validation
├── reusable logic

Companion
├── iOS app
├── UI
├── app flows
└── platform-specific logic