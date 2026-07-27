---
id: RA-001
title: "Building Trust Across the Pharmaceutical Supply Chain"
subtitle: "A Reference Architecture for End-to-End Traceability"
author: "A. S. Tomar"
author_role: "KryoNex Research & Engineering Team"
status: working-draft
document_version: 0.4
publish_date: ""
last_updated: "2026-07-27"
tags:
  - pharmaceutical-traceability
  - supply-chain
  - GS1-EPCIS
  - serialization
  - IoT
  - digital-trust
---
# RA-001 Changelog

All notable research, architecture, evidence, and publication-state changes to
RA-001 are recorded here.

RA-001 follows research-document versioning. A working-draft version does not
indicate production validation or regulatory approval.

---
## Pre-RA-001 Engineering Provenance — November 2024

Engineering and implementation work on pharmaceutical supply-chain
traceability concepts that later informed RA-001 began in November 2024.

This earlier work was undertaken as implementation and engineering activity,
not as a formally versioned A. S. Tomar (KryoNex Research) publication. RA-001 was
subsequently formalized as a research artifact in 2026, incorporating
standards analysis, regulatory research, evidence mapping, architectural
synthesis, and publication-level technical review.

The November 2024 provenance therefore represents the origin of the underlying
engineering investigation and does not constitute an RA-001 publication date,
research-publication version, or prior public release.

## [0.4] — 2026-07-24
> **Technical review updated:** 27 July 2026

### Research

- Established the current-state analysis of pharmaceutical product
  identification, serialization, aggregation, traceability-event exchange,
  enterprise systems, regulatory ecosystems, and environmental observations.
- Separated U.S. DSCSA, European medicines-verification, and Indian
  domestic/export contexts rather than treating them as one global
  traceability model.
- Established claim-level evidence tracking through
  `sources/evidence-register.md`.
- Distinguished standards capability, regulatory requirements, industry
  implementation patterns, peer-reviewed research, and KryoNex Research
  architectural synthesis.
- Reconciled the July 2026 regulatory evidence state against primary,
  standards, official implementation, intergovernmental, and peer-reviewed
  sources.
- Updated the Indian domestic traceability analysis to distinguish the
  22 June 2026 Schedule H2 notification from the applicable commencement
  dates of the expanded provisions.
- DGFT Public Notice No. 44/2024-25-DGFT withdrew Para 2.76 of the Handbook
  of Procedures 2023 with immediate effect. The notice states that
  implementation of the authentication system for exported drug formulations
  shall be undertaken by the Ministry of Health & Family Welfare in line with
  the Drugs Rules, 1945. Earlier DAVA/iVEDA mechanisms should therefore be
  treated as historical implementation context rather than presented as the
  unchanged current DGFT export traceability architecture.
- Reclassified DAVA/iVEDA as historical export implementation context rather
  than representing it as the unchanged current Indian export-regulatory
  architecture.
- Strengthened the European evidence model by separating EU regulatory
  requirements from EMVS operational implementation and distinguishing
  medicines verification from continuous logistics-event traceability.
- Updated organizational-authority analysis to distinguish W3C identity and
  credential standards, OCI industry interoperability mechanisms, and
  regulatory authority.
- Replaced generic counterfeit-goods evidence with pharmaceutical-specific
  OECD/EUIPO research.
- Removed evidence sources that were not required to support substantive
  RA-001 claims rather than retaining citations solely for bibliography
  breadth.

### Architecture

- Established F01 — Contemporary Pharmaceutical Supply Chain as the physical
  reference model.
- Developed F02 — Current Pharmaceutical Traceability Landscape as the
  current-state digital and organizational systems model.
- Developed F03 — Trust & Visibility Boundaries as the conceptual assurance
  model.
- Developed F04 — Logical Assurance Architecture for Cross-Organizational
  Pharmaceutical Traceability as the vendor-neutral synthesis of F01–F03.
- Organized F04 into six logical layers: Physical Pharmaceutical Supply Chain,
  Identification & Observation, Authoritative Operational Systems, Traceability
  Semantics & Exchange, Boundary Assurance Capabilities, and Regulatory &
  Partner Ecosystems.
- Defined Evidence Protection and Trust & Lifecycle Governance as cross-cutting
  architectural concerns.
- Established that event integrity does not establish physical truth,
  credential verification does not itself constitute transaction
  authorization, device identity does not establish calibration, and
  immutability does not establish correctness.
- Treated distributed/shared-ledger mechanisms as conditional candidates to be
  evaluated against governance, privacy, latency, complexity, and the need for
  independently governed shared state.
- Integrated assurance outcomes with existing exception, reconciliation,
  investigation, quarantine, and other applicable operational processes rather
  than assuming that every boundary evaluation produces a successful
  verification outcome.
- Established the principle that an assurance boundary does not itself
  constitute a control failure.
- Defined four distinct assurance dimensions — Product Identity, Event
  Integrity, Organizational Authority, and Observation Correlation — and
  carried them forward from F03 into the F04 logical architecture.
- Preserved authoritative regulatory and enterprise systems rather than
  assuming replacement by a new platform.
- Maintained blockchain and distributed-ledger mechanisms as optional
  architectural candidates rather than foundational requirements.

### Figures

- Added F01 physical supply-chain reference figure.
- Added F02 current traceability landscape figure.
- Added F03 trust and visibility boundaries figure.
- Added F04 logical assurance architecture figure.
- Completed the F01–F04 architecture-figure sequence for the v0.4 working
  draft.
- Retained figure-version review as part of the final publication freeze.

### Editorial

- Adopted vendor-neutral and research-oriented terminology.
- Separated physical-world evidence from digital assertions.
- Removed unsupported universal performance and adoption claims.
- Added explicit limitations and production-validation boundaries.
- Established architectural provenance for KryoNex Research synthesis.
- Completed the v0.4 research-discovery reconciliation for F01–F04 and
  established a research-discovery freeze: additional technologies,
  architectural layers, or general literature are not to be introduced
  unless subsequent verification identifies a material factual,
  regulatory, standards, or architectural issue.
- Standardized the approved F04 name as **Logical Assurance Architecture for
  Cross-Organizational Pharmaceutical Traceability**.
- Preserved the distinction between external facts, KryoNex Research
  synthesis, and proposed architectural mechanisms.

### Publication Status

RA-001 remains **Version 0.4 — Working Draft / Under Technical Review**.

The F01–F04 architecture sequence is complete for the v0.4 working draft:

- F01 establishes the physical pharmaceutical supply-chain model.
- F02 establishes the current traceability and regulatory systems landscape.
- F03 establishes the Trust & Visibility Boundaries model and four assurance
  dimensions.
- F04 synthesizes F01–F03 into the Logical Assurance Architecture for
  Cross-Organizational Pharmaceutical Traceability.

Research discovery for the v0.4 architecture has been frozen following the
July 2026 evidence reconciliation. This freeze does not prevent correction of
a factual error, citation, terminology issue, regulatory development, or other
material issue identified during final verification.

Architecture completion and research-discovery freeze do **not** constitute
publication approval, regulatory validation, production validation, or
implementation certification.

The next milestone:

The publication has completed the v0.4 primary-source and bibliography
verification, regulatory and standards terminology review, claim-to-evidence
consistency verification, F01–F04 cross-figure and narrative consistency
review, public-disclosure and intellectual-property boundary review, final
technical review, and final editorial review.

The remaining controlled-release activities are:

final cross-artifact consistency and release-state verification across the canonical RA-001 research repository and KryoNex website publication representation before the controlled v1.0 publication transition.

No **v1.0**, **Published**, regulatory-approval, or production-validation claim
is made by this release.
