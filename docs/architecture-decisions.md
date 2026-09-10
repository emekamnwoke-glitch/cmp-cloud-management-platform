# Architecture Decision Records — Cloud Management Platform (CMP)

This file holds formal decision records for the architectural decisions that shaped Phase One ("Chargeback: Insight") of the CMP programme. It follows the same structure used for other decisions on this programme: Context, Decision, Rationale, Architecture, Implementation Phases, Risk & Mitigation, Success Criteria, Next Steps, and Sign-Off.

---

## ADR-001: Adopt a Pilot-First, Phased Deployment Strategy

**Date:** November 2025
**Status:** Accepted — closed
**Deciders:** Product Owner, Architecture Sponsor (Group CIO)

### Context

**Current State:** Aztec Bank Nigeria's on-premises OpenShift estate spans many namespaces and workloads across business units, with no existing tool for cost or governance visibility.

**The Problem:**
- Rolling the CMP cost model and reporting out across the entire estate at once would validate the approach against maximum real-world complexity — workload diversity, ownership ambiguity, telemetry gaps — with no fallback if something proved wrong.
- A full-estate rollout requires a much larger upfront infrastructure and effort commitment before any value is demonstrated, making it harder to secure sign-off for the investment.

**Why Now:** Phase One had a fixed, tight window (5 November – 15 December 2025) and needed to prove the cost model and build stakeholder trust before Phase Two's larger investment (HA infrastructure, full-estate rollout) could be authorised.

**Impact:** Selected critical workloads validate the approach at manageable risk; full-estate governance and chargeback wait until Phase Two, once the model is proven.

### Decision

**One-sentence statement:** Scope Phase One to a pilot set of critical, selected on-premises OpenShift workloads — validating cost modelling, manual ownership mapping, and showback reporting — before committing to full-estate rollout in Phase Two.

**In Scope:** OpenShift Integration Phase I (critical applications only), manual ownership mapping for the selected scope, showback reporting for that scope.

**Out of Scope:** Full-estate workload coverage, dynamic/automated ownership mapping, and chargeback enforcement — all deferred to Phase Two.

### Rationale

**Reason 1 — De-risked validation.** Cost model accuracy can be checked against a manageable blast radius before wider rollout, directly addressing the cost-model-inaccuracy risk (R2).

**Reason 2 — Evidence-based Phase Two sign-off.** Demonstrable Phase One value gives Finance and the Group CIO a concrete basis to authorise Phase Two's larger investment, rather than committing on faith.

**Reason 3 — Reduced adoption resistance.** Introducing the platform to a subset of stakeholders first, rather than the whole bank at once, keeps the change manageable (addresses risk R1).

**Alternatives Considered:**
- **Full-estate, big-bang rollout:** rejected — no fallback if the cost model or telemetry integration had systemic issues; validation would happen at maximum risk instead of on a contained pilot.
- **A random or representative workload sample instead of "critical applications":** rejected — critical applications are exactly where cost and governance visibility deliver the most immediate, demonstrable value to Finance and Infrastructure stakeholders.

### Architecture

See [architecture.md](architecture.md) §2 (the "Phased value delivery" principle) and §6 (the Phase One / Phase Two work-package split).

### Implementation Phases

**Scoping & Infrastructure** (5–10 Nov 2025) — kickoff, workshop, business case, infrastructure VM provisioning. *(Done)*

**Critical Application Integration** (11 Nov – 1 Dec 2025) — OpenShift Integration Phase I, ownership mapping, cost allocation, showback reporting. *(Done)*

**Validation & Close-Out** (2–15 Dec 2025) — walkthrough, automation workflow testing, close-out meeting. *(Done)*

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| Stakeholder adoption resistance (R1) | Pilot scope, early engagement, pre-go-live training | OrikiTech + Aztec Bank | Medium | High |
| Cost model inaccuracy discovered only after full rollout (R2) | Validated against pilot scope with Finance/EA review gates before Phase Two | OrikiTech | Medium | High |
| Operational overload from attempting full-estate rollout in a compressed window (R3) | Pilot scope keeps Phase One's footprint manageable within the 6-week window | OrikiTech + Aztec Bank | Medium | Medium |

### Success Criteria

- Telemetry validated against known cost baselines for the pilot scope — ✅ met
- Showback reports reviewed and accepted by Finance for the pilot scope — ✅ met
- EA architecture review sign-off obtained ahead of Phase Two — ✅ met
- Phase Two authorised on the strength of Phase One's demonstrated value — ✅ met (see [phase-one-closeout.md](../reports/phase-one-closeout.md))

### Next Steps

None — Phase One complete; Phase Two scoped in [phase-two-plan.md](phase-two-plan.md).

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Product Owner | Chukwuemeka Nwoke | November 2025 | Signed |
| Architecture Sponsor (Group CIO) | [Name] | 15 December 2025 | Signed |
| Finance Team | [Name] | 15 December 2025 | Signed |

---

## ADR-002: Sequence Showback Before Chargeback

**Date:** November 2025
**Status:** Accepted — closed
**Deciders:** Product Owner, Finance Team

### Context

**Current State:** No cost visibility mechanism existed for Aztec Bank Nigeria's OpenShift workloads. Introducing one for the first time meant introducing both visibility and, potentially, financial accountability at the same time.

**The Problem:**
- Activating chargeback (real financial consequence) simultaneously with a brand-new, unvalidated cost model risked disputes over accuracy.
- Stakeholders were more likely to resist a tool that immediately affected their budgets before they'd had a chance to trust its numbers.

**Why Now:** This had to be settled before Phase One's cost allocation configuration work began, since it determines whether Phase One's BI reporting activates chargeback or showback.

**Impact:** Finance gets accurate figures to validate before they're used for accountability; Application Owners see and can question their own numbers before being billed against them.

### Decision

**One-sentence statement:** Activate showback (read-only cost visibility, no financial consequence) in Phase One; defer chargeback (financial accountability) to a later phase, once the cost model is validated and trusted.

**In Scope:** Phase One's BI reporting and cost allocation configuration, delivered as showback only.

**Out of Scope:** Chargeback settlement mechanics and billing integration — full chargeback settlement remains on the future roadmap beyond Phase Two.

### Rationale

**Reason 1 — Trust before accountability.** Stakeholders get time to build literacy with the numbers before those numbers carry financial weight.

**Reason 2 — Model validation without financial risk.** Any cost model inaccuracies (R2) surface as a showback correction, not a disputed bill.

**Reason 3 — Matches the "Insight before enforcement" architecture principle** established in Phase A ([architecture.md](architecture.md) §2).

**Alternatives Considered:**
- **Activate chargeback immediately in Phase One:** rejected — no validation window for the cost model, and higher risk of adoption resistance from Application Owners facing unvalidated bills.
- **Skip showback and go straight to full chargeback in Phase Two:** rejected — delays any visibility value until Phase Two, weakening Phase One's business case for Finance sign-off.

### Architecture

See [architecture.md](architecture.md) §3 — value stream: "Telemetry capture → cost modelling → governed reporting → informed workload decisions → (Phase 2) enforced chargeback."

### Implementation Phases

Delivered within Phase One's "Install Chargeback Business Intelligence Reporting" and "Configure Cost Allocation & Chargeback" milestones (see [phase-one-plan.md](phase-one-plan.md)), with chargeback enforcement intentionally left inactive.

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| Cost model inaccuracy disputed if chargeback had been active from day one (R2) | Showback-only activation gives a no-consequence validation window with Finance and EA review gates | OrikiTech | Medium | High |
| Stakeholders perceive showback numbers as "not real" and disengage | Explicit communication that showback precedes chargeback by design, not by delay | Product Owner | Low | Medium |

### Success Criteria

- Showback reports reviewed and accepted by the Finance Team — ✅ met
- No chargeback-related billing disputes during Phase One (none possible, by design) — ✅ met
- Cost allocation configuration validated and ready to extend to chargeback in a future phase — ✅ met

### Next Steps

Revisit chargeback activation timing as part of the future roadmap beyond Phase Two (full chargeback settlement is out of current scope per [architecture.md](architecture.md) §6).

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Product Owner | Chukwuemeka Nwoke | November 2025 | Signed |
| Finance Team | [Name] | 1 December 2025 | Signed |

---

## ADR-003: Build RBAC into the CMP Portal from Day One

**Date:** November 2025
**Status:** Accepted — closed
**Deciders:** Product Owner, EA Team

### Context

**Current State:** The CMP Portal was being designed to serve four distinct stakeholder groups — Finance, Infrastructure, EA, and Application Owners — each with different data needs and, in a regulated banking environment, different authorization boundaries.

**The Problem:** Retrofitting access control after a portal is already in use is a common source of governance gaps — a group could see data it shouldn't have had access to during any period before access control was added.

**Why Now:** This had to be settled before the CMP Portal's first installation (the "Installation of CMP Services – Containers" milestone), since it shapes the portal's data model and views from the outset.

**Impact:** Each stakeholder group only ever sees what it's authorized to see, from the platform's very first deployment.

### Decision

**One-sentence statement:** Implement role-based access control in the CMP Portal as a day-one requirement, scoping Finance, Infrastructure, EA, and Application views separately from initial installation, rather than launching with open access and adding RBAC later.

**In Scope:** CMP Portal authentication/authorization and the four stakeholder-scoped views (EA Dashboard, Finance, Infrastructure, Application View).

**Out of Scope:** Fine-grained per-application or per-namespace access control beyond the four stakeholder-group views — not required for Phase One's critical-application pilot scope.

### Rationale

**Reason 1 — Governance by design, not retrofit.** Matches the "Governance by design" architecture principle ([architecture.md](architecture.md) §2) — RBAC and audit are day-one requirements, not later additions.

**Reason 2 — Regulatory expectation.** A regulated banking environment expects access boundaries to exist from the first day a system holds cost and workload data, not after an audit finding.

**Reason 3 — Avoids rework.** Building the portal's view layer around RBAC-scoped data from the start avoids re-architecting the presentation layer later.

**Alternatives Considered:**
- **Launch Phase One with a single shared view, add RBAC in Phase Two:** rejected — creates a governance gap during Phase One and requires reworking the portal's view layer later.
- **Rely on network-level segmentation instead of application-level RBAC:** rejected — doesn't give the fine-grained per-stakeholder-group view separation the four CMP Portal audiences need.

### Architecture

See [architecture.md](architecture.md) §4.2 — the CMP Portal component is explicitly responsible for the "RBAC-scoped presentation layer for Finance, Infrastructure, EA, and Application stakeholders."

### Implementation Phases

Delivered as part of Phase One's CMP Portal installation and validated through the "CMP Walkthrough / Team Validations" milestone ([phase-one-plan.md](phase-one-plan.md)).

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| Incorrect role-scoping exposes one stakeholder group's data to another | CMP Walkthrough / Team Validations milestone explicitly tested view separation before close-out | OrikiTech + Aztec Bank | Low | High |
| RBAC configuration adds setup time within Phase One's compressed window | Scoped to 4 stakeholder groups only (not fine-grained per application), keeping effort proportionate | OrikiTech | Low | Medium |

### Success Criteria

- Finance, Infrastructure, EA, and Application Owners each see only their scoped view — ✅ met
- No governance gaps identified at Phase One close-out — ✅ met
- RBAC required no retrofit or rework during Phase One — ✅ met

### Next Steps

Extend RBAC granularity if Phase Two's broader application coverage (OpenShift Integration Phase II) surfaces a need for finer-grained boundaries.

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Product Owner | Chukwuemeka Nwoke | November 2025 | Signed |
| EA Team | [Name] | 2 December 2025 | Signed |

---

## ADR-004: Scope Phase One and Two to On-Premises OpenShift Only

**Date:** November 2025
**Status:** Accepted — closed
**Deciders:** Architecture Sponsor (Group CIO), EA Team

### Context

**Current State:** Aztec Bank Nigeria's OpenShift estate is entirely on-premises; no hybrid or public-cloud workloads are in the bank's current infrastructure strategy.

**The Problem:** A cost and governance platform could, in principle, be designed for hybrid or multi-cloud from the outset — but doing so adds integration surface area the current on-premises-only estate doesn't need yet.

**Why Now:** This had to be settled before the Technology Architecture (Phase D) was finalized, since it determines whether the Telemetry Integration Layer needs to support multiple cloud-provider APIs or just OpenShift's own.

**Impact:** Telemetry ingestion, cost modelling, and governance workflows are built specifically for the on-premises OpenShift estate, keeping scope proportionate to the bank's actual infrastructure footprint.

### Decision

**One-sentence statement:** Scope the CMP platform strictly to on-premises OpenShift workloads for Phase One and Phase Two; explicitly defer hybrid/multi-cloud support to the future roadmap.

**In Scope:** On-premises OpenShift clusters, namespaces, workloads, pods, and services.

**Out of Scope:** Any hybrid or public-cloud workload integration — deferred to the future roadmap alongside full chargeback settlement and cross-bank rollout.

### Rationale

**Reason 1 — Matches actual infrastructure.** The bank's current estate is on-premises only, so building for hybrid/multi-cloud now would be speculative scope with no workload to validate it against.

**Reason 2 — "On-premises first" architecture principle.** Established explicitly in Phase A ([architecture.md](architecture.md) §2) as a guiding principle for this engagement.

**Reason 3 — Keeps Phase One and Two proportionate.** Avoids diverting Phase One's compressed timeline, or Phase Two's HA/automation scope, into cloud-provider integration work that isn't yet needed.

**Alternatives Considered:**
- **Design for hybrid/multi-cloud from Phase One:** rejected — no current workload to validate it against, and would extend Phase One's timeline for capability the bank doesn't yet need.
- **Add partial multi-cloud support in Phase Two:** rejected — Phase Two is already scoped to HA infrastructure and expanded OpenShift integration; adding cloud-provider scope would dilute that focus.

### Architecture

See [architecture.md](architecture.md) §2 (the "On-premises first" principle) and §6 (hybrid/multi-cloud explicitly named as deferred future roadmap).

### Implementation Phases

This is a scope boundary applied across both Phase One and Phase Two, not a standalone delivery phase of its own.

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| Bank infrastructure strategy shifts toward hybrid/multi-cloud before the future roadmap phase | Deferred scope is explicit and documented, not assumed; revisit if bank strategy changes | Architecture Sponsor (Group CIO) | Low | Medium |

### Success Criteria

- Phase One and Two integration work targets only on-premises OpenShift APIs — ✅ met
- No hybrid/multi-cloud integration effort spent during Phase One or planned for Phase Two — ✅ met

### Next Steps

Revisit if the bank's infrastructure strategy introduces hybrid/multi-cloud workloads ahead of the future roadmap phase.

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Architecture Sponsor (Group CIO) | [Name] | November 2025 | Signed |
| EA Team | [Name] | November 2025 | Signed |

---

## ADR-005: Invest in Automation Infrastructure During Phase One to Compress Phase Two

**Date:** November 2025
**Status:** Accepted — closed
**Deciders:** Product Owner, Infrastructure Team

### Context

**Current State:** Even at Phase One kickoff, it was clear that Phase Two's control and automation objectives would need a working automation foundation — HA migration and expanded OpenShift integration alone would already load Phase Two's timeline.

**The Problem:** Building an automation backend from scratch at the start of Phase Two would delay Phase Two's other, more time-boxed HA and integration work.

**Why Now:** This was decided as part of Phase One's initial scope, agreed at the 5 November 2025 kickoff workshop, rather than left as a Phase Two problem — the Phase One milestone tracker was built from the start to include automation backend setup and an initial workflow, not just core showback delivery.

**Impact:** Phase Two starts with a working automation backend and one validated workflow already in place, rather than building that foundation from zero under Phase Two's own timeline pressure.

### Decision

**One-sentence statement:** Use part of Phase One's scope to stand up the IT automation process backend, and implement and validate an initial automation workflow, ahead of Phase Two's four-workflow rollout.

**In Scope:** IT automation process backend setup; one infrastructure automation workflow extracted, implemented, and validated in Phase One.

**Out of Scope:** The remaining automation workflows themselves (×4, planned for Phase Two) — Phase One builds the foundation, not the full workflow catalogue.

### Rationale

**Reason 1 — Compresses Phase Two.** A working backend and one proven workflow reduce the marginal effort of Phase Two's four additional workflow extractions.

**Reason 2 — Validated under lower stakes.** Testing the automation approach against Phase One's smaller pilot scope, rather than Phase Two's full-estate HA rollout, catches problems earlier and cheaper.

**Reason 3 — Named explicitly as a deliberate decision** in Phase One's close-out lessons learned ([phase-one-closeout.md](../reports/phase-one-closeout.md) §6).

**Alternatives Considered:**
- **Defer all automation work to Phase Two:** rejected — front-loads Phase Two with both HA migration and an automation backend built from zero, risking the compressed Jan–May 2026 window.
- **Build the full automation workflow catalogue in Phase One:** rejected — Phase One's window and critical-application pilot scope don't justify building workflows for services not yet integrated.

### Architecture

See [architecture.md](architecture.md) §5 — "IT Automation Process Backend + Workflow Engine" listed as part of the Phase One technology stack.

### Implementation Phases

Delivered via Phase One's "Setup IT Automation Process Backend," "Infrastructure Automation Workflow Extraction," and "Infrastructure Automation Workflow Implementation" milestones ([phase-one-plan.md](phase-one-plan.md)), validated through Phase One's infrastructure test iterations.

### Risk & Mitigation

| Risk | Mitigation | Owner | Likelihood | Impact |
|---|---|---|---|---|
| Automation backend built in Phase One doesn't scale to Phase Two's four-workflow load | Backend architecture reviewed at Phase One's EA sign-off gate before Phase Two commitment | OrikiTech | Low | Medium |
| Time spent on automation in Phase One reduces capacity for core showback delivery | Automation work sequenced after core cost/showback milestones in the Phase One tracker | OrikiTech | Low | Medium |

### Success Criteria

- IT automation process backend operational and validated by Phase One close-out — ✅ met
- At least one automation workflow implemented and tested in Phase One — ✅ met
- Phase Two's automation workload builds on, rather than starts from, this foundation — pending Phase Two execution

### Next Steps

Extract and implement the remaining four automation workflows in Phase Two ([phase-two-plan.md](phase-two-plan.md), Milestones 9–10).

### Approvals & Sign-Off

| Role | Name | Date | Status |
|---|---|---|---|
| Product Owner | Chukwuemeka Nwoke | December 2025 | Signed |
| Infrastructure Team | [Name] | 10 December 2025 | Signed |
