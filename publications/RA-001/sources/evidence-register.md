# RA-001 — Technical & Regulatory Evidence Register

**Publication:** Building Trust Across the Pharmaceutical Supply Chain  
**Publication ID:** RA-001  
**Publication Version:** 0.4 (Working Draft)  
**Register Version:** 0.4  
**Status:** Under Technical Review  
**Author:** A. S. Tomar — KryoNex Research & Engineering Team  
**Last Audited:** 24 July 2026  
**Next Scheduled Review:** 24 January 2027

---

## 1. Purpose

This evidence register provides claim-level traceability for material factual,
regulatory, standards-related, and technical statements used in RA-001.

It is maintained separately from the publication so that the readable research
document does not become an evidence-management worksheet.

The register is intended to answer five questions for each material claim:

1. What exactly does RA-001 claim?
2. What type of evidence supports that claim?
3. Which authority or publication supports it?
4. What is the verification status?
5. Is the statement an external fact, a KryoNex Research synthesis, or a
   proposed architectural direction?

This register does not imply that every explanatory sentence in RA-001 requires
an independent citation. Original architectural reasoning and synthesis are
identified separately from externally verifiable claims.

---

## 2. Evidence Classification

RA-001 uses the following evidence hierarchy.

| Evidence Type | Meaning | Typical Sources |
|---|---|---|
| Primary Regulatory | Legislation, regulations, gazette notifications, regulator-issued requirements or official guidance | FDA, European Commission / EUR-Lex, Government of India, CDSCO |
| Primary Standard | Formal technical standards and normative specifications | GS1, W3C, ISO |
| Official Implementation / Industry Guidance | Implementation material produced by recognized standards, industry, or professional organizations | GS1 US, EMVO, OCI, ISPE |
| Intergovernmental Research | Research or operational frameworks published by intergovernmental organizations | OECD/EUIPO, WHO, WCO |
| Peer-Reviewed Research | Research published through peer-reviewed academic or technical journals | IEEE Access and comparable journals |
| KryoNex Research Synthesis | Original systems-engineering interpretation produced by KryoNex Research from multiple evidence sources | RA-001 analysis and figures |
| Proposed Architecture | A design direction introduced for evaluation by RA-001; not presented as current industry practice | F03/F04 architectural mechanisms |

---

## 3. Verification Status

The following statuses are used throughout this register.

**Verified**  
The material claim has been checked against an identified authoritative or
appropriate source.

**Verified with Scope Qualification**  
The source supports the claim, but the wording requires a jurisdictional,
technical, temporal, or implementation qualification.

**Research Synthesis**  
The statement is an analytical conclusion derived from multiple sources rather
than a direct statement from one authority.

**Proposed**  
The statement describes an RA-001 architectural direction and is not a claim
about existing universal industry practice.

**Pending Verification**  
The source or exact wording has not yet been verified sufficiently for final
publication.

No `Pending Verification` claim should be presented as established fact in
RA-001 v1.0.

---

# 4. Evidence Mapping Registry

| Claim ID | RA-001 Claim | Evidence Type | Source / Authority | Location / Scope | Status | Research Note |
|---|---|---|---|---|---|---|
| **CL-01** | Eligible U.S. small dispensers and, where applicable, their trading partners have exemptions from specified DSCSA enhanced drug-distribution-security requirements through **27 November 2026**. | Primary Regulatory | U.S. Food and Drug Administration — *Waivers and Exemptions Beyond the Stabilization Period* | FDA section: “FDA Grants Exemptions to Small Dispensers” | **Verified** | Time-sensitive. Do not generalize this date to all DSCSA trading partners. |
| **CL-02** | GS1 EPCIS 2.0 supports modern data representations/interfaces and includes capabilities for sensor-related visibility information. | Primary Standard | GS1 — *EPCIS Standard* and *Core Business Vocabulary (CBV) 2.0* | EPCIS 2.0 data representation, interface and sensor-element provisions | **Verified** | RA-001 must distinguish standards capability from actual adoption by every pharmaceutical participant. |
| **CL-03** | The European medicines-verification framework is fundamentally an end-to-end authentication model with verification/decommissioning at defined points and additional wholesaler verification obligations in specified circumstances. | Primary Regulatory | European Commission — Commission Delegated Regulation (EU) 2016/161 | Particularly provisions concerning verification by manufacturers, wholesalers and persons authorized or entitled to supply medicinal products to the public | **Verified with Scope Qualification** | Do not describe EMVS as a complete continuous logistics-event tracking system. |
| **CL-04** | Indian domestic pharmaceutical barcode/QR requirements under Schedule H2 were expanded through a June 2026 Drugs Rules amendment affecting specified medicine categories. | Primary Regulatory | Government of India / Ministry of Health and Family Welfare / CDSCO — Schedule H2 amendment, June 2026 | Gazette / Drugs Rules amendment applicable to Schedule H2 | **Verified with Scope Qualification** | Exact product-category wording and effective-date implications must continue to follow the gazette itself. Keep domestic Schedule H2 separate from export DAVA architecture. |
| **CL-05** | India's pharmaceutical export traceability environment includes DAVA-related serialization/reporting processes distinct from domestic Schedule H2 requirements. | Primary Regulatory / Official Implementation | Government of India — pharmaceutical export traceability / DAVA implementation material | Export serialization and DAVA workflows | **Verified with Scope Qualification** | RA-001 intentionally models domestic and export requirements separately. |
| **CL-06** | W3C Verifiable Credentials Data Model 2.0 became a W3C Recommendation on **15 May 2025**. | Primary Standard | W3C — *Verifiable Credentials Data Model v2.0* | W3C publication history | **Verified** | This establishes standards maturity; it does not establish pharmaceutical regulatory acceptance. |
| **CL-07** | Credential-based approaches have been developed for electronic verification of Authorized Trading Partner status in the U.S. DSCSA ecosystem. | Official Implementation / Industry Guidance | Open Credentialing Initiative (OCI) | OCI ATP credentialing architecture and implementation materials | **Verified with Scope Qualification** | OCI is an industry initiative, not the FDA and not a statutory regulatory repository. |
| **CL-08** | Verification Router Service implementations support product-identifier verification workflows within the U.S. pharmaceutical ecosystem, including saleable-return use cases. | Official Implementation / Industry Guidance | GS1 US / industry VRS implementation material | Product Identifier verification and VRS use cases | **Verified with Scope Qualification** | VRS is industry-developed. Do not state that DSCSA itself mandates a particular VRS architecture. |
| **CL-09** | ISPE GAMP 5 provides an established risk-based industry approach for compliant GxP computerized systems. | Official Implementation / Industry Guidance | ISPE — *GAMP 5: A Risk-Based Approach to Compliant GxP Computerized Systems*, Second Edition | Computerized-system lifecycle and risk-based validation guidance | **Verified** | RA-001 must not characterize GAMP 5 itself as a universal legal mandate. |
| **CL-10** | GS1 SSCC identifies logistics units and can support identification of cases, pallets and other logistics units within aggregation/transport workflows. | Primary Standard | GS1 General Specifications / GS1 SSCC materials | SSCC and logistics-unit identification | **Verified** | ISO/IEC 15459 may provide broader unique-identification context, but RA-001 should not imply ISO defines the GS1 SSCC packaging hierarchy. |
| **CL-11** | International trade in counterfeit and pirated goods represents a material global economic problem and can create health and safety risks, including in product categories such as pharmaceuticals. | Intergovernmental Research | OECD/EUIPO — *Trends in Trade in Counterfeit and Pirated Goods*, 2019 | Report findings and product-risk analysis | **Verified with Scope Qualification** | Do not convert general counterfeit-trade estimates into pharmaceutical-only estimates. |
| **CL-12** | Distributed-ledger/blockchain approaches to pharmaceutical drug traceability have been investigated in peer-reviewed research. | Peer-Reviewed Research | A. Musamih et al., “A Blockchain-Based Approach for Drug Traceability in Healthcare Supply Chain,” *IEEE Access*, Vol. 9, pp. 9728–9743, 2021 | DOI: 10.1109/ACCESS.2021.3049920 | **Verified** | Evidence that the architectural pattern has been studied; not evidence that blockchain is required or universally deployed. |
| **CL-13** | Customs administrations use structured risk-management approaches involving risk assessment, profiling and targeting of consignments. | Intergovernmental / Operational Guidance | World Customs Organization — *Customs Risk Management Compendium* | Volume 1 and related risk-management framework | **Verified with Scope Qualification** | Useful contextual evidence for border-risk architecture; not a pharmaceutical track-and-trace standard. |
| **CL-14** | W3C Decentralized Identifiers (DIDs) v1.0 is a W3C Recommendation and provides a standardized decentralized-identifier data model. | Primary Standard | W3C — *Decentralized Identifiers (DIDs) v1.0* | W3C Recommendation | **Verified** | RA-001 treats DIDs as an optional identity mechanism, not a pharmaceutical requirement. |
| **CL-15** | EPCIS event interoperability and regulatory product verification solve related but different problems. | Primary Standard + Primary Regulatory + KryoNex Research Synthesis | GS1 EPCIS/CBV; FDA DSCSA materials; EU Delegated Regulation 2016/161 | Cross-source architectural comparison | **Research Synthesis** | Important RA-001 distinction: event visibility, regulatory verification and physical authenticity must not be collapsed into one concept. |
| **CL-16** | Environmental sensor information becomes more useful for traceability when correlated with product/logistics identity, time, location and custody context. | Primary Standard + KryoNex Research Synthesis | GS1 EPCIS 2.0 sensor capabilities plus RA-001 systems analysis | Sensor and event-correlation model | **Research Synthesis** | Do not claim universal EPCIS-based sensor correlation in current pharmaceutical deployments. |
| **CL-17** | Serialization establishes machine-readable product identity but does not independently establish the complete physical custody history or physical authenticity of a medicine. | Primary Standard + Regulatory Context + KryoNex Research Synthesis | GS1 identification standards; regulatory serialization/verification frameworks | Cross-source architectural analysis | **Research Synthesis** | This is one of RA-001's central trust-model distinctions. |
| **CL-18** | Existing pharmaceutical traceability should be modeled as a federation of independently governed enterprise, partner and regulatory systems rather than as one universal global database. | Multi-source Systems Analysis | GS1; FDA; EU framework; Indian regulatory systems; enterprise architecture analysis | RA-001 Sections 3.3–3.5 | **Research Synthesis** | Architectural abstraction; not attributed to a single external authority. |
| **CL-19** | A digitally valid event or signed assertion does not by itself prove that the corresponding physical medicine is authentic. | Security Principle + KryoNex Research Synthesis | Cross-domain security reasoning applied to pharmaceutical traceability | RA-001 Sections 4 and 7 | **Research Synthesis** | Prevents digital provenance from being misrepresented as a complete anti-counterfeit guarantee. |
| **CL-20** | A trust mechanism should be selected only after the relevant organizational/evidence boundary has been identified. | KryoNex Research Synthesis | RA-001 architectural methodology | Section 5.5 — Evidence Before Technology | **Research Synthesis** | Original RA-001 design principle. |
| **CL-21** | Distributed ledgers are one possible multi-party trust mechanism but are not a prerequisite for pharmaceutical traceability. | Peer-Reviewed Research + KryoNex Research Synthesis | Musamih et al.; existing regulatory/standards architectures; RA-001 trade-off analysis | Sections 5.5–5.6 | **Research Synthesis** | Core vendor-neutrality decision. |
| **CL-22** | RA-001 F04 evaluates conventional PKI, digital signatures, credentials, trusted directories, protected or append-only evidence structures, shared ledgers, and other mechanisms as conditional implementation options according to the assurance boundary rather than mandatory components. | Proposed Architecture | KryoNex Research RA-001 | F04 — Logical Assurance Architecture | **Proposed** | Mechanism inclusion in the evaluation does not imply universal necessity, regulatory endorsement, or production adoption. |
| **CL-23** | Existing operational, trading-partner, and regulatory systems remain authoritative in their respective domains; F04 introduces boundary-assurance capabilities rather than replacing those systems of record. | Proposed Architecture + Regulatory Constraint | KryoNex Research synthesis based on FDA/EU/India system boundaries | F04 — Logical Assurance Architecture | **Proposed** | Foundational integration constraint of RA-001. Boundary assurance must not be interpreted as creation of a new universal pharmaceutical authority or database. |
| **CL-24** | F02 should model current traceability systems before F03 identifies trust boundaries and before F04 proposes additional mechanisms. | Research Methodology | KryoNex Research | RA-001 figure-development sequence | **Proposed / Methodological** | Prevents solution-first architecture and protects the research from blockchain/IoT solutionism. |

---

# 5. Regulatory Boundary Notes

## 5.1 United States

RA-001 must distinguish between:

- statutory DSCSA requirements;
- FDA implementation guidance, exemptions and enforcement policy;
- standards used to exchange traceability information;
- industry-developed verification infrastructure; and
- optional credential or trust architectures.

FDA authority must not be attributed to GS1, OCI, VRS providers, or other
industry organizations.

Likewise, an industry implementation pattern must not be described as a
statutory requirement unless the governing law or regulator establishes that
requirement.

---

## 5.2 European Union

RA-001 must distinguish:

- the Falsified Medicines Directive;
- Delegated Regulation (EU) 2016/161;
- the European medicines-verification repository ecosystem; and
- broader supply-chain visibility/event systems.

The European verification model should not be described as if it records every
physical logistics event associated with a medicinal product.

---

## 5.3 India

RA-001 must keep at least two contexts separate:

### Domestic

Schedule H2 and other applicable domestic Drugs Rules / CDSCO requirements.

### Export

Export-oriented serialization and reporting mechanisms associated with DAVA
and relevant Government of India requirements.

A manufacturing organization can participate in both contexts, but this does
not make the underlying regulatory architectures identical.

---

# 6. Standards Boundary Notes

## GS1 Identification

Provides standardized identifiers and data carriers relevant to products and
logistics units.

Identification alone does not establish complete custody provenance.

## GS1 EPCIS / CBV

Provides a standardized framework for visibility-event information and
business vocabulary.

EPCIS should not be described as a pharmaceutical regulator or a universal
centralized repository.

## W3C Verifiable Credentials / DIDs

Provide general-purpose web standards relevant to machine-verifiable claims and
decentralized identifiers.

Their existence as W3C Recommendations does not imply mandatory pharmaceutical
adoption or regulatory endorsement.

## ISO/IEC 15459

Provides broader automatic-identification / unique-identification standards
context.

GS1 SSCC claims should be sourced principally to GS1 rather than attributing
the GS1 logistics-unit model directly to ISO/IEC 15459.

---

# 7. Architectural Provenance Register

The following RA-001 concepts are **KryoNex Research synthesis**, not claims
that a regulator, standards body, academic paper, or commercial organization
created the RA-001 architecture.

| Architecture Element | Provenance | Status |
|---|---|---|
| Separation of physical flow from digital traceability landscape | KryoNex Research systems analysis | Original synthesis |
| F01 Contemporary Pharmaceutical Supply Chain abstraction | KryoNex Research | Original figure / synthesis |
| Six-concern decomposition: physical movement, identity, events, enterprise records, environmental observations, trust | KryoNex Research | Original synthesis |
| Physical truth vs. digital assertion distinction | KryoNex Research synthesis from security/traceability principles | Original analytical framing |
| Federation-of-systems model | KryoNex Research synthesis | Original architectural framing |
| Trust-boundary-first methodology | KryoNex Research | Original design principle |
| Evidence-before-technology principle | KryoNex Research | Original design principle |
| F02 Current Traceability Landscape | KryoNex Research synthesis from standards, regulatory frameworks, and current-state systems analysis | Developed — under technical review |
| F03 Trust & Visibility Boundaries | KryoNex Research assurance-boundary synthesis | Developed — under technical review |
| F04 Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability | KryoNex Research synthesis derived from F01–F03 | Developed — under technical review |
| Distributed ledger treated as optional rather than foundational | KryoNex Research architecture decision | Active design constraint |

This table establishes provenance of the **architectural synthesis** without
claiming ownership of the standards, regulations, technologies, terminology,
or prior research on which the analysis depends.

---

# 8. Evidence-to-Figure Mapping

## F01 — Contemporary Pharmaceutical Supply Chain

**Purpose:** Establish physical actors and handovers.

Evidence basis:

- pharmaceutical distribution structures;
- serialization and logistics-unit identification practices;
- regulatory trading-partner models; and
- KryoNex Research abstraction.

F01 is not intended to reproduce a single organization's supply chain.

---

## F02 — Current Traceability Landscape

**Purpose:** Map the existing digital systems surrounding F01.

Expected evidence:

- CL-01 — DSCSA;
- CL-02 — EPCIS 2.0;
- CL-03 — EU medicines verification;
- CL-04/CL-05 — Indian domestic/export environments;
- CL-08 — VRS;
- CL-10 — GS1 identification;
- CL-15 — event interoperability vs. verification distinction;
- CL-18 — federation-of-systems synthesis.

F02 must represent **current state**, not the proposed KryoNex architecture.

---

## F03 — Trust & Visibility Boundaries

**Purpose:** Identify where one participant relies on evidence generated,
controlled, transmitted, or interpreted by another participant/system.

Expected evidence/synthesis:

- CL-16 — sensor correlation;
- CL-17 — identity vs. custody/authenticity;
- CL-18 — independently governed systems;
- CL-19 — digital assertion vs. physical truth;
- additional evidence identified during F02 analysis.

F03 must not manufacture a "gap" merely to justify F04.

---

## F04 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability

**Purpose:** Synthesize the physical model (F01), current traceability landscape
(F02), and assurance-boundary analysis (F03) into a vendor-neutral logical
architecture for cross-organizational pharmaceutical traceability.

F04 preserves existing authoritative operational, trading-partner, and
regulatory systems rather than proposing their replacement.

The architecture addresses four assurance dimensions:

- **Product Identity**
- **Event Integrity**
- **Organizational Authority**
- **Observation Correlation**

Its logical structure comprises:

1. Physical Pharmaceutical Supply Chain
2. Identification & Observation
3. Authoritative Operational Systems
4. Traceability Semantics & Exchange
5. Boundary Assurance Capabilities
6. Regulatory & Partner Ecosystems

Cross-cutting considerations include **Evidence Protection** and **Trust &
Lifecycle Governance**.

Expected evidence/synthesis basis:

- CL-02 — EPCIS 2.0 and CBV capabilities;
- CL-06/CL-07/CL-14 — credential and identity standards/patterns;
- CL-12 — distributed-ledger research;
- CL-15 — traceability interoperability vs. regulatory verification;
- CL-16 — observation correlation;
- CL-17 — identity vs. custody/authenticity;
- CL-18 — federation of independently governed systems;
- CL-19 — digital assertion vs. physical truth;
- CL-20 — evidence-before-technology;
- CL-21 — distributed-ledger optionality;
- CL-23 — preservation of regulatory-system authority.

F04 is a **KryoNex Research architectural synthesis** and is not presented as
current universal pharmaceutical-industry architecture.

The architecture does not prescribe distributed-ledger technology as a
mandatory layer. Shared-ledger mechanisms remain conditional candidates where
independently governed shared state is justified after considering governance,
privacy, latency, complexity, and operational requirements.

---

# 9. Claims Requiring Special Editorial Care

The following wording should not appear in RA-001 without strong,
source-specific evidence:

- "Blockchain eliminates counterfeit medicines."
- "Blockchain guarantees authenticity."
- "IoT guarantees cold-chain integrity."
- "All pharmaceutical companies use EPCIS."
- "All EPCIS implementations use EPCIS 2.0."
- "The FDA mandates VRS."
- "The EU tracks every pharmaceutical logistics event through EMVS."
- "DAVA is India's domestic pharmaceutical traceability system."
- "GAMP 5 is legally mandatory."
- "A QR code proves a medicine is genuine."
- "A serialized product cannot be counterfeited."
- "Distributed ledgers are required for end-to-end traceability."
- "One global pharmaceutical traceability architecture exists."

Statements of this type require correction, qualification, or removal during
technical review.

---

# 10. Research Quality Rules

Before a claim is promoted into RA-001 v1.0:

1. Prefer the primary source whenever available.
2. Verify the source actually supports the wording used.
3. Separate regulation from industry implementation.
4. Separate a standard's capability from observed industry adoption.
5. Preserve jurisdiction and effective-date context.
6. Do not convert academic prototypes into claims of production adoption.
7. Do not convert an architectural possibility into an industry requirement.
8. Do not use vendor marketing material as the sole evidence for a general
   industry claim.
9. Record unresolved contradictions rather than silently selecting the most
   convenient source.
10. Change a claim when evidence changes; do not defend an obsolete RA-001
    statement merely because it appeared in an earlier version.

---

# 11. Review Log

| Date | Version | Reviewer | Review Activity |
|---|---|---|---|
| 2026-07-24 | 0.4 | A. S. Tomar — KryoNex Research | Established claim-level evidence registry; separated regulatory, standards, implementation, research, synthesis and proposed-architecture evidence classes; aligned register with RA-001 v0.4 master draft. |

---

# 12. Current Review State

**RA-001 v0.4 remains under technical review.**

At this revision:

- F01 establishes the physical pharmaceutical supply-chain and handover model.
- F02 establishes the current pharmaceutical traceability systems landscape.
- F03 establishes the trust and visibility boundary model and its four assurance questions.
- F04 synthesizes F01–F03 into the Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability.
- F01–F04 are architecturally complete for the v0.4 working draft.
- Existing operational and regulatory systems remain authoritative within the proposed architecture.
- Product Identity, Event Integrity, Organizational Authority, and Observation Correlation remain distinct assurance dimensions.
- Evidence Protection and Trust & Lifecycle Governance are treated as cross-cutting concerns.
- Distributed-ledger technology remains explicitly optional and conditional rather than foundational.
- Current regulatory, standards, implementation, research, and architectural-synthesis evidence has been classified.
- Architectural provenance remains explicitly separated from external standards, regulatory requirements, and prior research.

Architectural completion of F01–F04 does **not** constitute publication approval.

Before RA-001 can progress from the v0.4 working draft toward a publication
candidate, the complete document remains subject to:

- final primary-source verification of regulatory claims;
- citation and bibliography reconciliation;
- standards-version and terminology verification;
- claim-to-evidence consistency review;
- cross-figure and prose consistency review;
- final technical review;
- final editorial review; and
- publication metadata and release validation.

The next milestone is therefore **publication-level technical and evidence
verification of the complete RA-001 artifact**, not development of another
architecture figure.

---

## Research Notice

This register documents the research basis and architectural provenance of
RA-001.

External standards, regulations, publications, organization names, and
technical specifications remain attributable to their respective authors and
organizations.

The selection, classification, comparison, architectural decomposition,
figures, trust-boundary methodology, and systems-engineering synthesis of
RA-001 are developed by KryoNex Research.

**© 2026 KryoNex Research.**
