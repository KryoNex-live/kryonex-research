# RA-001 — Technical & Regulatory Evidence Register

**Publication:** Building Trust Across the Pharmaceutical Supply Chain  
**Publication ID:** RA-001  
**Publication Version:** 0.4 (Working Draft)  
**Register Version:** 1.0  
**Status:** Published  
**Author:** A. S. Tomar — KryoNex Research & Engineering Team  
**Last Audited:** 27 July 2026  
**Next Scheduled Review:** 24 January 2027

---

## 1. Purpose

This evidence register provides claim-level traceability for material factual,
regulatory, standards-related, implementation-related, and technical statements
used in RA-001.

It is maintained separately from the publication so that the readable research
document does not become an evidence-management worksheet.

The register is intended to answer five questions for each material claim:

1. What exactly does RA-001 claim?
2. What type of evidence supports that claim?
3. Which authority, standard, publication, or implementation source supports it?
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
| Primary Regulatory | Legislation, regulations, gazette notifications, regulator-issued requirements, official notices, or official guidance | FDA, European Commission / EUR-Lex, Government of India, CDSCO, DGFT |
| Primary Standard | Formal technical standards and normative specifications | GS1, W3C, ISO |
| Official Implementation / Industry Guidance | Implementation material produced by recognized standards, industry, or professional organizations | GS1 US, EMVO, OCI, ISPE |
| Intergovernmental Research | Research or operational analysis published by intergovernmental organizations | OECD/EUIPO, WHO, WCO |
| Peer-Reviewed Research | Research published through peer-reviewed academic or technical journals | IEEE Access and comparable journals |
| KryoNex Research Synthesis | Original systems-engineering interpretation produced by KryoNex Research from multiple evidence sources | RA-001 analysis and figures |
| Proposed Architecture | A design direction introduced for evaluation by RA-001; not presented as current universal industry practice | F03/F04 architectural mechanisms |

---

## 3. Verification Status

The following statuses are used throughout this register.

### Verified

The material claim has been checked against an identified authoritative or
appropriate source.

### Verified with Scope Qualification

The source supports the claim, but the wording requires a jurisdictional,
technical, temporal, evidentiary, or implementation qualification.

### Research Synthesis

The statement is an analytical conclusion derived from multiple sources rather
than a direct statement from one external authority.

### Proposed

The statement describes an RA-001 architectural direction and is not a claim
about existing universal industry practice.

### Pending Verification

The source or exact wording has not yet been verified sufficiently for final
publication.

No `Pending Verification` claim should be presented as established fact in
RA-001 v1.0.

---

# 4. Evidence Mapping Registry

| Claim ID | RA-001 Claim | Evidence Type | Source / Authority | Location / Scope | Status | Research Note |
|---|---|---|---|---|---|---|
| **CL-01** | Eligible U.S. small dispensers and, where applicable under FDA's exemption framework, certain trading partners have exemptions from specified DSCSA enhanced drug-distribution-security requirements through **27 November 2026**. | Primary Regulatory | U.S. Food and Drug Administration — DSCSA waivers, exemptions, and stabilization-period implementation material | FDA material concerning exemptions for eligible small dispensers and applicable trading partners | **Verified with Scope Qualification** | Time-sensitive. The 27 November 2026 date must not be generalized to every DSCSA trading partner or every DSCSA requirement. |
| **CL-02** | GS1 EPCIS 2.0 and CBV 2.0 provide standardized supply-chain visibility-event semantics and include modern representation/interface capabilities and mechanisms relevant to sensor-related information. | Primary Standard | GS1 — *EPCIS Standard, Release 2.0* and *Core Business Vocabulary (CBV), Release 2.0* | EPCIS event model, representations, interfaces, and sensor-related provisions | **Verified** | Standards capability must remain distinct from claims about universal pharmaceutical-industry deployment or adoption. |
| **CL-03** | The European medicines-verification framework implements an end-to-end medicines-authentication model with pack verification/decommissioning at defined points and additional wholesaler verification obligations in specified circumstances. | Primary Regulatory + Official Implementation | European Commission — Commission Delegated Regulation (EU) 2016/161; European Medicines Verification Organisation — *The European Medicines Verification System Explained*, EMVO-02343, v1.0, 16 June 2023 | Safety-feature verification/decommissioning obligations and EMVS operational architecture | **Verified with Scope Qualification** | EMVS must not be described as a system that records every physical logistics or custody event. Medicines verification and event-oriented traceability are related but distinct functions. |
| **CL-04** | On **22 June 2026**, India's Ministry of Health and Family Welfare notified **G.S.R. 506(E)** expanding Schedule H2 to additional medicine categories, including all vaccines, all antimicrobials, specified narcotic drugs and psychotropic substances, and all anticancer drugs. The notification date must be distinguished from the applicable commencement dates of the expanded provisions. | Primary Regulatory | Government of India / Ministry of Health and Family Welfare / CDSCO — G.S.R. 506(E), 22 June 2026 | Drugs Rules / Schedule H2 amendment | **Verified with Scope Qualification** | RA-001 must distinguish notification from commencement. The Drugs (Seventh Amendment) Rules, 2026 come into force on 1 July 2027, except for the Schedule H2 provision concerning all antimicrobials, which comes into force on 1 July 2028. The expanded provisions must not be described as fully operative merely because the notification was issued in June 2026. Formal statutory category wording should be preserved where material. |
| **CL-05** | India's pharmaceutical-export traceability framework changed materially when **DGFT Public Notice No. 44/2024-25-DGFT, 31 January 2025**, withdrew Para 2.76 of the Handbook of Procedures 2023 concerning the Track and Trace procedure for exports of drug formulations and redirected implementation of authentication for exported drug formulations toward the Ministry of Health & Family Welfare under the Drugs Rules framework. | Primary Regulatory | Government of India — Directorate General of Foreign Trade, Public Notice No. 44/2024-25, 31 January 2025 | Export of drug formulations / withdrawal of HBP Para 2.76 | **Verified with Scope Qualification** | DAVA/iVEDA remains relevant as historical implementation context, but RA-001 must not present the former DGFT/DAVA model as the unchanged current regulatory anchor in July 2026. |
| **CL-06** | W3C Verifiable Credentials Data Model 2.0 became a W3C Recommendation on **15 May 2025**. | Primary Standard | W3C — *Verifiable Credentials Data Model v2.0* | W3C Recommendation / publication history | **Verified** | Standards maturity does not imply pharmaceutical regulatory acceptance, mandatory use, or suitability for every workflow. |
| **CL-07** | Credential-based approaches have been developed for machine-verifiable organizational identity and Authorized Trading Partner status within the U.S. DSCSA ecosystem. | Official Implementation / Industry Guidance | Open Credentialing Initiative — *OCI DSCSA Interoperability Profile v3.4.0* and associated credential/conformance specifications | Enterprise identity, ATP credential, wallet, issuer, and interoperability criteria | **Verified with Scope Qualification** | OCI is an industry initiative rather than FDA or a statutory regulatory repository. Credentials provide machine-verifiable evidence of assertions; they do not independently establish physical product authenticity or automatically establish legal authority outside their governance context. |
| **CL-08** | Verification Router Service implementations support product-identifier verification workflows within the U.S. pharmaceutical ecosystem, including saleable-return and related verification scenarios. | Official Implementation / Industry Guidance | GS1 US VRS / Lightweight Messaging implementation material; OCI VRS interoperability/conformance material where relevant | Product-identifier verification and routed verification workflows | **Verified with Scope Qualification** | VRS is industry-developed infrastructure. RA-001 must not state that DSCSA itself mandates one specific VRS architecture or provider. |
| **CL-09** | ISPE GAMP 5 provides an established risk-based industry approach for GxP computerized-system lifecycle management and validation. | Official Implementation / Industry Guidance | ISPE — *GAMP 5: A Risk-Based Approach to Compliant GxP Computerized Systems*, Second Edition, 2022 | Risk-based computerized-system lifecycle and validation guidance | **Verified** | GAMP 5 should not be characterized as a universal statutory mandate. Applicable regulatory obligations remain authoritative. |
| **CL-10** | GS1 SSCC provides standardized identification of logistics units and can support identification of cases, pallets, and other logistics units within aggregation and transportation workflows. | Primary Standard | GS1 General Specifications and GS1 SSCC materials | Logistics-unit identification | **Verified** | SSCC claims should be sourced principally to GS1. ISO/IEC 15459 may provide broader unique-identification context but should not be presented as defining the GS1 SSCC aggregation hierarchy. |
| **CL-11** | Counterfeit pharmaceutical trade represents a material international economic and public-health risk. | Intergovernmental Research | OECD/EUIPO — *Trade in Counterfeit Pharmaceutical Products*, Illicit Trade, OECD Publishing, Paris, 2020 | Pharmaceutical-specific counterfeit-trade analysis | **Verified with Scope Qualification** | Prefer this pharmaceutical-specific report over generic counterfeit-goods statistics. Historical estimates must retain their measurement period and should not be presented as current 2026 market-size estimates. |
| **CL-12** | Distributed-ledger and blockchain approaches to pharmaceutical drug traceability have been investigated in peer-reviewed research. | Peer-Reviewed Research | Ahmad Musamih, Khaled Salah, et al. — “A Blockchain-Based Approach for Drug Traceability in Healthcare Supply Chain,” *IEEE Access*, Vol. 9, pp. 9728–9743, 2021, DOI: 10.1109/ACCESS.2021.3049920 | Evaluated blockchain-based pharmaceutical traceability architecture | **Verified** | This establishes that the pattern has been researched. It does not establish regulatory endorsement, universal deployment, physical-product authenticity, or architectural necessity. |
| **CL-13** | W3C Decentralized Identifiers (DIDs) v1.0 is a W3C Recommendation providing a standardized decentralized-identifier data model. | Primary Standard | W3C — *Decentralized Identifiers (DIDs) v1.0* | W3C Recommendation | **Verified** | DIDs are treated by RA-001 as an optional identity mechanism, not a pharmaceutical requirement. |
| **CL-14** | EPCIS event interoperability and regulatory product verification solve related but different assurance problems. | Primary Standard + Primary Regulatory + KryoNex Research Synthesis | GS1 EPCIS/CBV; FDA DSCSA materials; EU Delegated Regulation 2016/161; EMVS implementation material | Cross-source architectural comparison | **Research Synthesis** | Event visibility, regulatory verification, digital evidence integrity, and physical authenticity must not be collapsed into one concept. |
| **CL-15** | Environmental sensor information becomes more useful for pharmaceutical traceability when it can be correlated with relevant product or logistics identity, time, location, event, and custody context. | Primary Standard + KryoNex Research Synthesis | GS1 EPCIS 2.0 sensor capabilities plus RA-001 systems analysis | Observation/event correlation model | **Research Synthesis** | Do not claim universal EPCIS-based sensor correlation in current pharmaceutical deployments. Correlation strength depends on implementation and evidence quality. |
| **CL-16** | Serialization establishes machine-readable product identity but does not independently establish complete physical custody history or the physical authenticity of a medicine. | Primary Standard + Regulatory Context + KryoNex Research Synthesis | GS1 identification standards; pharmaceutical serialization and verification frameworks | Cross-source architectural analysis | **Research Synthesis** | Product Identity is intentionally separated from Event Integrity, Organizational Authority, and Observation Correlation in F03/F04. |
| **CL-17** | Existing pharmaceutical traceability is appropriately modeled in RA-001 as a federation of independently governed enterprise, partner, standards-based exchange, and regulatory systems rather than as one universal global database. | Multi-source Systems Analysis | GS1; FDA; European regulatory/EMVS architecture; Indian regulatory frameworks; enterprise systems analysis | RA-001 current-state analysis / F02 | **Research Synthesis** | Architectural abstraction developed by KryoNex Research; not attributed to a single external authority. |
| **CL-18** | A digitally valid event, signature, hash, ledger entry, or credential does not by itself prove that the corresponding physical medicine, physical handover, or physical-world assertion is correct. | Security Principle + KryoNex Research Synthesis | Cross-domain security reasoning applied to pharmaceutical traceability | F03/F04 assurance-boundary analysis | **Research Synthesis** | Cryptographic integrity can protect a digital representation without independently establishing the truth of the physical event represented. |
| **CL-19** | A boundary between organizations, systems, or evidence domains is not itself evidence of a control failure. | KryoNex Research Synthesis | RA-001 F03 methodology | Trust & Visibility Boundaries | **Research Synthesis** | Boundaries identify where assurance questions arise; they must not be manufactured or automatically characterized as vulnerabilities. |
| **CL-20** | Assurance mechanisms should be selected only after the relevant evidence, organizational, physical-digital, or governance boundary has been identified. | KryoNex Research Synthesis | RA-001 architectural methodology | Evidence-before-technology principle | **Research Synthesis** | Original RA-001 design principle intended to prevent technology-first architecture. |
| **CL-21** | Distributed ledgers are one possible multi-party evidence or shared-state mechanism but are not a prerequisite for pharmaceutical traceability. | Peer-Reviewed Research + KryoNex Research Synthesis | Musamih et al.; existing regulatory/standards architectures; RA-001 trade-off analysis | F04 mechanism evaluation | **Research Synthesis** | Core vendor-neutrality constraint. DLT remains conditional on governance, privacy, latency, complexity, operational, and multi-party shared-state requirements. |
| **CL-22** | RA-001 F04 evaluates conventional PKI, digital signatures, credentials, trusted directories, protected or append-only evidence structures, federated verification, shared ledgers, and other mechanisms as conditional implementation options according to the assurance boundary rather than mandatory components. | Proposed Architecture | KryoNex Research RA-001 | F04 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability | **Proposed** | Inclusion in the architecture does not imply universal necessity, regulatory endorsement, or production adoption. |
| **CL-23** | Existing operational, trading-partner, and regulatory systems remain authoritative in their respective domains; F04 introduces boundary-assurance capabilities rather than replacing those systems of record. | Proposed Architecture + Regulatory Constraint | KryoNex Research synthesis based on U.S., EU, India, standards, and enterprise-system boundaries | F04 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability | **Proposed** | F04 must not be interpreted as creating a universal pharmaceutical authority, universal repository, or replacement regulatory network. |
| **CL-24** | RA-001 intentionally develops the architecture in sequence: F01 establishes the physical domain, F02 establishes the current traceability landscape, F03 identifies assurance boundaries, and F04 evaluates a logical assurance architecture. | Research Methodology | KryoNex Research | RA-001 figure-development methodology | **Proposed / Methodological** | This sequence prevents solution-first reasoning and preserves the distinction between current state, analytical synthesis, and proposed architecture. |

---

# 5. Regulatory Boundary Notes

## 5.1 United States

RA-001 must distinguish between:

- statutory DSCSA requirements;
- FDA implementation guidance, exemptions, waivers, and enforcement policy;
- standards used for traceability-information exchange;
- industry-developed product-verification infrastructure;
- industry-developed organizational credentialing mechanisms; and
- optional technical assurance mechanisms.

FDA authority must not be attributed to GS1, OCI, VRS providers, credential
issuers, or other industry organizations.

Likewise, an industry implementation pattern must not be described as a
statutory requirement unless the governing law or regulator establishes that
requirement.

VRS and credential-based ATP verification are relevant implementation
mechanisms, but neither should be represented as establishing the physical
truth of a product or transaction.

---

## 5.2 European Union

RA-001 must distinguish between:

- Directive 2011/62/EU (Falsified Medicines Directive);
- Commission Delegated Regulation (EU) 2016/161;
- the European Medicines Verification System (EMVS);
- the European Hub and national verification systems;
- verification/decommissioning responsibilities of applicable supply-chain
  actors; and
- broader logistics visibility or traceability-event systems.

The European medicines-verification environment is appropriately described as
an end-to-end medicines-verification model, but this terminology must not be
interpreted as continuous recording of every physical custody or logistics
event.

EMVS medicines verification and EPCIS-style event visibility are related but
different architectural functions.

---

## 5.3 India

RA-001 must preserve temporal and regulatory context.

### Domestic

Schedule H2 and other applicable Drugs Rules / CDSCO requirements form part of
the domestic pharmaceutical identification and traceability environment.

G.S.R. 506(E), notified on 22 June 2026, expanded Schedule H2 to additional
medicine categories.

The date of notification must be distinguished from the applicable
commencement dates of the expanded requirements.

RA-001 must therefore avoid wording that implies all June 2026 Schedule H2
expansions were already fully operative in July 2026.

### Export

Historical Indian pharmaceutical-export traceability included DGFT Track and
Trace procedures and DAVA/iVEDA-related implementation mechanisms.

However, DGFT Public Notice No. 44/2024-25-DGFT withdrew Para 2.76 of the Handbook
of Procedures 2023 with immediate effect. The notice states that
implementation of the authentication system for exported drug formulations
shall be undertaken by the Ministry of Health & Family Welfare in line with
the Drugs Rules, 1945. Earlier DAVA/iVEDA mechanisms should therefore be
treated as historical implementation context rather than presented as the
unchanged current DGFT export traceability architecture..

Accordingly, DAVA/iVEDA may be discussed as historical implementation context
where useful, but should not be presented as the unchanged current regulatory
anchor for pharmaceutical exports in July 2026.

Domestic Schedule H2 and export-related regulatory evolution must not be
collapsed into one Indian traceability architecture.

---

# 6. Standards and Implementation Boundary Notes

## 6.1 GS1 Identification

GS1 identifiers and data carriers provide standardized mechanisms relevant to
product and logistics-unit identification.

Identification alone does not establish:

- complete custody provenance;
- physical authenticity;
- organizational authorization; or
- environmental observation integrity.

---

## 6.2 GS1 EPCIS / CBV

EPCIS and CBV provide standardized mechanisms for representing and exchanging
visibility-event information and associated business vocabulary.

EPCIS should not be described as:

- a pharmaceutical regulator;
- a universal centralized repository;
- proof that a physical event actually occurred exactly as represented; or
- universally deployed across all pharmaceutical organizations.

EPCIS 2.0 sensor-related capabilities establish standards capability, not
universal implementation.

---

## 6.3 EMVS

EMVS provides medicines-verification infrastructure under the European
medicines safety-features framework.

It should not be conflated with a complete EPCIS-style logistics-event history.

Pack verification/decommissioning and supply-chain event visibility answer
different questions and may coexist within a broader architecture.

---

## 6.4 VRS

Verification Router Service implementations provide industry-developed routing
and product-identifier verification capabilities in the U.S. pharmaceutical
ecosystem.

RA-001 must not characterize VRS as:

- the complete DSCSA architecture;
- an FDA-operated system;
- proof of physical product authenticity; or
- a universally mandated implementation topology.

---

## 6.5 W3C Verifiable Credentials / DIDs

Verifiable Credentials and DIDs provide general-purpose standards relevant to
machine-verifiable claims and decentralized identifiers.

Their existence as W3C Recommendations does not imply:

- mandatory pharmaceutical adoption;
- FDA or EU regulatory endorsement;
- automatic legal authority;
- physical product authenticity; or
- correctness of the underlying asserted fact.

Trust remains dependent on issuer authority, credential status, subject
binding, governance, policy, and the authoritative evidence underlying the
claim.

---

## 6.6 OCI

OCI provides industry interoperability profiles and credentialing mechanisms
relevant to organizational identity and Authorized Trading Partner status in
the U.S. DSCSA ecosystem.

OCI is not a regulator.

OCI credential mechanisms should therefore be represented as
organizational-evidence and interoperability mechanisms rather than as a new
source of statutory authority.

---

## 6.7 GAMP 5

GAMP 5 provides established industry guidance for risk-based lifecycle
management of GxP computerized systems.

It should not be described as a universal statutory requirement.

---

## 6.8 ISO/IEC 15459

ISO/IEC 15459 provides broader unique-identification standards context.

Where RA-001 discusses GS1 SSCC and GS1 logistics-unit identification, the
principal source should remain GS1 rather than implying that ISO/IEC 15459
defines the GS1 aggregation model.

---

# 7. Architectural Provenance Register

The following RA-001 concepts are **KryoNex Research synthesis** or proposed
architecture.

They must not be represented as concepts created or mandated by an external
regulator, standards body, academic publication, or commercial organization.

| Architecture Element | Provenance | Status |
|---|---|---|
| Separation of physical pharmaceutical flow from the surrounding digital traceability landscape | KryoNex Research systems analysis | Original synthesis |
| F01 — Contemporary Pharmaceutical Supply Chain | KryoNex Research | Original figure / synthesis |
| F02 — Current Pharmaceutical Traceability Landscape | KryoNex Research synthesis from standards, regulatory frameworks, implementation mechanisms, and enterprise-systems analysis | Developed — under technical review |
| Boundary ≠ Failure principle | KryoNex Research | Original analytical principle |
| F03 — Trust & Visibility Boundaries | KryoNex Research assurance-boundary synthesis | Developed — under technical review |
| Four assurance dimensions: Product Identity, Event Integrity, Organizational Authority, Observation Correlation | KryoNex Research | Original architectural decomposition |
| Physical truth vs. digital assertion distinction | KryoNex Research synthesis from security and traceability principles | Original analytical framing |
| Federation-of-independently-governed-systems model | KryoNex Research | Original architectural framing |
| Evidence-before-technology principle | KryoNex Research | Original design principle |
| Preservation of authoritative enterprise and regulatory systems | KryoNex Research architecture constraint informed by regulatory/current-state analysis | Proposed architecture constraint |
| Evidence Protection as a cross-cutting concern | KryoNex Research | Proposed architecture |
| Trust & Lifecycle Governance as a cross-cutting concern | KryoNex Research | Proposed architecture |
| F04 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability | KryoNex Research | Architecturally complete — under technical review |
| Distributed ledger treated as optional and conditional rather than foundational | KryoNex Research | Active architecture constraint |

This provenance register establishes authorship of the architectural selection,
classification, decomposition, comparison, and synthesis without claiming
ownership of external standards, regulations, technologies, organization
names, or prior research.

---

# 8. Evidence-to-Figure Mapping

## F01 — Contemporary Pharmaceutical Supply Chain

**Purpose:** Establish the physical pharmaceutical supply-chain and handover
model.

Evidence basis includes:

- pharmaceutical distribution structures;
- serialization and logistics-unit identification practices;
- regulatory trading-partner models; and
- KryoNex Research abstraction.

F01 is not intended to reproduce the operating model of any single company or
jurisdiction.

---

## F02 — Current Pharmaceutical Traceability Landscape

**Purpose:** Map the current digital, enterprise, partner, standards-based, and
regulatory environments surrounding the physical supply chain.

Evidence/synthesis basis includes:

- CL-01 — U.S. DSCSA regulatory context;
- CL-02 — EPCIS/CBV;
- CL-03 — EU medicines verification;
- CL-04 — Indian domestic Schedule H2 evolution;
- CL-05 — Indian pharmaceutical-export regulatory evolution;
- CL-08 — VRS;
- CL-10 — logistics-unit identification;
- CL-14 — event interoperability vs. regulatory verification; and
- CL-17 — federation of independently governed systems.

F02 represents **current-state architecture** and must not be presented as the
proposed KryoNex architecture.

Historical DAVA/iVEDA implementation context must not be mistaken for the
unchanged July 2026 Indian export-regulatory state.

---

## F03 — Trust & Visibility Boundaries

**Purpose:** Identify where one participant relies on evidence generated,
controlled, transmitted, interpreted, or asserted by another participant,
system, device, or authority.

Evidence/synthesis basis includes:

- CL-14 — event interoperability vs. verification;
- CL-15 — observation correlation;
- CL-16 — identity vs. custody/authenticity;
- CL-17 — independently governed systems;
- CL-18 — digital assertion vs. physical truth; and
- CL-19 — Boundary ≠ Failure.

F03 frames four distinct assurance questions:

1. **Product Identity**
2. **Event Integrity**
3. **Organizational Authority**
4. **Observation Correlation**

F03 must not manufacture a failure or vulnerability merely to justify F04.

---

## F04 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability

**Purpose:** Synthesize the physical model (F01), current traceability
landscape (F02), and assurance-boundary analysis (F03) into a vendor-neutral
logical architecture for cross-organizational pharmaceutical traceability.

F04 preserves existing authoritative operational, trading-partner, and
regulatory systems rather than proposing their replacement.

Its logical structure comprises:

1. Physical Pharmaceutical Supply Chain
2. Identification & Observation
3. Authoritative Operational Systems
4. Traceability Semantics & Exchange
5. Boundary Assurance Capabilities
6. Regulatory & Partner Ecosystems

The four assurance dimensions remain:

- Product Identity;
- Event Integrity;
- Organizational Authority; and
- Observation Correlation.

Cross-cutting concerns include:

- Evidence Protection; and
- Trust & Lifecycle Governance.

Evidence/synthesis basis includes:

- CL-02 — EPCIS/CBV capabilities;
- CL-06/CL-07/CL-13 — credential and identity standards/patterns;
- CL-12 — distributed-ledger research;
- CL-14 — traceability interoperability vs. regulatory verification;
- CL-15 — observation correlation;
- CL-16 — identity vs. custody/authenticity;
- CL-17 — federation of independently governed systems;
- CL-18 — digital assertion vs. physical truth;
- CL-19 — Boundary ≠ Failure;
- CL-20 — evidence-before-technology;
- CL-21 — distributed-ledger optionality;
- CL-22 — conditional mechanism selection; and
- CL-23 — preservation of authoritative systems.

F04 is **KryoNex Research architectural synthesis**.

It is not presented as current universal pharmaceutical-industry architecture,
a regulatory mandate, or a required implementation topology.

The architecture does not prescribe distributed-ledger technology as a
mandatory layer.

Shared-ledger mechanisms remain conditional candidates where independently
governed shared state or shared evidence is justified after considering
governance, privacy, latency, complexity, operational requirements, and
available conventional alternatives.

---

# 9. Claims Requiring Special Editorial Care

The following wording should not appear in RA-001 without strong,
source-specific evidence and appropriate qualification:

- "Blockchain eliminates counterfeit medicines."
- "Blockchain guarantees authenticity."
- "Blockchain guarantees event truth."
- "IoT guarantees cold-chain integrity."
- "All pharmaceutical companies use EPCIS."
- "All EPCIS implementations use EPCIS 2.0."
- "The FDA mandates VRS."
- "OCI credentials prove legal authority."
- "A credential proves that the corresponding physical transaction occurred."
- "The EU tracks every pharmaceutical logistics event through EMVS."
- "EMVS is a complete pharmaceutical custody-history system."
- "DAVA is India's domestic pharmaceutical traceability system."
- "DAVA/iVEDA remains the unchanged current export-regulatory architecture."
- "All Schedule H2 expansion requirements became operative in June 2026."
- "GAMP 5 is legally mandatory."
- "A QR code proves a medicine is genuine."
- "A serialized product cannot be counterfeited."
- "A valid digital signature proves physical authenticity."
- "A hash proves that the original physical event was correct."
- "Distributed ledgers are required for end-to-end traceability."
- "One global pharmaceutical traceability architecture exists."
- "An organizational boundary is automatically a control failure."

Statements of this type require correction, qualification, or removal during
technical review.

---

# 10. Research Quality Rules

Before a claim is promoted into RA-001 v1.0:

1. Prefer the primary source whenever available.
2. Verify that the source actually supports the wording used.
3. Separate regulation from standards and industry implementation.
4. Separate a standard's technical capability from observed industry adoption.
5. Preserve jurisdiction, date, and effective-date context.
6. Distinguish a notification date from a commencement or enforcement date.
7. Do not convert historical implementation infrastructure into a current-state
   regulatory claim after the governing framework changes.
8. Do not convert academic prototypes into claims of production adoption.
9. Do not convert architectural possibilities into industry requirements.
10. Do not treat cryptographic integrity as proof of physical-world truth.
11. Do not treat machine-verifiable credentials as self-sufficient legal
    authority outside their governance and issuer context.
12. Do not use vendor marketing material as the sole evidence for a general
    industry claim.
13. Record unresolved contradictions rather than silently selecting the most
    convenient source.
14. Change a claim when evidence changes; do not defend an obsolete RA-001
    statement merely because it appeared in an earlier version.
15. Keep KryoNex Research synthesis visibly separate from externally sourced
    facts.
16. Keep proposed architecture visibly separate from current universal
    industry practice.
17. Preserve authoritative regulatory and enterprise systems unless the
    research establishes a specific reason not to.
18. Re-check time-sensitive regulatory claims immediately before publication.

---

# 11. Review Log

| Date | Version | Reviewer | Review Activity |
|---|---|---|---|
| 2026-07-27 | 0.4 | A. S. Tomar — KryoNex Research | Completed F01–F04 architecture and cross-figure consistency review; synchronized final publication figure assets; corrected generated-artwork terminology regressions; preserved current Indian regulatory/export treatment and technology-neutral assurance architecture. |
| 2026-07-24 | 0.4 | A. S. Tomar — KryoNex Research | Established claim-level evidence registry; separated regulatory, standards, implementation, research, synthesis, and proposed-architecture evidence classes. |
| 2026-07-26 | 0.4 | A. S. Tomar — KryoNex Research | Completed research-discovery reconciliation for F01–F04; incorporated July 2026 regulatory/current-state corrections; updated Indian domestic/export treatment; strengthened EU/EMVS and OCI distinctions; updated counterfeit-pharmaceutical evidence; synchronized F04 provenance and architecture status. |

---

# 12. Current Review State

# Research Notice

This register documents the research basis and architectural provenance of
RA-001.

External standards, regulations, publications, organization names, and
technical specifications remain attributable to their respective authors,
issuers, standards bodies, regulators, and organizations.

The selection, classification, comparison, architectural decomposition,
figures, trust-boundary methodology, assurance model, and systems-engineering
synthesis of RA-001 are developed by KryoNex Research.

**© 2026 A. S. Tomar , KryoNex Research .**
