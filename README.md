This migration plan is well structured overall. I would make two recommendations before applying it.

1. Keep the original identifier if it has governance significance

If 6185:85:ad:AD is intended as a canonical identifier within your governance model, don’t rely on the filename alone to preserve it. Instead:

* Rename the file to a portable filename:

docs/specifications/6185-85-ad-AD.md

* Preserve the original identifier inside the document:

id: "6185:85:ad:AD"
filename: "6185-85-ad-AD.md"
version: "1.0.0"
status: draft
classification: CAL:9

This keeps the symbolic identifier intact while avoiding filesystem compatibility issues.

2. Separate specification from implementation

Your proposed repository layout is a good separation of concerns:

Tiger-Lily/
├── docs/
├── schemas/
├── registry/
├── validators/
├── examples/
├── tests/
└── .github/

I would add a registry/ directory if the project will maintain canonical registries, since that aligns with the governance approach you’ve been developing.

README

The README accurately reflects a specification repository rather than an executable project. One sentence I’d consider adjusting is:

Draft specification — no reference implementation.

If there are validators, schemas, or other executable governance components in the future, this could instead become:

Draft governance specification. Reference implementation in progress.

That leaves room for incremental implementation without making the README obsolete.

About the “Sources”

The text ends with a “Sources” heading but doesn’t actually list any sources. If this README is intended to be self-contained, remove that heading. If you want references, include links to relevant standards (for example, SPDX, CycloneDX, SLSA, JSON Schema) or your related repositories.

Overall, this is a solid refactoring plan. It improves portability, clarifies repository identity, and separates governance documentation from future implementation work while preserving the underlying CAL:9 concepts.