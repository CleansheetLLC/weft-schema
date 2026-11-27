# Changelog

All notable changes to the Weft Schema are recorded here. Weft follows
[Semantic Versioning](https://semver.org/): the schema is **append-only** — node and edge types
carry `since` / `deprecated` markers and are never removed, so a minor version never breaks a
conforming implementation of an earlier one.

Each released version is archived with a version-specific DOI (see [How to cite](https://weftgraph.org/#cite)).

## [0.2.1] — 2026-11

Publication correction — **no schema change** (still 10 node families, 70 node types, 85 forward
edge types). `SPEC.md` and `weft.json` remain at 0.2.

- **Corrected** the concept DOI. Versions 0.1 through 0.2 gave `10.5281/zenodo.21806130` as the concept DOI
  "that resolves to the latest version". That is the DOI of the 0.1 record and resolves to 0.1.
  The concept DOI is `10.5281/zenodo.21806129`. The specification, README, citation metadata and
  machine projection now carry it. The archived 0.1, 0.1.1 and 0.2 snapshots keep the old value;
  0.2.1 is the first archived snapshot with the correct one.
- **Added** the 0.2 version DOI, `10.5281/zenodo.24601450`, and a table of version DOIs in the README.

## [0.2] — 2026-11 (draft)

First schema change since publication. **Append-only**: nothing is removed or renamed, so a
conforming 0.1 implementation remains conforming. 10 node families and 70 node types are
unchanged; forward edge types go from 76 to **85**. Every addition carries `since: "0.2"` in
`weft.json`, and every widened edge carries `widened: "0.2"`.

The nine new edges are escape-hatch kinds (`RELATES_TO{kind}`) that recurred across settings
and were promoted under design principle P4. Each names its standards anchor in `weft.json`.

- **Added** `COUNTS` (inverse `COUNTED_BY`) — CountEvent → InventoryLot | StockLocation | Order |
  Encounter. What a count counts. Anchor: FHIR InventoryReport; DEA 21 CFR 1304; AORN counts.
- **Added** `AMENDS` (inverse `AMENDED_BY`) — Document → Entity. A dated addendum beside a locked
  record; the original stays current, so this is distinct from `SUPERSEDES`. Anchor: FHIR
  `DocumentReference.relatesTo` (*appends*); HL7 CDA addendum; W3C PROV `wasRevisionOf`.
- **Added** `FOR_ITEM` (ParLevel → ItemDefinition) and `HELD_AT` (ParLevel → StockLocation) — the
  two ends of a minimum-on-hand level. Anchor: GS1; FHIR InventoryItem / SupplyRequest.
- **Added** `BINDS` (inverse `BOUND_BY`; Association → Tag | DeviceInstance) and `BOUND_TO`
  (Association → Person | Patient | DeviceInstance | Location | Encounter) — the two ends of the
  dated binding record behind `ATTACHED_TO` and `ASSIGNED_TO`. Anchor: FHIR R5 DeviceAssociation.
- **Added** `WITH` — CareRelationship → PractitionerRole | Organization. Anchor: FHIR
  `CareTeam.participant` / `Patient.generalPractitioner`.
- **Added** `IMPLICATES` (inverse `IMPLICATED_IN`) — Alert → Order | Event | Condition. Anchor: FHIR
  `DetectedIssue.implicated`.
- **Added** `SETTLES` (inverse `SETTLED_BY`) — Payment | Remittance → Claim | ClaimLine. Anchor: X12
  835; FHIR PaymentReconciliation.
- **Changed** `LOCATED_AT` gains a `basis` property — `sensed`, `scheduled` or `authored` — and
  accepts Patient → Location. A placement derived from a timetable must never be presented as a
  sensed one. Anchor: FHIR `Encounter.location.status`; ISA-95.
- **Changed** `ABOUT` widened so Consent, CareRelationship, WaitlistEntry, Credential, CountEvent,
  Condition and Communication name their Patient subject with the same edge.
- **Changed** `REGARDING` widened to Communication → Patient | Panel | Condition; `FROM` widened to
  Route → Location; `FULFILLS` widened to InventoryLot → Order (the bottle dispensed against an
  order; FHIR `MedicationDispense.authorizingPrescription`).
- **Changed** publisher and steward to **Cleansheet Inc.** (Cleansheet LLC converted to a Delaware
  C-corp effective 2026-10-23). Versions 0.1 and 0.1.1 remain published under Cleansheet LLC.
- **Corrected** the edge count. The 0.1 text said "77 forward edge types plus one escape hatch";
  the catalog held 77 edge types *including* the escape hatch (76 forward). Counts in 0.2 are
  taken from `weft.json`: 85 forward plus the hatch.
- **Deferred** the split of the overloaded `FOR` edge: no setting has been blocked by it.
- **Status** draft. Published 2026-11-27; version DOI `10.5281/zenodo.24601450`.

## [0.1.1] — 2026-08

Publication refresh — **no schema change** (still 10 node families, 70 node types, 77 edges).

- **Changed** license stated as CC BY 4.0 without the earlier "proposed; pending final legal
  review" qualifier, across the specification, README, and machine projection.
- **Added** the Zenodo concept DOI `10.5281/zenodo.21806130` to the specification, README, and
  citation metadata.
- **Added** canonical home at [weftgraph.org](https://weftgraph.org), served via GitHub Pages.

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
  prior art. Published under CC BY 4.0.

[0.2.1]: https://weftgraph.org
[0.2]: https://weftgraph.org
[0.1.1]: https://weftgraph.org
[0.1]: https://weftgraph.org
