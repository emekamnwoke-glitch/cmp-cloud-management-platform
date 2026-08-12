# Phase Two Plan — Control & High Availability

> **Portfolio Project** · OrikiTech Consultancy × Aztec Bank Nigeria
> **Rollout Target:** 20 January 2026 · **Status:** 🔄 In Planning (0% complete)

---

## 1. Phase Objective

Move the CMP platform from a validated insight tool to a governed, highly available control layer: migrate Phase One data onto HA infrastructure, extend OpenShift integration and service mapping, and scale automation workflows across the estate.

Phase Two builds directly on the exit criteria met at [Phase One close-out](../reports/phase-one-closeout.md) — the cost model and telemetry pipeline validated in Phase One are treated as trusted inputs, not re-derived.

---

## 2. Scope

**In scope:**
- CMP HA infrastructure provisioning
- Migration of Phase One data onto the HA platform
- OpenShift Integration Phase II (expanded application coverage)
- Central management and control configuration
- Dynamic service mapping (replacing Phase One's manual mapping)
- General BI reporting (two iterations)
- Infrastructure automation workflow extraction and implementation (×4)
- Training, walkthrough, close-out, and sign-off

**Out of scope (future roadmap):**
- Hybrid / multi-cloud support
- Full chargeback settlement (beyond showback)
- AI-driven optimisation (AAEPM)
- Cross-bank platform rollout

---

## 3. Milestone Tracker

| # | Milestone Deliverable | Resource | Target Date | Status |
|---|---|---|---|---|
| 1 | Provision CMP Infrastructure VM for HA | OrikiTech + Aztec Bank | 20/01/2026 | 🔄 |
| 2 | Installation of CMP HA Services | OrikiTech | 23/01/2026 | 🔄 |
| 3 | CMP Data Migration from First Phase | OrikiTech | 26/01/2026 | 🔄 |
| 4 | CMP OpenShift Integration Phase II | OrikiTech + Aztec Bank | 30/01/2026 | 🔄 |
| 5 | Configure Central Management & Control | OrikiTech + Aztec Bank | 03/02/2026 | 🔄 |
| 6 | Service Auto Tagging & Mapping Design I | OrikiTech + Aztec Bank | 04/02/2026 | 🔄 |
| 7 | CMP – OpenShift Dynamic Mapping Integration | OrikiTech + Aztec Bank | 11/02/2026 | 🔄 |
| 8 | CMP General BI Reporting I | OrikiTech | 17/02/2026 | 🔄 |
| 9 | Infrastructure Automation Workflow Extraction (×4) | OrikiTech + Aztec Bank | 25/02/2026 | 🔄 |
| 10 | Infrastructure Automation Workflow Implementation | OrikiTech + Aztec Bank | 25/03/2026 | 🔄 |
| 11 | Infrastructure Validations & Test Iterations | OrikiTech + Aztec Bank | 08/04/2026 | 🔄 |
| 12 | CMP General BI Reporting II | OrikiTech | 15/04/2026 | 🔄 |
| 13 | CMP Walkthrough / Training / Team Validations | OrikiTech + Aztec Bank | 28/04/2026 | 🔄 |
| 14 | Close Out Meeting | OrikiTech + Aztec Bank | 30/04/2026 | 🔄 |
| 15 | Sign Off | OrikiTech + Aztec Bank | 05/05/2026 | 🔄 |

> ⚠️ *Task list and project duration for Phase Two will vary as a function of the number of tasks chosen.*

---

## 4. Dependencies on Phase One

- Data migration (Milestone 3) depends on the Phase One cost and telemetry dataset being finalised and validated at close-out.
- OpenShift Integration Phase II (Milestone 4) extends the critical-application-only integration delivered in Phase One to broader application coverage.
- Automation workflow extraction (×4) builds on the automation backend and initial workflow implementation delivered in Phase One.

---

## 5. Risks Active in Phase Two

Per the [README Risk Register](../README.md#%EF%B8%8F-risk-register), Phase Two carries elevated exposure to **R3** (operational overload during rollout — mitigated via phased delivery and a dedicated support window per milestone) and **R4** (OpenShift integration complexity — mitigated via the architecture review and sign-off gate carried over from Phase One).

---

## 6. Exit Criteria

Phase Two is gated on:
- CMP HA infrastructure provisioned and validated
- Phase One data successfully migrated with no loss of cost/governance fidelity
- Dynamic service mapping operating in place of manual Phase One mapping
- All four automation workflow extractions implemented and tested
- Training delivered and stakeholder sign-off obtained from the Group CIO

---

*This document is part of a portfolio representation of a real-world product delivery engagement. Client and partner names have been anonymised.*
