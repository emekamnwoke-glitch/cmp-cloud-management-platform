# Phase One Close-Out Report — Chargeback: Insight

> **Portfolio Project** · OrikiTech Consultancy × Aztec Bank Nigeria
> **Close-Out Meeting:** 15 December 2025 · **Outcome:** ✅ Complete, Sign-Off Obtained

---

## 1. Summary

Phase One of the Cloud Management Platform (CMP) programme delivered cost visibility and showback reporting for a scoped set of Aztec Bank Nigeria's on-premises OpenShift workloads. All 18 planned milestones were completed on schedule, from stakeholder kickoff (5 November 2025) through close-out (15 December 2025). The phase met its exit criteria and unlocked Phase Two — Control & High Availability, targeted for January–May 2026.

---

## 2. Delivery Against Plan

| Workstream | Completion |
|---|---|
| Scoping & Kickoff | 100% ✅ |
| Infrastructure Setup | 100% ✅ |
| Application Mapping | 100% ✅ |
| OpenShift Integration | 100% ✅ |
| Cost & Chargeback | 100% ✅ |
| Automation Workflows | 100% ✅ |
| Reporting & Validation | 100% ✅ |
| **Overall Phase One** | **100% ✅** |

Full milestone-by-milestone detail is tracked in [docs/phase-one-plan.md](../docs/phase-one-plan.md).

---

## 3. What Was Delivered

- **Telemetry & Cost Modelling:** Infrastructure VM provisioned, CMP services installed, and real-time monitoring configured for the initial critical-application scope.
- **Ownership Mapping:** Business units validated and applications mapped to owners across the in-scope estate — performed manually, with dynamic mapping deferred to Phase Two.
- **Showback Reporting:** Chargeback BI reporting installed and cost allocation configured; showback (not chargeback) was activated, consistent with the deliberate [Showback Before Chargeback](../README.md#-showback-before-chargeback) product decision.
- **Automation Foundations:** IT automation process backend stood up, with initial workflow extraction and implementation completed and validated through infrastructure test iterations — designed to compress Phase Two's four-workflow rollout.
- **Governance:** RBAC-scoped CMP Portal delivered as a day-one requirement, giving Finance, Infrastructure, EA, and Application stakeholders separated views.
- **Stakeholder Enablement:** CMP walkthrough, team validations, and reporting presentation delivered ahead of close-out.

---

## 4. Exit Criteria — Verification

| Exit Criterion | Status |
|---|---|
| Telemetry validated against known cost baselines | ✅ Met |
| Ownership mapping confirmed by application owners | ✅ Met |
| Showback reports reviewed and accepted by Finance | ✅ Met |
| Automation workflows tested via validation iterations | ✅ Met |
| EA architecture review sign-off ahead of Phase Two | ✅ Met |

---

## 5. Risks Retired or Carried Forward

Per the [README Risk Register](../README.md#%EF%B8%8F-risk-register):

- **R1 (Stakeholder adoption resistance):** Substantially mitigated through the insight-first showback approach and early stakeholder engagement; no material adoption blockers reported at close-out.
- **R2 (Cost model inaccuracy):** Addressed via the structured validation phase with Finance and EA review gates; no material inaccuracies identified.
- **R5 (Telemetry data quality):** Retired as a Phase One exit criterion — telemetry validated successfully.
- **R3 (Operational overload) and R4 (OpenShift integration complexity):** Carried forward into Phase Two, where scope and integration surface area increase materially (see [docs/phase-two-plan.md](../docs/phase-two-plan.md)).

---

## 6. Lessons Learned

1. **Pilot-first reduced friction.** Scoping Phase One to critical applications only, rather than a full-estate rollout, allowed the cost model to be validated with a manageable blast radius before Phase Two investment was committed.
2. **Showback built trust ahead of accountability.** Introducing cost visibility without financial consequence gave stakeholders time to build literacy before chargeback enforcement — a sequencing decision worth repeating in future phases.
3. **Automation investment paid forward.** Time spent on the automation backend and initial workflow implementation in Phase One is expected to materially compress the ×4 workflow extraction planned for Phase Two.
4. **RBAC from day one avoided rework.** Building role-scoped access into the CMP Portal from the outset, rather than retrofitting it, avoided governance gaps during the regulated-banking rollout.

---

## 7. Sign-Off

Phase One was formally closed at the Close Out Meeting on 15 December 2025, with sign-off from OrikiTech Consultancy and Aztec Bank Nigeria stakeholders. Phase Two — Control & High Availability — was authorised to commence, targeting a 20 January 2026 rollout.

---

*This report is part of a portfolio representation of a real-world product delivery engagement. Client and partner names have been anonymised. All project data reflects actual delivery timelines and milestones.*
