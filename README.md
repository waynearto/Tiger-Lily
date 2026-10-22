# Performance Governance and Pattern Observation Model

This repository follows a layered governance model that separates policy from execution and makes provenance explicit across requirements, evidence, claims, decisions, and revisions.

## Governance Kernel

The Governance Kernel defines the stable rules and controls that apply across the full lifecycle.

- Identity
- Versioning
- Traceability
- Evidence Policy
- Review Policy
- Change Control
- Audit Policy
- Naming Standards
- Classification

## Performance Governance Lifecycle

The lifecycle defines the workflow used to execute performance work under the governance rules.

```mermaid
flowchart LR
    R["Requirement"] --> PCM["PCM"]
    PCM --> BEP["BEP"]
    BEP --> I["Implementation"]
    I --> E["Execution"]
    E --> PER["PER"]
    PER --> TR["Technical Review"]
    TR --> PCR["PCR"]
    PCR --> ADR["ADR"]
    ADR --> REV["PCM Revision"]