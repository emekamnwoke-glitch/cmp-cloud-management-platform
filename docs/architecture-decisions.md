# Architecture Decision Records — Cloud Management Platform (CMP)

This file holds formal decision records for architecture and documentation decisions made on this repository. It follows the same structure used across the OrikiTech/Aztec Bank Nigeria and companion portfolio engagements: Context, Decision, Rationale, Architecture, Implementation Phases, Risk & Mitigation, Success Criteria, Next Steps, and Sign-Off.

---

## ADR-001: Use Mermaid C4 Diagrams for Architecture Documentation

**Date:** September 2026
**Status:** Accepted — render verified
**Deciders:** Product Owner, EA Team

### Context

**Current State:** `docs/architecture.md` §4.2 (Application Architecture) represented the CMP container view as ASCII box-and-arrow art embedded directly in the markdown. Separately, `assets/architecture-diagram.svg` — a real, purpose-built diagram — existed in the repository but was never referenced by any document; it was only visible as a filename in README's repository-structure tree.

**The Problem:**
- ASCII art has no formal architecture notation behind it — it's readable, but it isn't a recognized diagramming standard, which sits oddly next to a document that titles itself "CMP Architecture Document (TOGAF ADM)."
- The SVG asset represented real design effort that no reader would ever discover without browsing the raw file tree.
- Two diagrams of the same architecture existed in the repository (ASCII inline, SVG orphaned) with no stated relationship between them — an invitation for the two to drift out of sync.

**Why Now:** This was surfaced during an end-to-end documentation review of the repository (see the fixes for stale Phase Two status and broken cross-file anchors in the same review pass) and was the natural next fix alongside them.

**Impact:** Readers get one diagram, in a recognized notation, that renders inline and stays version-controlled as text alongside the prose that describes it — rather than two competing representations, one of which nobody could find.

### Decision

**One-sentence statement:** Replace the ASCII diagram in `docs/architecture.md` §4.2 with a Mermaid `C4Container` diagram, rendered natively by GitHub from a fenced code block.

**In Scope:** The Application Architecture diagram in §4.2.

**Out of Scope:** The disposition of `assets/architecture-diagram.svg` (delete vs. keep as a supplementary image) — tracked as an open item below, not decided by this ADR.

### Rationale

**Reason 1 — Native rendering, no asset to keep in sync.** A Mermaid code block lives as text in the same file as the prose describing it. There's no separate image file that can silently drift out of date the way `architecture-diagram.svg` already had.

**Reason 2 — Recognized notation.** C4's `Person` / `Container` / `System_Boundary` / `Rel` primitives are a standard architecture modeling vocabulary, consistent with what a document claiming TOGAF ADM rigor should actually use for its Information Systems Architecture view — an upgrade from decorative box-drawing characters.

**Reason 3 — Diffable and reviewable.** As plain text, the diagram participates in normal code review — a future change to the architecture shows up as a readable diff, not a re-exported binary image.

**Reason 4 — Consistency with the companion portfolio.** The sibling `unified-service-platform` repository already uses Mermaid (C4 context/container and sequence diagrams) successfully; using the same approach here keeps both portfolio pieces consistent in how they present architecture.

**Alternatives Considered:**
- **Keep the ASCII diagram:** rejected — no formal notation, and it's the weaker artifact next to a "TOGAF ADM" document title.
- **Reference `architecture-diagram.svg` directly as the primary diagram:** rejected as the *sole* diagram — a static image isn't diffable as text and doesn't match the Mermaid pattern already established in the companion repo. It may still be worth keeping as a supplementary polished export (see Next Steps).
- **PlantUML or another diagram-as-code tool:** rejected — GitHub does not natively render PlantUML in a markdown preview the way it renders Mermaid; using it would require an external rendering badge/service dependency that Mermaid doesn't need.

### Architecture

The diagram itself models the CMP container architecture already described in `docs/architecture.md` §4: OpenShift Clusters → Telemetry Integration Layer → (Cost Model Engine, Governance Engine, Reporting & Showback Engine) → CMP Portal, with Finance, Infrastructure, EA, and Application Owner personas as external actors of the Portal.

### Implementation Phases

**Phase 1 — Replace the diagram.** *(Done)* §4.2's ASCII art replaced with the `C4Container` Mermaid block.

**Phase 2 — Verify rendering.** *(Done)* Confirmed by screenshot on github.com — the diagram renders correctly, with all 4 person actors, both system boundaries, and all 5 containers laid out and labelled as designed.

**Phase 3 — Resolve the orphaned SVG.** *(Not started)* Decide whether `assets/architecture-diagram.svg` is deleted as fully superseded, or kept and explicitly embedded as a supplementary downloadable/print-quality image.

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| GitHub's pinned Mermaid version doesn't support the C4 diagram type and silently fails to render | **Resolved** — confirmed by screenshot; renders correctly | Product Owner | ~~Low–Medium~~ | ~~Medium~~ |
| A reader viewing this file outside github.com (local editor, different git host) sees raw Mermaid syntax instead of a diagram | Accepted — GitHub is the only currently-known consumption path for this portfolio | Product Owner | Medium | Low |
| The orphaned SVG stays in the repo indefinitely, causing confusion about which diagram is authoritative | Tracked explicitly as Phase 3 / Next Steps rather than left silent | Product Owner | Low | Low |

### Success Criteria

- The Mermaid diagram renders as an actual visual on github.com, not raw code text — ✅ met
- No unreferenced diagram assets remain undocumented in the repository once Phase 3 resolves
- `docs/architecture.md` §4.2 uses a named, recognized architecture notation rather than ad hoc ASCII art

### Next Steps

- Decide and execute the disposition of `assets/architecture-diagram.svg`

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Product Owner | Chukwuemeka Nwoke | September 2026 | Signed |
| EA Team | [Name] | — | Pending |
