Here is a shorter, more modern GitHub landing page version for Tiger-Lily, optimized for clarity and quick scanning.

```md
# Tiger-Lily

Tiger-Lily is the public documentation and entry point for the David.Orwell project and the broader 6185 ecosystem.

It provides the project’s public-facing architecture, onboarding, release notes, examples, and contributor guidance. The implementation, runtime, and orchestration logic live in the David.Orwell repository.

## Why Tiger-Lily exists

Tiger-Lily gives the ecosystem a stable public home:
- clear project entry point
- architecture and design context
- contributor onboarding
- documentation and examples
- repository navigation across the wider system

This keeps the public-facing experience clean while the implementation continues to evolve in the underlying repositories.

## Ecosystem overview

```text
                            6185
                              │
         ┌────────────────────┼────────────────────┐
         │                    │                    │
     datasets         MoDuSRegister            shared
                                               │
                                        CompanionCore
                                               │
                                        Companion (iOS)
                                               │
                                        David.Orwell
                                               │
                                          Tiger-Lily
                                    Public Documentation
```

## Repository roles

- `Tiger-Lily` — public documentation, project identity, onboarding, examples
- `David.Orwell` — orchestration, automation, runtime, agent logic
- `Companion` — client applications
- `CompanionCore` — shared Swift package for models, networking, validation, and domain logic
- `6185` — governance, standards, architecture, specification
- `datasets` — public reference datasets and supporting material
- `MoDuSRegister` — register management and domain tooling
- `shared` — reusable cross-project packages and shared libraries

## Design principles

- documentation stays independent from implementation
- shared logic stays reusable and modular
- applications depend on shared foundations
- dependencies flow toward common infrastructure
- architecture stays explicit and understandable

## Getting started

```bash
git clone https://github.com/waynearto/Tiger-Lily.git
cd Tiger-Lily
```

Read the docs, explore the architecture, and use this repository as the public entry point into the 6185 ecosystem.

For implementation and runtime work, refer to:

- [David.Orwell](https://github.com/waynearto/David.Orwell)
- [Companion](https://github.com/waynearto/Companion)
- [6185](https://github.com/waynearto/6185)

## Vision

Tiger-Lily makes the 6185 ecosystem easier to understand by giving people a clear starting point for documentation, architecture, and onboarding — while leaving implementation details to the repositories that own them.

## License

This repository will include an open-source license before public release (for example, MIT or Apache-2.0).

---

If you want, I can also produce:
- a docs-focused README with links into `docs/`
- an SEO-optimized README with a stronger project description
- a more formal, enterprise-style version
- a lightweight, badge-based GitHub landing page version