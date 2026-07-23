# KryoNex Research

Research-driven insights on AI, Industrial IoT, Enterprise Architecture, Intelligent Automation, Supply Chain Technology, and Digital Transformation.

Published by KryoNex — [kryonex.live](https://kryonex.live)

Read `MANIFESTO.md` first. It defines what this publication stands for and
is the tiebreaker whenever a draft's tone or content is in question.

## Editorial Position

KryoNex Research publishes reference architectures, frameworks, and technical
analysis — not product marketing. Publications do not promote KryoNex's
commercial offerings and avoid sales language. The goal is work a CTO,
architect, or engineer would trust enough to cite.

## Repository Structure

```
MANIFESTO.md    What this publication stands for. Read first.

publications/   One folder per publication (RA-001, FM-001, ...):
                  draft.md            the publication itself
                  sources/            research source tracking (per-publication)
                  figures/            diagram source (.drawio) + exports (.svg/.png)
                  CHANGELOG.md        version history, published only after v1.0
                  review-notes.md     internal reviewer feedback — never published

frameworks/     Reusable non-article outputs, organized by type:
                  trust-models/
                  maturity-models/
                  decision-matrices/
                  implementation-patterns/

research-log/   Dated, unstructured research sessions (YYYY-MM-DD.md),
                spanning whatever publications are active that day.
                Research happens here first — never directly inside a draft.

diagrams/       Shared/reusable diagram assets not tied to one publication
references/     Shared citation library, standards docs (GS1, WHO, FDA, EMA, ISO, etc.)
templates/      Publication template, diagram rules, citation style,
                changelog/review-notes/research-log templates
images/         Brand assets (wordmark, color/type specimens)
editorial/      Brand style guide, editorial guidelines
checklists/     Review, SEO, and AI-discoverability checklists
```

## Publication Numbering

Prefix by type, sequential within each prefix:

| Prefix | Type |
|---|---|
| RA | Reference Architecture |
| FM | Framework / Maturity Model |
| EG | Engineering Guide |
| TN | Technical Note |
| WP | White Paper |

"Publications" — not "articles" — because most of these aren't articles in
the blog-post sense; they're durable technical references.

## Figure Numbering

`{publication-id}-F{NN}`, e.g. `RA-001-F01`. Always includes the publication
ID, never a bare "Figure 1" — keeps figures unambiguous when reused or cited
externally.

## Status

| ID | Type | Title | Status |
|---|---|---|---|
| RA-001 | Reference Architecture | Building Trust Across the Pharmaceutical Supply Chain: A Reference Architecture for End-to-End Traceability Using IoT and Distributed Ledgers | Research phase |
| FM-001 | Maturity Model | Industrial AI Adoption Maturity Model | Not started |
