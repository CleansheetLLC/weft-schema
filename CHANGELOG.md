# Changelog

All notable changes to the Weft Schema are recorded here. Weft follows
[Semantic Versioning](https://semver.org/): the schema is **append-only** — node and edge types
carry `since` / `deprecated` markers and are never removed, so a minor version never breaks a
conforming implementation of an earlier one.

Each released version is archived with a version-specific DOI (see [README](README.md)).

## [0.1] — 2026-08 (draft)

Initial public specification and machine projection.

- **Added** `SPEC.md` — the specification: 10 node families, 70 node types, 77 forward edge
  types (with named inverses) plus one monitored escape hatch, 8 design principles, the
  hardware/software/wetware agent trichotomy, setting-extension model, embedding/GraphRAG facet,
  and full standards lineage.
- **Added** `weft.json` — normative machine-readable projection of the full node/edge catalog
  with families, mixins, `dataClass`, `fhirAlignment`, and `standardsAnchor`.
- **Added** publication scaffolding — `LICENSE` (CC BY 4.0), `CITATION.cff`, `.zenodo.json`.
- **Status** draft; published as a defensive publication establishing the five-domain fusion as
  prior art. License (CC BY 4.0) proposed, pending final legal review.

[0.1]: https://weftgraph.org
