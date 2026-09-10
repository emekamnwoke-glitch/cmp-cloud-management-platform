# Architecture Decision Records — Cloud Management Platform (CMP)

This file holds formal decision records for architecture and documentation decisions made during the CMP engagement. It follows the same structure used for other decisions on this programme: Context, Decision, Rationale, Architecture, Implementation Phases, Risk & Mitigation, Success Criteria, Next Steps, and Sign-Off.

---

## ADR-001: Use C4 Diagrams for Architecture Documentation

**Date:** December 2025
**Status:** Accepted — closed
**Deciders:** Product Owner, EA Team

### Context

**Current State:** An early working draft of `docs/architecture.md` §4.2 (Application Architecture) represented the CMP container view as ASCII box-and-arrow art. A separate diagram, `assets/architecture-diagram.svg`, had also been commissioned to illustrate the same architecture for stakeholder presentations, but was never incorporated into the architecture document itself.

**The Problem:**
- ASCII art has no formal architecture notation behind it — readable, but not a recognized diagramming standard, which sat oddly in a document following TOGAF ADM structure.
- Two representations of the same architecture existed — the inline ASCII version and the standalone SVG — with no stated relationship between them, risking the two drifting out of sync as the design evolved through Phase One.

**Why Now:** The architecture document needed to be finalized ahead of the EA Team's architecture review sign-off, one of Phase One's exit criteria (see [phase-one-plan.md](phase-one-plan.md)). A single, authoritative diagram was needed before that review, not two competing ones.

**Impact:** Reviewers and future readers get one diagram, in a recognized notation, embedded directly alongside the architecture narrative it describes — rather than two representations that could quietly disagree with each other.

### Decision

**One-sentence statement:** Represent the Application Architecture in `docs/architecture.md` §4.2 as a C4 container diagram, and retire the standalone SVG graphic in favour of it.

**In Scope:** The Application Architecture diagram in §4.2, and the disposition of `assets/architecture-diagram.svg`.

**Out of Scope:** Diagramming notation for other sections of the architecture document (data models, deployment topology) — this decision covers the application/container view only.

### Rationale

**Reason 1 — Recognized notation.** C4's `Person` / `Container` / `System_Boundary` / `Rel` vocabulary is a standard architecture modeling notation, consistent with the rigor a TOGAF ADM-structured document should apply to its Information Systems Architecture view — an upgrade from box-drawing characters.

**Reason 2 — One source of truth.** Embedding the diagram directly in the architecture document, rather than maintaining it as a separate presentation asset, removes the risk of the diagram and the narrative describing it drifting apart as the design changes.

**Reason 3 — Reviewable alongside the text.** As part of the same document, the diagram is reviewed by the EA Team in the same pass as the narrative around it, rather than as a separate artifact that could be reviewed — or missed — independently.

**Alternatives Considered:**
- **Keep the ASCII diagram:** rejected — no formal notation, and the weaker artifact to bring to an EA architecture review.
- **Keep the SVG as the primary diagram, referenced from the document:** rejected — it would still be a separate asset maintained outside the document it illustrates, the same drift risk the ASCII/SVG split already created.
- **Commission a new standalone diagram in another tool:** rejected — adds a further external asset and review dependency ahead of the Phase One close-out deadline, without solving the underlying single-source-of-truth problem.

### Architecture

The diagram models the CMP container architecture described in `docs/architecture.md` §4: OpenShift Clusters → Telemetry Integration Layer → (Cost Model Engine, Governance Engine, Reporting & Showback Engine) → CMP Portal, with Finance, Infrastructure, EA, and Application Owner personas as external actors of the Portal.

### Implementation Phases

**Phase 1 — Replace the diagram.** *(Done)* §4.2's ASCII art replaced with a C4 container diagram embedded in the document.

**Phase 2 — Verify rendering ahead of EA review.** *(Done)* Diagram confirmed rendering correctly ahead of the Phase One architecture review sign-off.

**Phase 3 — Retire the standalone SVG.** *(Done)* `assets/architecture-diagram.svg` removed from the repository, fully superseded by the embedded diagram.

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| Diagramming tool doesn't render correctly wherever the document is reviewed | Verified rendering ahead of the EA review meeting rather than assuming it | Product Owner | Low | Medium |
| Retiring the SVG loses a presentation-quality asset stakeholders had already seen | Accepted — the embedded diagram now serves the same purpose as part of the reviewed document, and stakeholder walkthroughs reference the document directly | Product Owner | Low | Low |

### Success Criteria

- The diagram renders correctly wherever the architecture document is reviewed — ✅ met
- No unreferenced or duplicate diagram assets remain in the repository — ✅ met, SVG retired
- `docs/architecture.md` §4.2 uses a named, recognized architecture notation rather than ad hoc ASCII art — ✅ met

### Next Steps

None — decision closed ahead of Phase One close-out.

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Product Owner | Chukwuemeka Nwoke | December 2025 | Signed |
| EA Team | [Name] | 15 December 2025 | Signed |
