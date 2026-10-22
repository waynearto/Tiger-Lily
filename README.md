# Tiger-Lily / Resolve Framework

A unified repository README for the Tiger-Lily project and the Resolve framework, including the assembly model and code conventions used to define project assemblies.

---

## Overview

Tiger-Lily is a governance-aware, traceable software architecture framework for defining, assembling, validating, and evolving complex engineering systems. The Resolve Framework formalizes how artifacts, components, patterns, and assemblies are tracked from observation to approval.

The project is designed around a simple principle:

- observe patterns,
- classify them,
- govern the process,
- assemble validated components into coherent systems.

This repository combines:
- the Tiger-Lily platform model,
- the Resolve governance framework,
- a reusable assembly description model,
- and example code for declarations, manifests, and assembly definitions.

---

## Goals

- Provide a clear framework for assembling components into a governed architecture
- Separate observation, classification, validation, and approval
- Preserve traceability across assembly definitions and modules
- Support engineering workflows for AI, infrastructure, software, and hardware projects
- Make repository structure readable and maintainable

---

## Resolve Framework

The Resolve Framework is a layered model for system construction.

### 1. Governance Kernel

The stable rules that govern all work.

- Identity
- Versioning
- Traceability
- Evidence Policy
- Review Policy
- Change Control
- Audit Policy
- Naming Standards
- Classification

### 2. Performance / Engineering Lifecycle

The operational workflow executed under governance.

```text
Requirements
  -> Model / Specification
  -> Assembly Definition
  -> Implementation
  -> Execution
  -> Observation
  -> Review
  -> Decision
  -> Formal Revision
```

### 3. Assembly Model

An assembly is a structured composition of components with explicit metadata, traceability, and validation status.

Each assembly captures:
- identity
- version
- dependencies
- validation state
- owner and review status
- trace links to source artifacts

---

## Repository Model

```text
Tiger-Lily/
├── README.md
├── docs/
│   ├── architecture/
│   ├── governance/
│   ├── assemblies/
│   └── patterns/
├── src/
│   ├── framework/
│   ├── assemblies/
│   ├── validation/
│   └── runtime/
├── examples/
│   └── assemblies/
├── tests/
│   └── assemblies/
└── scripts/
```

---

## Assembly Definition

An assembly is defined as a structured manifest describing the intended composition of a system.

Example YAML assembly manifest:

```yaml
assembly:
  id: tiger-lily.resolve.core
  name: Resolve Core
  version: 1.0.0
  status: draft
  classification: framework
  traceability: active

  components:
    - id: kernel.identity
      type: governance
      role: identity
      required: true

    - id: kernel.versioning
      type: governance
      role: versioning
      required: true

    - id: lifecycle.execution
      type: workflow
      role: operational
      required: true

    - id: assembly.validation
      type: validation
      role: review
      required: true

  dependencies:
    - kernel.identity
    - kernel.versioning
    - lifecycle.execution

  review:
    approved_by: governance.board
    approval_state: pending
    evidence_ref: docs/governance/resolve-core.md
```

---

## Assembly Code Example

Below is a simple example of assembly declaration in code form.

### TypeScript-style example

```ts
type AssemblyStatus = "draft" | "review" | "approved" | "published" | "archived";

interface ComponentRef {
  id: string;
  type: string;
  role: string;
  required: boolean;
}

interface Assembly {
  id: string;
  name: string;
  version: string;
  status: AssemblyStatus;
  classification: string;
  traceability: "active" | "inactive";
  components: ComponentRef[];
  dependencies: string[];
  review?: {
    approved_by?: string;
    approval_state: "pending" | "approved" | "rejected";
    evidence_ref?: string;
  };
}

const resolveCoreAssembly: Assembly = {
  id: "tiger-lily.resolve.core",
  name: "Resolve Core",
  version: "1.0.0",
  status: "draft",
  classification: "framework",
  traceability: "active",
  components: [
    { id: "kernel.identity", type: "governance", role: "identity", required: true },
    { id: "kernel.versioning", type: "governance", role: "versioning", required: true },
    { id: "lifecycle.execution", type: "workflow", role: "operational", required: true },
    { id: "assembly.validation", type: "validation", role: "review", required: true }
  ],
  dependencies: [
    "kernel.identity",
    "kernel.versioning",
    "lifecycle.execution"
  ],
  review: {
    approved_by: "governance.board",
    approval_state: "pending",
    evidence_ref: "docs/governance/resolve-core.md"
  }
};
```

---

## Assembly Metadata Pattern

A practical assembly should include metadata for governance and traceability.

```json
{
  "id": "tiger-lily.resolve.core",
  "name": "Resolve Core",
  "version": "1.0.0",
  "status": "draft",
  "classification": "framework",
  "traceability": "active",
  "dependencies": [
    "kernel.identity",
    "kernel.versioning",
    "lifecycle.execution"
  ],
  "review": {
    "approved_by": "governance.board",
    "approval_state": "pending"
  }
}
```

---

## Governance Rules for Assemblies

All assemblies must obey the following:

1. Every assembly must have a unique identifier.
2. Every assembly must have a version and status.
3. Dependencies must be explicit and traceable.
4. Validation state must be visible.
5. Unapproved or draft assemblies must not be treated as production systems.
6. Superseded assemblies remain in the repository history for auditability.

---

## Assembly Lifecycle

```text
Draft
  -> Review
  -> Approved
  -> Published
  -> Superseded
  -> Archived
```

This lifecycle is applied to assemblies as well as governance documents and controlled artifacts.

---

## Example Project Assembly

```yaml
assembly:
  id: tiger-lily.companion
  name: Tiger-Lily Companion
  version: 0.1.0
  status: draft
  classification: platform
  traceability: active

  components:
    - id: identity.service
      type: service
      role: identity
      required: true

    - id: memory.store
      type: service
      role: memory
      required: true

    - id: audit.logger
      type: service
      role: audit
      required: true

    - id: knowledge.graph
      type: infrastructure
      role: discovery
      required: true

  dependencies:
    - identity.service
    - memory.store
    - audit.logger
    - knowledge.graph

  review:
    approved_by: tiger-lily.team
    approval_state: pending
```

---

## Interpretation

The assembly model moves beyond a mere container or module list. It defines a governed composition structure that includes:

- component identity
- governance relevance
- dependency graph
- traceability
- validation state
- review history

This is what makes Tiger-Lily and the Resolve Framework useful for larger engineering systems and architectural governance.

---

## Core Principles

- Observe first
- Classify second
- Validate before approval
- Maintain traceability
- Keep governance separate from implementation
- Treat assemblies as controlled artifacts

---

## Recommended Use

Use this framework for:

- platform composition
- system assembly design
- governance-aware architecture
- repository-driven engineering workflows
- traceable implementation planning

---

## Summary

Tiger-Lily, together with the Resolve Framework, provides a model for building engineering systems in a controlled, auditable, and traceable way. Assemblies are treated as governed components of a larger architecture rather than de facto project containers.

The result is a framework that supports:
- disciplined engineering,
- clear provenance,
- governance-aware assembly design,
- and maintainable system evolution.

---

## License

This project is intended for open engineering and governance use. Individual components and referenced dependencies remain subject to their own licenses.

---

Built as part of the Tiger-Lily and Resolve ecosystem.