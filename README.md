# Cloud Management Platform (CMP) — Phased Project Plan

> **Portfolio Project** · OrikiTech Consultancy × Aztec Bank Nigeria · 2025–2026

---

## 📋 Project Overview

| Attribute | Detail |
|---|---|
| **Project** | Cloud Management Platform (CMP) — Production Rollout |
| **Client** | Aztec Bank Nigeria |
| **Delivery Partner** | OrikiTech Consultancy |
| **Product Owner** | Chukwuemeka Nwoke, OrikiTech Consultancy |
| **Project Manager** | Project Manager, Aztec Bank Nigeria (Internal) |
| **Architecture Sponsor** | Group CIO, Aztec Bank Nigeria |
| **Version** | v1.0 |
| **Engagement Start Date** | November 2025 |
| **Document Snapshot Date** | 15 December 2025 (Phase One close-out) |

> **Snapshot note:** Phase Two was authorised to commence but not yet started as of the snapshot date above. Dates and percentages below are fixed to that snapshot — they are not a live tracker.

---

## 🎯 Product Vision

The CMP initiative was commissioned to deliver **end-to-end cost transparency, governance accountability, and performance visibility** across Aztec Bank Nigeria's on-premises OpenShift workloads.

As Product Owner, I led OrikiTech's consultancy engagement — translating business requirements into a structured, phased delivery roadmap, managing cross-functional stakeholder alignment between OrikiTech engineers and Aztec Bank Nigeria's infrastructure and finance teams, and ensuring each phase delivered measurable value before the next was unlocked.

> *"Enable teams to see, understand, and optimise their workloads — improving cost transparency, operational efficiency, and governance adherence — through a governed, insight-led Cloud Management Platform."*

---

## 🏗️ Product Scope

```
✅ In Scope (Phase 1 & 2)          🔮 Future Roadmap
─────────────────────────────      ─────────────────────────────
On-premises OpenShift workloads    Hybrid / multi-cloud support
Cost attribution & modelling       Full chargeback settlement
Governance & compliance workflows  AI-driven optimisation (AAEPM)
Showback reporting                 Cross-bank platform rollout
Chargeback – Insight (Phase 1)
Control & HA (Phase 2)
```

---

## 📐 Architecture at a Glance

```
┌──────────────────────────────────────────────────────┐
│            ON-PREMISES OPENSHIFT CLUSTERS            │
│        (Namespaces / Workloads / Pods / Services)    │
└──────────────────────┬───────────────────────────────┘
                       │  Telemetry & Metrics (API)
                       ▼
┌──────────────────────────────────────────────────────┐
│             TELEMETRY INTEGRATION LAYER              │
│       (Ingestion · Normalisation · Enrichment)       │
└──────────────────────┬───────────────────────────────┘
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
   ┌────────────┐ ┌──────────┐ ┌──────────────┐
   │ Cost Model │ │Governance│ │  Reporting & │
   │   Engine   │ │  Engine  │ │ Showback Eng.│
   └─────┬──────┘ └────┬─────┘ └──────┬───────┘
         └─────────────┼──────────────┘
                       ▼
┌──────────────────────────────────────────────────────┐
│                  CMP PORTAL (RBAC)                   │
│  EA Dashboard · Finance · Infrastructure · App View  │
└──────────────────────────────────────────────────────┘
```

---

## 🗺️ Phased Delivery Roadmap

```
Q4 2025                              Q1–Q2 2026
──────────────────────────────────────────────────────────────►

│◄─────── PHASE ONE ──────────►│◄────────── PHASE TWO ────────►│
│  Chargeback – INSIGHT         │  Control & High Availability  │
│  Nov 2025 → Dec 2025          │  Jan 2026 → May 2026          │
│                               │                               │
│  ✓ Scoping & Stakeholders     │  ○ CMP HA Infrastructure      │
│  ✓ Infra Virtual Machine      │  ○ Phase 1 Data Migration     │
│  ✓ Business Case Validation   │  ○ OpenShift Integration II   │
│  ✓ Ownership Mapping          │  ○ Central Mgmt & Control     │
│  ✓ Chargeback Reporting       │  ○ Dynamic Mapping (OpenShift)│
│  ✓ Monitoring – Select Nodes  │  ○ BI Reporting II            │
│  ✓ OpenShift Integration I    │  ○ Automation Workflow Impl.  │
│  ✓ Cost Allocation Config     │  ○ Infrastructure Validations │
│  ✓ IT Automation Backend      │  ○ Training / Walkthrough     │
│  ✓ Automation Workflow Impl.  │  ○ Close Out & Sign Off       │
│  ✓ Infra Validations & Tests  │                               │
│  ✓ CMP Walkthrough / Training │                               │
│  ✓ Close Out Meeting          │                               │
```

---

## 📊 Phase One — Milestone Tracker

> **Rollout Target:** 5th November 2025 · **Phase:** Chargeback – INSIGHT

| # | Milestone Deliverable | Resource | Target Date | Status |
|---|---|---|---|---|
| 1 | Project Kickoff with Stakeholders | OrikiTech + Aztec Bank | 05/11/2025 | ✅ |
| 2 | Project Workshop, Business Case & First Phase App | OrikiTech + Aztec Bank | 05/11/2025 | ✅ |
| 3 | Provision Infrastructure VM & Firewall Permission | OrikiTech + Aztec Bank | 10/11/2025 | ✅ |
| 4 | Collect & Validate Business Units | OrikiTech + Aztec Bank | 11/11/2025 | ✅ |
| 5 | Collate Application List & Ownership Mapping | OrikiTech + Aztec Bank | 13/11/2025 | ✅ |
| 6 | Installation of CMP Services – Containers | OrikiTech | 14/11/2025 | ✅ |
| 7 | Install Chargeback Business Intelligence Reporting | OrikiTech | 18/11/2025 | ✅ |
| 8 | Configure Real-Time Monitoring – Workload | OrikiTech + Aztec Bank | 21/11/2025 | ✅ |
| 9 | OpenShift Integration Phase I – Critical Applications | OrikiTech + Aztec Bank | 24/11/2025 | ✅ |
| 10 | Service Tagging & Mapping Phase I | OrikiTech + Aztec Bank | 27/11/2025 | ✅ |
| 11 | Configure Cost Allocation & Chargeback | OrikiTech + Aztec Bank | 01/12/2025 | ✅ |
| 12 | CMP Walkthrough / Team Validations | OrikiTech + Aztec Bank | 02/12/2025 | ✅ |
| 13 | CMP Reporting / Presentation | OrikiTech | 04/12/2025 | ✅ |
| 14 | Setup IT Automation Process Backend | OrikiTech | 06/12/2025 | ✅ |
| 15 | Infrastructure Automation Workflow Extraction | OrikiTech + Aztec Bank | 08/12/2025 | ✅ |
| 16 | Infrastructure Automation Workflow Implementation | OrikiTech + Aztec Bank | 10/12/2025 | ✅ |
| 17 | Infrastructure Validations & Test Iterations | OrikiTech + Aztec Bank | 12/12/2025 | ✅ |
| 18 | Close Out Meeting – Phase One | OrikiTech + Aztec Bank | 15/12/2025 | ✅ |

---

## 📊 Phase Two — Milestone Tracker

> **Rollout Target:** 20th January 2026 · **Phase:** Control

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

## 📈 Delivery Progress

### Phase One Completion (As of Nov 2025)
```
Scoping & Kickoff       ████████████████████  100%
Infrastructure Setup    ████████████████████  100%
Application Mapping     ████████████████████  100%
OpenShift Integration   ████████████████████  100%
Cost & Chargeback       ████████████████████  100%
Automation Workflows    ████████████████████  100%
Reporting & Validation  ████████████████████  100%

Overall Phase One       ████████████████████  100% ✅
```

### Phase Two Progress (Target: May 2026)
```
Infrastructure HA       ░░░░░░░░░░░░░░░░░░░░   0%  🔄 In Planning
Data Migration          ░░░░░░░░░░░░░░░░░░░░   0%  🔄 In Planning
OpenShift Integration   ░░░░░░░░░░░░░░░░░░░░   0%  🔄 In Planning
Automation (×4)         ░░░░░░░░░░░░░░░░░░░░   0%  🔄 In Planning
Reporting & Sign-Off    ░░░░░░░░░░░░░░░░░░░░   0%  🔄 In Planning

Overall Phase Two       ░░░░░░░░░░░░░░░░░░░░   0%  🔄 Commences Jan 2026
```

---

## 🤝 Stakeholder Map

```
                    ┌─────────────────────┐
                    │  Group CIO          │  ← Architecture Sponsor
                    │  Aztec Bank Nigeria │
                    └──────────┬──────────┘
                               │
           ┌───────────────────┼────────────────────┐
           ▼                   ▼                    ▼
    ┌──────────────┐   ┌──────────────┐   ┌──────────────────┐
    │  EA Team     │   │Infrastructure│   │  Finance Team    │
    │  Aztec Bank  │   │  Aztec Bank  │   │  Aztec Bank      │
    └──────────────┘   └──────────────┘   └──────────────────┘

                    ┌─────────────────────┐
                    │  Chukwuemeka Nwoke  │  ← Product Owner
                    │  OrikiTech          │
                    └──────────┬──────────┘
                               │
           ┌───────────────────┼────────────────────┐
           ▼                   ▼                    ▼
    ┌──────────────┐   ┌──────────────┐   ┌──────────────────┐
    │  Engineering │   │  Reporting & │   │  Infrastructure  │
    │  OrikiTech   │   │  Analytics   │   │  Delivery        │
    └──────────────┘   └──────────────┘   └──────────────────┘
```

---

## 🔑 Key Product Decisions & Learnings

### ✅ Pilot-First Deployment Strategy
A phased rollout was adopted over a big-bang deployment. Phase One targeted chargeback and insight reporting for selected workloads only, allowing the cost model to be validated before full production commitment. This reduced adoption resistance and created an evidence base for Phase Two investment sign-off.

### ✅ Showback Before Chargeback
Teams were introduced to cost visibility through showback reporting (read-only, no financial consequence) before full chargeback was activated. This was a deliberate product decision to build trust and literacy before accountability.

### ✅ Automation as a Force Multiplier
A significant portion of Phase One effort was invested in infrastructure automation workflows and IT automation backend setup. This upfront investment was designed to compress Phase Two delivery timelines by eliminating manual repetition across the 4× automation workflow extractions planned.

### ✅ RBAC as a Day-One Requirement
Role-based access control was built into the CMP portal from the outset rather than retrofitted. This enabled different stakeholder groups (Finance, Infrastructure, EA, Application Support) to access only the dashboards and data relevant to them — a critical governance requirement for a regulated banking environment.

---

## 🛡️ Risk Register

| # | Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| R1 | Stakeholder adoption resistance | Medium | High | Insight-first showback; early engagement; pre-go-live training |
| R2 | Cost model inaccuracy | Medium | High | Structured validation phase with Finance and EA review gates |
| R3 | Operational overload during rollout | Medium | Medium | Phased delivery; dedicated support window per milestone |
| R4 | OpenShift integration complexity | Low | High | Architecture review in Phase One; sign-off gate before Phase Two |
| R5 | Telemetry data quality | Low | High | Telemetry validation as Phase One exit criterion |

---

## 📚 Technology Stack

| Layer | Technology |
|---|---|
| Compute Platform | On-premises OpenShift Clusters |
| CI/CD | Existing enterprise CI/CD pipeline |
| Portal | Web application with RBAC |
| Monitoring | OpenShift monitoring stack + custom ingestors |
| Security | RBAC + TLS in transit |
| Audit | Centralised audit trail with log retention policy |
| Reporting | BI Reporting engine (Chargeback + Showback) |
| Automation | IT Automation Process Backend + Workflow Engine |

---

## 📁 Repository Structure

```
📦 cmp-cloud-management-platform
 ┣ 📄 README.md                       ← You are here
 ┣ 📁 docs/
 ┃  ┣ 📄 architecture.md              ← TOGAF ADM architecture document
 ┃  ┣ 📄 architecture-decisions.md    ← ADRs for architecture & documentation decisions
 ┃  ┣ 📄 phase-one-plan.md            ← Phase One detailed plan
 ┃  ┗ 📄 phase-two-plan.md            ← Phase Two detailed plan
 ┗ 📁 reports/
    ┗ 📄 phase-one-closeout.md        ← Phase One closeout summary
```

**Explore further:** [Architecture Document](docs/architecture.md) · [Architecture Decision Records](docs/architecture-decisions.md) · [Phase One Plan](docs/phase-one-plan.md) · [Phase Two Plan](docs/phase-two-plan.md) · [Phase One Close-Out Report](reports/phase-one-closeout.md)

---

## 👤 About the Product Owner

**Chukwuemeka Nwoke** — Product Owner, OrikiTech Consultancy

Responsible for end-to-end product ownership of the CMP programme: defining the product vision, managing the phased roadmap, aligning cross-functional stakeholders across OrikiTech and Aztec Bank Nigeria, and ensuring each phase delivered measurable business value before progression.

---

*This repository is a portfolio representation of a real-world product delivery engagement. Client and partner names have been anonymised. All project data reflects actual delivery timelines and milestones.*

---

![Phase One](https://img.shields.io/badge/Phase%20One-Complete-brightgreen)
![Phase Two](https://img.shields.io/badge/Phase%20Two-Planned-lightgrey)
![Stack](https://img.shields.io/badge/Stack-OpenShift%20%7C%20CMP%20%7C%20BI-orange)
![Role](https://img.shields.io/badge/Role-Product%20Owner-purple)
