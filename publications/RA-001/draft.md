---
id: RA-001
title: "Building Trust Across the Pharmaceutical Supply Chain"
subtitle: "A Reference Architecture for End-to-End Traceability"
author: "A. S. Tomar"
author_role: "KryoNex Research & Engineering Team"
status: "working-draft"
document_version: "0.4"
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

# Building Trust Across the Pharmaceutical Supply Chain

## A Reference Architecture for End-to-End Traceability

**RA-001 · Version 0.4 · Working Draft**

Prepared by **A. S. Tomar — KryoNex Research & Engineering Team**

**Status:** Under Technical Review  
**Last Updated:** 27 July 2026

> **Research status**
>
> RA-001 is a working reference architecture. It examines existing
> pharmaceutical traceability mechanisms and develops a vendor-neutral
> architectural model for connecting product identity, traceability events,
> environmental observations, enterprise systems and trust mechanisms across
> organizational boundaries.
>
> This version does not propose distributed-ledger technology, blockchain, IoT,
> or any other individual technology as a universal requirement.

---

## Executive Summary

Pharmaceutical traceability is not a single-system problem. A medicinal product
can pass through manufacturers, logistics providers, wholesalers, distributors,
pharmacies, hospitals, regulatory environments and other independently
operated organizations before reaching a patient. During that journey, physical
product movement must be associated with identifiers, serialization records,
business transactions, custody events, verification activities and, for some
products, environmental observations.

Significant infrastructure already exists. GS1 identification standards provide
globally recognized product and logistics identifiers. GS1 EPCIS and Core
Business Vocabulary (CBV) provide standards for sharing visibility-event data.
The United States, European Union, India and other jurisdictions operate
different regulatory and implementation models for pharmaceutical
serialization, verification and traceability.

The architectural challenge is therefore not simply to create another tracking
database. It is to understand how independently governed physical and digital
systems can exchange relevant evidence while preserving regulatory boundaries,
organizational control, interoperability, security and operational
performance.

RA-001 examines this problem from the point at which serialized pharmaceutical
packaging enters distribution through subsequent logistics and trading-partner
handovers toward dispensing. It separates six concerns that are frequently
collapsed into a single concept of "track and trace":

1. physical product movement.
2. product and logistics-unit identification.
3. traceability-event capture and exchange.
4. enterprise-system records.
5. environmental observations. and
6. identity, authorization and evidence validation across organizational
   boundaries.

The resulting reference architecture is deliberately vendor-neutral. Existing
regulatory repositories and enterprise systems remain authoritative within
their respective domains. Additional cryptographic credentials, signatures,
shared ledgers, or other trust mechanisms are considered optional architectural
patterns whose usefulness depends on the trust boundary being addressed.

The principal trade-off is therefore between stronger cross-organizational
verification and the additional governance, integration, latency, privacy and
operational complexity introduced by those mechanisms.

---

# 1. Why This Problem Matters

Medicines move through supply chains in which physical custody and digital
information are distributed across multiple organizations. Counterfeit,
falsified, diverted, stolen, improperly handled, or incorrectly represented
products can create consequences extending beyond conventional inventory loss:
the integrity of a pharmaceutical supply chain directly affects patient safety.

Counterfeiting is also part of a broader international illicit-trade problem.
OECD/EUIPO analysis has documented substantial international trade in
counterfeit and pirated goods and identifies pharmaceuticals among product
categories in which counterfeit goods can create significant health and safety
risks [11].

Pharmaceutical regulation has consequently moved progressively toward stronger
product identification and electronic verification. These initiatives have
created substantial traceability infrastructure, but the global environment is
not homogeneous.

A manufacturer may operate packaging-line serialization software and a
corporate serialization repository. A logistics provider may operate warehouse
and transportation systems. A wholesaler may receive EPCIS events. A pharmacy
may verify or decommission a serialized identifier. Regulators or industry
networks may operate separate verification or repository infrastructure.

Each system can be functioning correctly while cross-organizational visibility
remains incomplete.

The problem addressed by RA-001 is therefore:

> **How can pharmaceutical product identity, physical custody, traceability
> events, environmental evidence and independently governed digital systems
> be connected in a way that improves verifiability without replacing
> authoritative regulatory or enterprise systems?**

This question is intentionally broader than blockchain, IoT, serialization, or
any single technology.

---

# 2. Scope and Methodology

## 2.1 Research Scope

RA-001 focuses primarily on the pharmaceutical distribution lifecycle beginning
when packaged and serialized product becomes available for downstream
distribution.

The physical model includes:

- pharmaceutical manufacturer / packaging site.
- warehouse and dispatch operations.
- third-party logistics providers.
- distributors and wholesalers.
- pharmacies and healthcare dispensing environments and
- the final patient-facing handover.

The digital model considers:

- product identification and serialization.
- packaging aggregation.
- traceability-event generation.
- GS1 EPCIS and CBV.
- MES, serialization repositories, ERP, WMS and TMS.
- pharmacy and hospital dispensing systems.
- regulatory and trading-partner verification mechanisms.
- IoT and sensor observations where relevant. and
- mechanisms for validating identity, authorization, provenance and evidence.

## 2.2 Geographic Scope

RA-001 is globally oriented but uses three regulatory environments as major
reference points:

- United States.
- European Union.
- India.

These jurisdictions are not treated as having equivalent architectures.

The U.S. DSCSA environment, European medicines-verification environment and
Indian domestic/export traceability requirements have different legal,
technical and operational structures.

## 2.3 Research Method

RA-001 uses a systems-analysis approach rather than evaluating a specific
commercial platform.

Evidence is prioritized approximately as follows:

1. primary legislation, regulatory notifications and government guidance.
2. formal standards and specifications.
3. standards-body and industry implementation guidance.
4. peer-reviewed academic literature and
5. established technical and intergovernmental research.

Material factual and regulatory claims are mapped separately in the
`evidence-register.md` maintained with this publication.

## 2.4 Architectural Method

The architecture separates the problem into layers rather than beginning with a
preferred technology.

The analysis asks:

- Where is physical truth established?
- Where is product identity established?
- Which system creates each digital event?
- Which organization controls that system?
- Which information crosses organizational boundaries?
- Which participant is authorized to create, modify, verify, or consume it?
- What evidence links a digital record to a physical handover?
- Which records are legally or operationally authoritative?
- Where does verification depend on trust in another organization?
- Where could additional verification mechanisms create meaningful value?

This distinction is fundamental to RA-001.

## 2.5 Out of Scope

Version 0.4 does not attempt to:

- replace DSCSA, EMVS/NMVS, CDSCO, Indian domestic and export regulatory, or other regulatory infrastructure.
- define a new pharmaceutical serialization standard.
- prescribe a specific blockchain or distributed-ledger platform.
- prescribe a particular IoT vendor or device.
- claim that digital records alone establish physical authenticity.
- provide a production deployment blueprint for a specific organization.
- provide legal or regulatory advice or
- claim that one architecture applies unchanged across all jurisdictions.

---

# 3. Current Pharmaceutical Traceability Landscape

## What is pharmaceutical traceability?

For the purposes of RA-001, pharmaceutical traceability is the ability to
identify a medicinal product and reconstruct relevant events associated with
its movement and handling through the supply chain.

Effective traceability can involve several different forms of evidence:
serialized product identifiers, logistics-unit identifiers, business
transactions, event records, regulatory verification, custody changes and
environmental observations.

These records are not necessarily created or controlled by the same system.

---

## 3.1 Product Identification and Serialization

Pharmaceutical traceability begins with the ability to identify products and,
where required, individual saleable units.

GS1-based implementations can combine product identifiers with serial numbers,
batch or lot information and expiration information in machine-readable data
carriers such as 2D DataMatrix symbols.

Logistics hierarchies introduce another level of identity. Cases, pallets and
other logistics units can be assigned identifiers such as the Serial Shipping
Container Code (SSCC).

Aggregation can then establish parent-child associations between serialized
saleable units and higher packaging levels.

This distinction matters because:

> **product identity is not the same thing as custody history.**

A correctly serialized package establishes an identity reference. It does not,
by itself, prove every physical location, custody change, environmental
condition, or business transaction associated with that package.

---

## 3.2 Traceability Events and EPCIS

Identification becomes operationally useful when systems record what happened
to an identified object.

GS1 EPCIS provides a standardized model for visibility-event information.
Together with the GS1 Core Business Vocabulary, EPCIS can represent business
events and their context across supply-chain processes [2].

Depending on the implementation, relevant lifecycle activities can include:

- commissioning identifiers.
- aggregation and disaggregation.
- packing.
- shipping.
- receiving.
- transformation.
- dispensing or decommissioning and
- other business-process events.

EPCIS 2.0 extends the standards environment beyond legacy XML-centric
implementations. It supports JSON/JSON-LD representations, REST-oriented
interfaces and sensor-related data capabilities [2].

RA-001 therefore treats EPCIS as an important interoperability layer rather
than as a centralized pharmaceutical database.

An EPCIS event can answer questions such as:

- **what** objects were involved.
- **when** the event occurred.
- **where** it occurred and
- **why** the event occurred in a particular business context.

The reliability of the resulting history still depends on the systems and
organizations creating and exchanging those events.

---

## 3.3 Enterprise Systems

Traceability information is generated and consumed by several classes of
enterprise and operational systems.

### Manufacturing Execution Systems

MES and packaging-line systems coordinate manufacturing and packaging
operations and can participate in serialization workflows.

### Serialization Repositories

Serialization repositories maintain identifier states, packaging hierarchies,
commissioning information and related serialization records.

### Enterprise Resource Planning

ERP systems associate product movement with commercial and organizational
processes such as orders, invoices, customers and inventory accounting.

### Warehouse Management Systems

WMS platforms manage warehouse operations including receiving, put-away,
picking, packing and dispatch.

### Transportation Management Systems

TMS platforms coordinate shipment planning, carriers, routes and
transportation execution.

### Pharmacy and Hospital Systems

Endpoint systems can participate in verification, dispensing, decommissioning,
inventory management and patient-facing workflows depending on jurisdiction
and implementation.

No single one of these systems necessarily represents the complete
pharmaceutical journey.

The current landscape is therefore better understood as a **federation of
systems of record and operational systems** rather than one global tracking
platform.

---

## 3.4 Partner Data Exchange

Supply-chain visibility requires selected information to cross organizational
boundaries.

GS1 EPCIS/CBV provides a standards-based mechanism for representing and
exchanging visibility-event information. EPCIS 2.0 supports modern
representations and interfaces, while organizations may also continue to
operate legacy EPCIS environments or other partner-integration mechanisms [2].

Real implementations can therefore contain combinations of:

- EPCIS interfaces.
- XML-based exchanges.
- JSON/JSON-LD.
- REST APIs.
- AS2.
- managed file transfer.
- SFTP.
- message brokers.
- integration platforms and
- proprietary trading-partner APIs.

RA-001 does not assume that every participant operates EPCIS 2.0 natively.

### Legacy interoperability

Where organizations continue to operate EPCIS 1.2 or other legacy exchange
formats, implementations may require transformation or compatibility services
when integrating with EPCIS 2.0 environments.

Transformation introduces its own engineering questions:

- semantic preservation.
- schema-version management.
- event deduplication.
- identifier normalization.
- error handling.
- retry behavior and
- provenance of transformed records.

Interoperability therefore involves more than converting one payload syntax
into another.

---

## 3.5 Regulatory and Partner Architectures

Pharmaceutical traceability cannot be represented accurately as one global
regulatory model.

### 3.5.1 United States — DSCSA

The U.S. Drug Supply Chain Security Act establishes requirements intended to
enable electronic and interoperable identification and tracing of certain
prescription drugs as they move through the supply chain [1].

The DSCSA environment involves authorized trading partners, product
identifiers, transaction information, verification, investigation of suspect
and illegitimate product and interoperable electronic exchange.

Verification Router Service implementations have also emerged as
industry-developed mechanisms supporting product-identifier verification
workflows, including workflows associated with saleable returns.

VRS should not be interpreted as the U.S. equivalent of the European medicines
verification repository architecture. It is one mechanism within the broader
U.S. implementation ecosystem.

FDA has also provided phased exemptions and enforcement approaches during
DSCSA implementation. In particular, qualifying small dispensers and, where
applicable, their trading partners have exemptions from specified enhanced drug
distribution security requirements through November 27, 2026 [1].

RA-001 therefore treats DSCSA implementation state as time-sensitive regulatory
context rather than a static technical specification.

### 3.5.2 European Union — FMD / EMVS

The European pharmaceutical verification model follows a different
architecture.

The Falsified Medicines Directive and Delegated Regulation (EU) 2016/161
establish safety-feature and verification requirements for applicable medicinal
products [15, 3].

The European Medicines Verification System operates through a European and
national repository structure. Manufacturers or marketing authorization
participants upload relevant product/serialization information, while
verification and decommissioning occur according to regulated workflows,
including at the dispensing endpoint and specified wholesaler scenarios.

The EU model is therefore primarily an **end-to-end medicines-authentication
model supplemented by defined verification activities**, rather than a
continuous replica of every logistics event occurring between manufacturer and
patient.

This distinction is important when comparing EMVS with EPCIS-based event
visibility.

### 3.5.3 India — Domestic and Export Traceability

India's pharmaceutical traceability environment should be interpreted with
separate domestic and export-policy contexts.

For the domestic market, Schedule H2 of the Drugs Rules establishes
barcode/QR-related identification requirements for applicable formulations.
On 22 June 2026, the Ministry of Health and Family Welfare notified
G.S.R. 506(E), expanding Schedule H2 to additional medicine categories,
including all vaccines, all antimicrobials, specified narcotic drugs and
psychotropic substances, and all anticancer drugs [5].

The June 2026 notification date should not be interpreted as meaning that all
expanded requirements were already operative at that date. The applicable
commencement dates must be considered separately when evaluating the current
regulatory state.

India's pharmaceutical-export traceability environment has also evolved.
Historically, DGFT Track and Trace procedures and DAVA/iVEDA-related
mechanisms were used for export serialization and reporting. However, DGFT
Public Notice No. 44/2024-25, dated 31 January 2025, withdrew Para 2.76 of
the Handbook of Procedures 2023 concerning the Track and Trace procedure
for exports of drug formulations [6].

Accordingly, RA-001 treats DAVA/iVEDA as relevant historical implementation
context rather than as the unchanged current regulatory anchor for Indian
pharmaceutical exports. The applicable current framework should instead be
evaluated against subsequent Government of India policy and Drugs Rules
requirements.

---

## 3.6 Environmental Monitoring

Serialization establishes identity, but pharmaceutical integrity can also
depend on environmental conditions.

Temperature-sensitive medicines and biological products may be monitored using
devices such as:

- temperature data loggers.
- humidity sensors.
- active IoT sensors.
- location-aware monitoring devices and
- shock or handling sensors where appropriate.

Historically and operationally, environmental telemetry can reside in systems
separate from serialization and custody-event records. Data may be downloaded
from devices, retained by logistics providers, included in quality
documentation, or exposed through monitoring platforms.

This creates an architectural question:

> Can an organization reliably associate an environmental observation with the
> correct product, logistics unit, location, time interval and custody event?

EPCIS 2.0 provides standardized capabilities for incorporating sensor data into
visibility information, including information relevant to cold-chain
monitoring [2].

However, **standards capability must not be confused with universal industry
deployment**.

The existence of EPCIS sensor-data capabilities does not mean that all
pharmaceutical organizations currently correlate environmental telemetry with
custody events using EPCIS.

RA-001 therefore treats telemetry correlation as an architectural capability
whose implementation varies between organizations and supply chains.

---

# 4. Technical and Trust Challenges

The current landscape already provides significant product-identification,
serialization, event-exchange, enterprise and regulatory capabilities.

RA-001 does not assume these systems are failures.

Instead, it identifies challenges that emerge when evidence must cross
organizational and technological boundaries.

## 4.1 Fragmented System Authority

Different systems are authoritative for different facts.

For example:

- a packaging system may establish serialization state.
- a WMS may establish warehouse execution.
- a TMS may establish transportation activity.
- a sensor platform may record temperature.
- a trading partner may record receipt.
- a regulatory repository may establish verification state.

No single system necessarily has authority over all of them.

## 4.2 Digital Event vs. Physical Reality

A digital event stating that a product was received does not independently
prove that the physical item corresponding to the identifier was present.

Similarly, a valid barcode does not prove that the packaging carrying that
barcode has not been copied, diverted, substituted, or otherwise compromised.

Traceability architectures must therefore distinguish:

**identifier validity** from **physical authenticity**.

## 4.3 Custody Continuity

Physical custody changes can occur across independently operated organizations.

A traceability history is stronger when shipment, dispatch, receipt and
aggregation records can be correlated consistently, but gaps can occur when:

- identifiers are not captured.
- event data is delayed.
- partners use incompatible systems.
- aggregation relationships change.
- exceptions are handled manually or
- data remains within one participant's system.

## 4.4 Identity and Authorization

A technically valid message still raises questions:

- Who created it?
- Was that organization authorized to create that event?
- Was the sending system acting for the claimed organization?
- Has the message been altered?
- Is the credential or authorization still valid?

Transport security alone does not answer every organizational-trust question.

## 4.5 Environmental Evidence Correlation

Sensor data becomes substantially more useful when it can be correlated with:

- a product or logistics-unit identifier.
- a time interval.
- a physical location.
- a shipment.
- a custody holder and
- relevant traceability events.

Without reliable correlation, telemetry may establish that a sensor experienced
a condition without conclusively establishing which products were affected.

## 4.6 Cross-Jurisdictional Differences

Regulatory architectures differ.

A system designed around one jurisdiction's verification model cannot simply
assume identical responsibilities, repositories, events, or legal meanings in
another jurisdiction.

## 4.7 Legacy and Partner Integration

Pharmaceutical organizations cannot replace every enterprise and partner
system simultaneously.

Any practical architecture must therefore accommodate:

- legacy interfaces.
- asynchronous exchange.
- multiple schema versions.
- partial partner adoption.
- temporary network failures.
- retries.
- duplicate messages and
- differing organizational modernization timelines.

## 4.8 Data Governance and Confidentiality

Greater visibility is not automatically better.

Pharmaceutical and logistics information can reveal commercially sensitive
relationships, shipment volumes, locations, inventory positions, or other
information that participants may not be entitled to access.

A trust architecture must therefore answer not only:

> "Can this information be shared?"

but also:

> "Who needs this information, for what purpose and at what level of
> granularity?"

---

# 5. Reference Architecture

RA-001 develops the reference architecture incrementally.

The figures intentionally separate the physical supply chain from the digital
systems surrounding it. This prevents technology diagrams from obscuring where
the underlying evidence originates.

---

## 5.1 F01 — Contemporary Pharmaceutical Supply Chain

![Figure 1 — Contemporary Pharmaceutical Supply Chain](figures/RA-001-F01-v0.4-PUBLICATION.png)

**Figure 1. Contemporary Pharmaceutical Supply Chain.**  
A conceptual physical-flow model from pharmaceutical packaging and
serialization through logistics, distribution, dispensing and the final
patient-facing handover.

**Source:** KryoNex Research synthesis. The figure represents an architectural
abstraction rather than the operating model of any single company or
jurisdiction.

F01 establishes the physical domain against which later digital evidence is
evaluated.

At each handover, different questions can arise:

| Physical stage | Relevant architectural questions |
|---|---|
| Packaging | Which identifier was commissioned and attached to the physical package? |
| Aggregation | Which serialized units belong to which case or pallet? |
| Dispatch | Which physical logistics unit left which controlled location? |
| Transportation | Who had custody and what environmental conditions were observed? |
| Receiving | Was the expected product physically received and recorded? |
| Distribution | Were aggregation and identity relationships preserved? |
| Dispensing | Was the identifier verified/decommissioned as required? |
| Patient handover | What product ultimately reached the endpoint? |

F01 does not claim that every supply chain contains exactly these actors or
handoffs. It establishes a common physical reference model for the subsequent
systems analysis.

---

## 5.2 F02 — Current Pharmaceutical Traceability Landscape

![Figure 2 — Current Pharmaceutical Traceability Landscape](figures/RA-001-F02-v0.4-PUBLICATION.png)

**Figure 2. Current Pharmaceutical Traceability Landscape.**  
A vendor-neutral systems view of the principal digital layers surrounding the
physical pharmaceutical supply chain, including product identification,
enterprise and edge systems, traceability-event interoperability,
trading-partner exchange, and jurisdiction-specific regulatory or partner
ecosystems.

**Source:** KryoNex Research synthesis derived from the RA-001 current-state
analysis and supporting standards and regulatory evidence.

F02 establishes that pharmaceutical traceability should not be treated as one
globally integrated technology stack.

Relevant information can be created, maintained, exchanged, or verified across
multiple independently governed environments, including:

1. product and logistics-unit identification;
2. serialization and aggregation systems;
3. MES, ERP, WMS, TMS, and serialization repositories;
4. GS1 EPCIS / CBV event exchange;
5. trading-partner interfaces and verification mechanisms;
6. dispensing and endpoint systems; and
7. jurisdiction-specific regulatory or partner ecosystems.

These components can interoperate while retaining separate ownership,
governance, authority, and system-of-record responsibilities.

The architectural significance of F02 is therefore not that existing
traceability infrastructure is absent. Substantial infrastructure already
exists.

The relevant question is where assurance must cross organizational, physical,
identity, observation, or system boundaries.

That question is examined in F03.

---

## 5.3 F03 — Trust and Visibility Boundaries

![Figure 3 — Trust and Visibility Boundaries in Pharmaceutical Traceability](figures/RA-001-F03-v0.4-PUBLICATION.png)

**Figure 3. Trust and Visibility Boundaries in Pharmaceutical Traceability.**  
A conceptual assurance model identifying transitions among physical products,
digital identities and observations, traceability records, independently
governed systems, trading partners, and external verification or regulatory
ecosystems.

**Source:** KryoNex Research architectural synthesis derived from the RA-001
current-state analysis and supporting standards and regulatory evidence.

F03 introduces an important distinction:

> **Boundary ≠ Failure**

A boundary identifies a transition at which assurance may depend on evidence,
controls, reconciliation, authorization, correlation, or governance. The
existence of a boundary does not itself demonstrate a control failure or
traceability weakness.

The analysis organizes cross-boundary assurance around four questions:

### Q1 — Product Identity

Is sufficient confidence established that the physical product corresponds to
the digital identifier being used?

Serialization can identify a package, but digital identity and physical reality
remain distinct domains.

### Q2 — Event Integrity

Can the origin, sequence, timing, and representation integrity of a digital
traceability event be assessed?

Integrity of a digital record should not be interpreted automatically as proof
that the represented physical-world event occurred exactly as recorded.

### Q3 — Organizational Authority

Can the participating organization be identified and can its relevant
authorization or status be evaluated for the applicable interaction?

Organizational identity, system authentication, regulatory status, and
transaction authorization are related but distinct concerns.

### Q4 — Observation Correlation

Can an environmental or logistics observation be associated with the relevant
product, logistics unit, event, location, time interval, or custody period at
the granularity required by the use case?

Sensor evidence becomes more useful when its relationship to traceability
identity and custody can be established.

F03 also highlights three recurring boundary patterns:

1. **Physical possession versus legal or transactional responsibility** —
   custody transfer and data-recording responsibility may occur on different
   timelines.

2. **Heterogeneous regulatory or implementation state** — participants may
   operate under different jurisdictional requirements, implementation
   timelines, or technical maturity.

3. **Endpoint verification and lifecycle closure** — some workflows require
   evidence of an appropriate terminal or lifecycle status.

F03 remains vendor-neutral and non-prescriptive. It does not establish
blockchain, distributed ledgers, credentials, or any other particular
technology as the required mechanism for resolving these boundaries.

The purpose of F03 is to establish which assurance requirements are sufficiently
supported by evidence to justify architectural mechanisms in F04.

---

## 5.4 Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability

Figure 4 synthesizes the findings from Figures 1–3 into a vendor-neutral logical assurance architecture for cross-organizational pharmaceutical traceability.

The architecture does not replace existing operational, trading-partner, or regulatory systems. Instead, it preserves authoritative systems of record while introducing logical assurance capabilities at boundaries where identity, traceability events, organizational authority, or environmental observations move between independently governed systems.

The architecture is organized into six logical layers:

1. **Physical Pharmaceutical Supply Chain** — The physical movement and handover of pharmaceutical products among manufacturers, logistics providers, distributors or wholesalers, pharmacies, healthcare providers, and other authorized participants.

2. **Identification & Observation** — Product and logistics-unit identifiers, including serialization, DataMatrix and SSCC, together with environmental or logistics observations such as temperature, humidity, shock, time, and other applicable sensor measurements.

3. **Authoritative Operational Systems** — Existing systems that remain responsible for their respective operational records, including MES, serialization repositories, ERP, WMS/TMS, EPCIS repositories, environmental-monitoring systems, and dispensing systems.

4. **Traceability Semantics & Exchange** — Standards and interfaces that allow independently governed systems to represent and exchange traceability information consistently. Relevant mechanisms include GS1 EPCIS and CBV together with APIs and applicable JSON, JSON-LD, XML, or legacy interfaces.

5. **Boundary Assurance Capabilities** — Logical capabilities used to evaluate assurance when information crosses organizational or system boundaries. Four assurance dimensions are considered:

   - **Product Identity** — whether sufficient evidence associates the identifier being evaluated with the relevant product, package, or logistics unit.
   - **Event Integrity** — whether the origin and subsequent integrity of a digital event representation can be evaluated.
   - **Organizational Authority** — whether evidence concerning organizational identity or status can be evaluated and then applied by the receiving party's authorization policy.
   - **Observation Correlation** — whether an environmental or logistics observation can be sufficiently associated with the relevant shipment, logistics unit, event, location, time interval, or custody period.

6. **Regulatory & Partner Ecosystems** — Existing jurisdiction-specific and trading-partner infrastructures, including applicable DSCSA infrastructure in the United States, EMVS/NMVS in Europe, Indian regulatory and export systems, and corresponding mechanisms in other jurisdictions.

Two cross-cutting control areas apply across these layers:

- **Evidence Protection** — mechanisms such as digital signatures, hashes or commitments, PKI, and audit controls may protect or help evaluate digital evidence where justified.
- **Trust & Lifecycle Governance** — issuance, key management, rotation, revocation, status checking, correction, supersession, and recovery must be governed throughout the evidence lifecycle.

Assurance outcomes must integrate with existing operational processes. Where sufficient assurance cannot be established, systems may require exception handling, reconciliation, investigation, quarantine, or other applicable procedures rather than silently treating uncertain evidence as trusted.

The architecture intentionally does not prescribe distributed-ledger technology as a permanent layer. Shared-ledger mechanisms remain conditional candidates and should be evaluated only where independently governed shared state provides material assurance that cannot be obtained more appropriately through authoritative registries, conventional APIs, signed evidence, or existing audit infrastructure.

Four distinctions constrain interpretation of the architecture:

- Event integrity does not establish the physical truth of the underlying event.
- Credential verification does not itself constitute transaction authorization.
- Device identity does not establish sensor calibration or measurement accuracy.
- An immutable or tamper-evident history does not establish that the original assertion was correct.

Accordingly, Figure 4 should be interpreted as a logical assurance model rather than a mandatory technology stack.

![Figure 4 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability](figures/RA-001-F04-v0.4-PUBLICATION.png)

*Figure 4 — Logical Assurance Architecture for Cross-Organizational Pharmaceutical Traceability. The model preserves existing authoritative systems while introducing boundary-specific assurance capabilities. Cryptographic, credential, sensor, or shared-ledger mechanisms are conditional implementation choices rather than universal requirements.*

---

## 5.5 Architectural Principle: Evidence Before Technology

RA-001 follows one central design principle:

> **Do not introduce a trust technology until the evidence boundary requiring
> that technology has been identified.**

For example, if two systems are operated by the same organization under a
controlled security boundary, conventional authenticated APIs and audit
controls may be sufficient.

If independently governed organizations need to verify claims without granting
one participant unilateral authority over shared evidence, additional
cryptographic or distributed mechanisms may become relevant.

This prevents the architecture from treating blockchain, distributed ledgers,
verifiable credentials, or IoT as solutions in search of a problem.

---

## 5.6 Distributed Ledgers as an Optional Pattern

Distributed-ledger approaches to pharmaceutical traceability have been
investigated in peer-reviewed research [12].

Such approaches can provide architectural patterns involving shared
transaction histories, cryptographic integrity, smart contracts and
multi-party verification.

They also introduce trade-offs:

- additional infrastructure.
- consensus or transaction-processing overhead.
- key management.
- privacy considerations.
- governance complexity.
- integration with authoritative systems.
- data-correction mechanisms and
- questions about which information should or should not be placed on a shared
  ledger.

RA-001 therefore does **not** make distributed-ledger technology a prerequisite.

A ledger should be considered only where the identified trust boundary and
governance model justify its additional complexity.

---

# 6. Engineering Considerations

## 6.1 Integration Before Replacement

A realistic architecture should assume that existing MES, ERP, WMS,
serialization, regulatory and partner systems will remain in operation.

Integration boundaries should therefore be explicit.

Potential patterns include:

- APIs.
- event brokers.
- EPCIS repositories.
- adapters.
- integration gateways.
- asynchronous queues and
- controlled batch exchange.

The architecture should avoid requiring a synchronized global replacement of
existing systems.

## 6.2 Event Idempotency

Supply-chain event exchange must tolerate retries and duplicate delivery.

Systems should establish stable event identities or equivalent mechanisms that
allow receivers to distinguish:

- a legitimate retry.
- a duplicate event.
- a correction.
- a new event and
- a conflicting assertion.

## 6.3 Time

Cross-organizational event histories depend on time.

Implementations should consider:

- timestamp precision.
- time zones.
- clock synchronization.
- event occurrence time versus record time.
- delayed/offline event submission and
- correction of inaccurate timestamps.

## 6.4 Identity and Key Management

Cryptographic verification creates operational dependencies of its own.

Key and credential lifecycle management should address:

- issuance.
- storage.
- rotation.
- revocation.
- compromise.
- organizational changes.
- delegated authority and
- recovery.

Cryptography without lifecycle governance can create a different class of
traceability failure.

## 6.5 Security

Security should be applied at multiple layers.

Relevant controls can include:

- device authentication.
- service authentication.
- encryption in transit.
- encryption at rest.
- authorization.
- least-privilege access.
- signed messages where justified.
- audit logging.
- anomaly detection and
- segmentation between operational and enterprise environments.

## 6.6 Data Minimization

Cross-organizational traceability does not require every participant to receive
every field.

Architecture should distinguish between:

- data required for interoperability.
- evidence required for verification.
- commercially sensitive information.
- personal information.
- regulatory records and
- internal operational telemetry.

Selective disclosure or restricted access may be preferable to universal
replication.

## 6.7 Performance

Performance requirements vary substantially by workflow.

Packaging-line operations can have strict local timing requirements, while
partner event exchange or regulatory verification can operate under different
latency and throughput constraints.

RA-001 deliberately avoids claiming universal transaction-volume or
microsecond-response requirements.

Performance targets should be derived from:

- packaging-line throughput.
- event volumes.
- number of trading partners.
- verification workflow.
- network conditions.
- retention requirements and
- regulatory obligations.

## 6.8 Availability and Offline Operation

Physical logistics do not stop whenever a remote service becomes unavailable.

Implementations should therefore consider:

- local buffering.
- retry queues.
- offline capture.
- reconciliation.
- degraded operating modes.
- duplicate suppression and
- recovery after extended disconnection.

## 6.9 Computerized-System Validation

Where traceability components participate in regulated GxP processes,
computerized-system lifecycle and validation requirements must be evaluated in
the applicable organizational and regulatory context.

ISPE GAMP 5 provides an established risk-based industry approach to compliant
GxP computerized systems [14].

RA-001 does not represent GAMP 5 as a universal statutory mandate.

## 6.10 Cost Drivers

Major cost drivers can include:

- packaging-line integration.
- serialization infrastructure.
- partner onboarding.
- EPCIS repositories.
- integration middleware.
- sensors and gateways.
- network connectivity.
- security infrastructure.
- credential/key management.
- validation.
- monitoring.
- support.
- regulatory change and
- data retention.

A technically sophisticated trust mechanism that significantly increases
partner onboarding cost may reduce practical adoption.

Architecture decisions should therefore be evaluated against operational value,
not technical novelty.

---

# 7. Limitations

RA-001 has deliberate limitations.

## 7.1 Digital Traceability Cannot Guarantee Physical Authenticity

A cryptographically valid record can prove properties of a digital assertion.

It cannot independently prove that the physical medicine associated with that
assertion is genuine.

Physical anti-tamper controls, regulated packaging, inspection, quality
processes, enforcement and other controls remain necessary.

## 7.2 Garbage In, Verifiable Garbage Out

Tamper-resistant storage cannot make an incorrect observation true.

If a compromised device, malicious participant, incorrect scanner, or faulty
integration creates false data, stronger immutability may preserve the false
data more reliably.

Input trust remains a separate problem.

## 7.3 Regulatory and Operational Systems Remain Authoritative

The proposed logical assurance architecture does not replace applicable
regulatory, verification, trading-partner, or enterprise systems.

Depending on jurisdiction and workflow, authoritative environments can include:

- FDA/DSCSA regulatory requirements and associated trading-partner systems;
- European medicines-verification infrastructure;
- CDSCO and other applicable Indian regulatory mechanisms;
- jurisdiction-specific national or regional repositories;
- legally required organizational records; and
- authoritative enterprise systems operated by supply-chain participants.

Historical infrastructure should not automatically be treated as current
regulatory authority when the governing framework changes. For example,
DAVA/iVEDA remains relevant to the historical evolution of Indian
pharmaceutical-export traceability, while the applicable current regulatory
framework must be evaluated according to subsequent Government of India
policy and Drugs Rules requirements.

Any production implementation of RA-001 must therefore be mapped to the
applicable legal and operational environment rather than assuming that one
regulatory topology applies globally.

## 7.4 Jurisdictional Variation

The U.S., EU and Indian examples in RA-001 do not represent every
pharmaceutical market.

Additional jurisdictions can impose materially different serialization,
reporting, privacy, verification, retention, or data-localization requirements.

## 7.5 IoT Sensors Introduce Their Own Trust Boundary

Sensor data should not automatically be considered trustworthy because it is
digitally available.

Relevant considerations include:

- calibration.
- device identity.
- tamper resistance.
- battery state.
- placement.
- sampling frequency.
- connectivity.
- gateway integrity and
- chain of custody for the sensor itself.

## 7.6 Aggregation Is Not Permanently Static

Cases and pallets can be opened, repacked, disaggregated, or reaggregated.

Architectures that assume permanent parent-child relationships can produce
incorrect histories after legitimate logistics operations.

### 7.7 Architecture Status

Figures F01–F04 now form the complete logical architecture sequence for RA-001 v0.4:

- **F01** establishes the physical pharmaceutical supply-chain and handover model.
- **F02** maps the existing traceability and regulatory systems landscape.
- **F03** identifies trust and visibility boundaries and frames the four assurance questions.
- **F04** synthesizes those findings into a vendor-neutral logical assurance architecture.

F04 is architecturally complete for the v0.4 working draft. The publication remains under technical review because regulatory claims, evidence mappings, citations, terminology, and the complete document still require final verification before release.

---

# 8. Future Architectural Directions

This section describes possible architectural directions rather than
predictions of universal industry adoption.

## 8.1 Richer EPCIS 2.0 Integration

EPCIS 2.0 provides JSON/JSON-LD, REST-oriented interfaces and sensor-data
capabilities [2].

These capabilities can enable more developer-friendly event integration and
richer relationships between supply-chain events and environmental
observations.

Adoption will nevertheless depend on existing infrastructure, partner
readiness, regulation, cost and migration strategy.

## 8.2 Verifiable Organizational Identity

W3C Verifiable Credentials Data Model 2.0 became a W3C Recommendation in
May 2025 [8]. W3C Decentralized Identifiers (DIDs) v1.0 provides an
additional standardized identity primitive relevant to decentralized
identifier architectures [13].

Within pharmaceutical interoperability, industry initiatives such as the Open
Credentialing Initiative have developed credential-based approaches for
machine-verifiable organizational identity and Authorized Trading Partner
status [9].

These mechanisms can provide evidence concerning identity, qualification,
licensure, authorization status, or other organizational assertions.

A valid credential should not, however, be interpreted as automatically
authorizing a particular transaction. The receiving party must still evaluate
the issuer, credential status, subject binding, applicable policy, regulatory
context, and the authoritative evidence underlying the assertion.

Whether credential-based mechanisms are appropriate for a pharmaceutical
workflow therefore depends on governance, trust anchors, lifecycle management,
interoperability, policy, and regulatory acceptance.

## 8.3 Event and Sensor Correlation

Increasing correlation between product identity, logistics events and
environmental observations could improve investigation of cold-chain and
handling exceptions.

EPCIS 2.0 provides standards capabilities relevant to this model [2], but
implementation remains organization-specific.

## 8.4 Selective Cryptographic Verification

Not every traceability event needs a distributed ledger.

Future architectures may instead combine different trust mechanisms according
to boundary:

- authenticated APIs within controlled environments.
- signed messages between organizations.
- verifiable credentials for organizational claims.
- append-only evidence stores for audit.
- regulatory repositories for legally authoritative state and
- shared/distributed ledgers only where multi-party governance warrants them.

## 8.5 Stronger Physical-Digital Binding

One of the most difficult long-term problems is strengthening the relationship
between a physical object and its digital identity.

Possible approaches include combinations of:

- tamper-evident packaging.
- secure identifiers.
- RFID/NFC.
- device-assisted verification.
- optical or material signatures.
- sensor evidence and
- cryptographic mechanisms.

No single mechanism currently removes the need for layered physical and digital
controls.

---

# 9. Key Takeaways

- **Pharmaceutical traceability is a multi-system problem.** Product identity,
  enterprise records, logistics events, regulatory verification and physical
  custody are controlled by different systems and organizations.

- **Serialization is foundational but not equivalent to end-to-end trust.**
  A serialized identifier establishes machine-readable identity, additional
  evidence is required to reconstruct custody, handling and verification.

- **Existing standards should be treated as architecture foundations, not
  obstacles.** GS1 identifiers, EPCIS/CBV and jurisdiction-specific regulatory
  infrastructure already solve important parts of the problem.

- **Interoperability is primarily an organizational-boundary problem.** Open and
  widely adopted standards can reduce dependence on proprietary data models,
  but governance, authorization, semantics and evidence quality remain
  necessary.

- **IoT telemetry becomes more valuable when correlated with identity and
  custody.** Sensor data alone does not establish which pharmaceutical product
  experienced a particular environmental condition.

- **Distributed ledgers are an architectural option, not the starting
  assumption.** Their use should be justified by a specific multi-party trust
  or governance requirement.

- **Digital verification does not replace physical controls.** A trustworthy
  pharmaceutical supply chain requires both physical and digital evidence.

- **The proposed architecture strengthens assurance at organizational and
  system boundaries without requiring replacement of existing authoritative
  systems.** Product Identity, Event Integrity, Organizational Authority, and
  Observation Correlation are treated as distinct assurance dimensions.
  F01 establishes the physical domain, F02 maps the current traceability
  landscape, F03 identifies assurance boundaries, and F04 synthesizes those
  findings into a vendor-neutral logical assurance architecture. Candidate
  mechanisms are selected according to the boundary and use case rather than
  prescribed universally.

---

# 10. References

> **Reference note:** Regulatory and standards references are maintained with
> claim-level verification in `sources/evidence-register.md`. RA-001 v0.4
> remains under technical review; time-sensitive regulatory claims will be
> rechecked before publication.

[1] U.S. Food and Drug Administration (FDA), *Drug Supply Chain Security Act
(DSCSA)* implementation materials, including applicable FDA waivers,
exemptions, and stabilization-period guidance.

[2] GS1, *EPCIS Standard, Release 2.0* and *Core Business Vocabulary (CBV),
Release 2.0*.

[3] European Commission, *Commission Delegated Regulation (EU) 2016/161 of
2 October 2015 supplementing Directive 2001/83/EC by laying down detailed
rules for the safety features appearing on the packaging of medicinal
products for human use*.

[4] European Medicines Verification Organisation (EMVO), *The European
Medicines Verification System Explained*, EMVO-02343, Version 1.0,
16 June 2023.

[5] Government of India, Ministry of Health and Family Welfare,
*G.S.R. 506(E)*, 22 June 2026, amendment concerning Schedule H2 of the
Drugs Rules.

[6] Government of India, Directorate General of Foreign Trade,
*Public Notice No. 44/2024-25*, 31 January 2025, withdrawal of Para 2.76
of the Handbook of Procedures 2023 concerning Track and Trace for exports
of drug formulations.

[7] GS1, *GS1 General Specifications*, including standards for product and
logistics-unit identification and the Serial Shipping Container Code (SSCC).

[8] World Wide Web Consortium (W3C), *Verifiable Credentials Data Model
v2.0*, W3C Recommendation, 15 May 2025.

[9] Open Credentialing Initiative (OCI), *DSCSA Interoperability Profile
v3.4.0*, together with applicable credential issuer, wallet, and conformance
materials.

[10] GS1 US, Verification Router Service and Lightweight Messaging
implementation materials for pharmaceutical product-identifier verification
workflows.

[11] OECD/EUIPO, *Trade in Counterfeit Pharmaceutical Products*, Illicit
Trade, OECD Publishing, Paris, 2020.

[12] Ahmad Musamih, Khaled Salah, et al., “A Blockchain-Based Approach for
Drug Traceability in Healthcare Supply Chain,” *IEEE Access*, Vol. 9,
pp. 9728–9743, 2021. DOI: 10.1109/ACCESS.2021.3049920.

[13] World Wide Web Consortium (W3C), *Decentralized Identifiers (DIDs)
v1.0*, W3C Recommendation, 19 July 2022.

[14] International Society for Pharmaceutical Engineering (ISPE),
*GAMP 5: A Risk-Based Approach to Compliant GxP Computerized Systems*,
Second Edition, 2022.

[15] Directive 2011/62/EU of the European Parliament and of the Council of
8 June 2011 amending Directive 2001/83/EC as regards the prevention of the
entry into the legal supply chain of falsified medicinal products.

---

## Publication and Research Notice

RA-001 is an independent technical research publication developed by
**KryoNex Research**.

Standards, regulations, product names, organization names and technical
specifications referenced in this publication remain the property of their
respective organizations.

The diagrams, architectural synthesis, classifications, explanatory models,
and original analysis presented by KryoNex Research represent the authors'
interpretation of publicly documented standards, regulatory requirements,
technical literature and systems-engineering considerations.

Reference architectures are provided for informational and research purposes.
Implementation requirements vary by organization, jurisdiction, product class,
risk profile and regulatory environment.

This publication does not constitute legal, regulatory, medical, quality or
compliance advice.

**© 2026 KryoNex Research.**
