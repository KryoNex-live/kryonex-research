# Diagram Template & Rules

## Figure numbering
`{publication-id}-F{NN}` — e.g. `RA-001-F01`, `RA-001-F02`. Zero-padded to
two digits. This ID is the figure's name everywhere: file name, in-text
reference ("see RA-001-F01"), and caption prefix. Don't use bare "Figure 1"
alone — the publication ID makes it unambiguous when figures get reused,
cited externally, or pulled into other publications.

## File naming
`{publication-id}-F{NN}.{drawio|svg|png}` — e.g. `RA-001-F01.drawio`,
`RA-001-F01.svg`, `RA-001-F01.png`.
Keep the editable source (`.drawio` or equivalent) AND the exported formats
together in `publications/{id}/figures/`. All versions of a figure live in
one place, next to the article — nothing scattered in a shared pool that
drifts out of sync three years later.

## Visual rules (apply every time — see editorial/brand-style-guide.md)
- Line diagrams only. No 3D, no shadows, no photo-style icons.
- Colors: Graphite (#1B2430) boxes/text, Steel Blue (#4A7A96) for flows or
  emphasis, Slate Gray (#6B7684) for secondary/inactive elements. Background
  Off-white (#FAFAF8) or transparent.
- Font: Plex Mono throughout (labels, captions, legend).
- Border weight: 1-1.5px, consistent across all boxes in a diagram.

## Structure
- Multi-actor systems use horizontal or vertical swimlanes, one per actor
  (e.g. Manufacturer / Distributor / Pharmacy / Regulator).
- Data flows shown as directional arrows; label what's flowing (e.g. "EPCIS
  event," "batch ID"), not generic arrows.
- Every diagram gets a caption: "{publication-id}-F{NN}. {One-line description}."
  e.g. "RA-001-F01. System overview: actors and data flow."
- Include a legend if the diagram uses more than 2 distinct symbol types.

## Standard diagram types used across articles
1. System overview (actors + major components)
2. Data flow (what moves between systems, and when)
3. Sequence/process flow (time-ordered steps)
4. Component/deployment view (where things run — edge, cloud, on-prem)

Reuse these four types consistently rather than inventing new diagram
grammars per article.
