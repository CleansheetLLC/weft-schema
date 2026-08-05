# Weft

**A unified graph schema for healthcare** — clinical, facility, device, people, supply, financial, and AI-provenance in one metagraph.

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21806130.svg)](https://doi.org/10.5281/zenodo.21806130)

| | |
|---|---|
| **Version** | 0.1 (draft) |
| **Date** | 2026-08 |
| **Steward** | Cleansheet LLC |
| **License** | [CC BY 4.0](LICENSE) |
| **Canonical home** | https://weftgraph.org |
| **DOI** | [`10.5281/zenodo.21806130`](https://doi.org/10.5281/zenodo.21806130) — concept DOI, resolves to the latest version |

---

## What Weft is

Weft defines the node types, edge types, and modeling rules for representing everything a
clinician's mental model actually touches — equipment, locations, people, clinical facts,
money, supply, and AI reasoning; across hardware, software, and human (wetware) agents — as a
single typed graph. The *weft* is the cross-thread that binds separate strands into one fabric;
the schema binds five domains normally modeled in isolation into one metagraph.

Weft fuses five domains the literature and industry model **separately** — clinical acts,
people/organization, facility/space, device/sensing, and trust/AI-provenance. Biomedical
knowledge graphs are knowledge-only; EHR graphs are patient-only; building ontologies are
facility-only; CMDBs are IT-only. Every construct traces its lineage to a recognized standard
(FHIR, W3C PROV, SOSA/SSN, Brick, SNOMED CT, ISA-95, GS1 UDI, OCEL, and others). **The
primitives are precedented; the combination is the contribution.**

## Repository contents

| File | What it is |
|---|---|
| [`SPEC.md`](SPEC.md) | The specification — 10 node families, 70 node types, 77 typed edges, 8 design principles, agent trichotomy, setting extension, standards lineage. Narrative source of truth. |
| [`weft.json`](weft.json) | Normative machine-readable projection — full node/edge catalog with families, mixins, `dataClass`, `fhirAlignment`, and `standardsAnchor`. Tooling validates against this. |
| [`CHANGELOG.md`](CHANGELOG.md) | Versioned change history. |
| [`CITATION.cff`](CITATION.cff) | Machine-readable citation metadata (GitHub "Cite this repository"; read by Zenodo). |
| [`LICENSE`](LICENSE) | CC BY 4.0 legal code. |
| [`.zenodo.json`](.zenodo.json) | Deposit metadata for the Zenodo archive. |

## How to cite

> *The Weft Schema, v0.1.* Cleansheet LLC, 2026. https://doi.org/10.5281/zenodo.21806130

Or, citing the canonical home:

> *The Weft Schema, v0.1.* Cleansheet LLC, 2026. https://weftgraph.org

## Status and defensive publication

This specification is published, in part, as a **defensive publication**: a public, dated,
enabling disclosure establishing the five-domain fusion as prior art. The schema itself is not
patentable subject matter; publication establishes the fusion architecture in the public record
and supports open citation and implementation.

The specification and its machine projection are the open layer. The executable pipeline that
extracts, traverses, validates, and scaffolds against this schema — and the corpora, policy
packs, and fixtures that exercise it — are **not** part of this publication.

Weft is versioned append-only: node and edge types carry `since` / `deprecated` markers and are
never removed. Product teams extend Weft by authoring artifacts (policy packs, protocols,
instruments, prompts), not by adding node types.

## License and attribution

Copyright © 2026 Cleansheet LLC. Licensed under
[Creative Commons Attribution 4.0 International](LICENSE). You may share and adapt the material,
including commercially, provided you give
appropriate credit, link to the license, and indicate if changes were made. Attribute as shown
under **How to cite**.

*"Weft" is used by Cleansheet LLC as the name of this schema; trademark rights in the name are
reserved and are not licensed under CC BY 4.0.*
