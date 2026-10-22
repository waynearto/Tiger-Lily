I’ve formatted your content as a clean, GitHub-ready README.md.
Tiger-Lily
The public home of the David.Orwell project and the primary entry point into the 6185 ecosystem.
Tiger-Lily is the public-facing repository for the David.Orwell project within the 6185 ecosystem.
It provides documentation, architectural guidance, onboarding resources, release information, examples, and community materials. The implementation, orchestration, and runtime components are maintained in the David.Orwell repository.
 
⸻
 
Purpose
Tiger-Lily provides a stable, discoverable starting point for developers, researchers, contributors, and users.
Its responsibilities include:
	•	Project documentation
	•	Architecture guides
	•	Installation and onboarding
	•	Release information
	•	Public examples
	•	Reference material
	•	Contributor guidance
	•	Community resources
	•	Navigation to related repositories
By separating documentation from implementation, the public interface remains stable while the underlying software continues to evolve.
 
⸻
 
Architecture
The 6185 ecosystem is organised as a layered architecture with clear separation of concerns.
                          6185
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
    datasets         MoDuSRegister          shared
                                                │
                                         CompanionCore
                                                │
                                         Companion (iOS)
                                                │
                                         David.Orwell
                                                │
                                           Tiger-Lily
                                      Public Documentation
Dependency Direction
CompanionCore
      ▲
      │
Companion Applications
      ▲
      │
David.Orwell
      ▲
      │
Tiger-Lily
Architectural Principles
	•	Documentation depends on published interfaces.
	•	Applications depend on shared libraries.
	•	Shared libraries do not depend on applications.
	•	Governance remains independent of implementation.
	•	Dependencies flow toward shared foundations.
	•	Documentation remains independent of runtime implementation.
 
⸻
 
Repository Roles
Repository	Responsibility
Tiger-Lily	Public documentation, onboarding, releases, examples, and project identity
David.Orwell	AI orchestration, agent runtime, automation, implementation, and development planning
Companion	Client applications
CompanionCore	Shared Swift package providing reusable models, networking, validation, and domain logic
6185	Governance, specifications, architecture, standards, and project coordination
datasets	Versioned datasets and reference material
MoDuSRegister	Register management, validation, and supporting tooling
shared	Cross-project packages and reusable libraries
 
⸻
 
Workspace Layout
~/Developer/waynearto/
├── 6185/
├── Companion/
├── David.Orwell/
├── Tiger-Lily/
├── datasets/
├── MoDuSRegister/
├── shared/
└── .github/
 
⸻
 
Design Principles
	•	Documentation and implementation remain independent.
	•	Public interfaces should remain stable.
	•	Shared functionality belongs in reusable packages.
	•	Dependencies flow in one direction.
	•	Governance and specifications remain independent of implementation.
	•	Components should be modular, testable, maintainable, and reusable.
	•	Documentation should describe behaviour rather than duplicate source code.
 
⸻
 
Getting Started
Clone the repository:
git clone https://github.com/waynearto/Tiger-Lily.git
cd Tiger-Lily
Explore the documentation, architecture guides, and examples.
For implementation details, development workflows, and runtime components, refer to the David.Orwell repository.
 
⸻
 
Vision
Tiger-Lily serves as the public gateway to the 6185 ecosystem by bringing together documentation, architectural guidance, release information, onboarding resources, and community materials into a single location.
Its goal is to provide a clear entry point for developers, researchers, contributors, and users while allowing the implementation repositories to evolve independently.
As the ecosystem grows, Tiger-Lily will remain the canonical starting point for understanding the overall architecture, repository relationships, governance model, and contribution workflow.
 
⸻
 
Related Repositories
	•	David.Orwell — AI orchestration and implementation
	•	Companion — Client applications
	•	shared — Shared packages, including CompanionCore
	•	6185 — Governance, specifications, and architectural standards
	•	MoDuSRegister — Register management, validation, and supporting tooling
	•	datasets — Versioned datasets and reference material
 
⸻
 
License
This repository will include an open-source license before public release (for example, MIT, Apache-2.0, or another appropriate license).
 
⸻
 
Tiger-Lily is the public home of the David.Orwell project and the primary entry point into the 6185 ecosystem.
This version follows standard GitHub README conventions and is ready to save as README.md in the root of the Tiger-Lily repository.
