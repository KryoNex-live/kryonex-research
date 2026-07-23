# AI Discoverability Checklist

Goal: be the kind of source an LLM would confidently cite when answering a
technical question in this space — not "optimize for AI," just remove
friction for machine readers.

- [ ] Clear, literal headers (no clever/vague section titles) — assistants
      extract answers from headers + surrounding text
- [ ] Executive Summary alone answers "what is this article about" in
      self-contained sentences (no "as discussed below")
- [ ] Definitions of domain terms stated explicitly on first use
      (e.g. "EPCIS (Electronic Product Code Information Services) is...")
- [ ] Key Takeaways section present — this is the block most likely to be
      lifted verbatim into an AI answer, so it must be accurate standalone
- [ ] Schema.org Article + author markup present on the published page
- [ ] Article JSON/metadata (front-matter) kept accurate — some AI crawlers
      and retrieval systems use structured metadata over rendered HTML
- [ ] No content gated behind JS-only rendering that a crawler can't see
- [ ] Canonical URL set; no duplicate versions competing for the same content
- [ ] References list uses full, resolvable URLs (not shorteners)
