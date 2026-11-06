# VELOOP Rewards — Product Analytics & Data Management Blueprint
## Data Analyst Internship — Task 01 (Milestone: Days 1 to 6)

[![Project Status: Days 1–6 Complete](https://img.shields.io/badge/Sprint-Days%201--6%20Complete-success)](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/01_EXECUTIVE_SUMMARY_DAY_1_TO_6.md)
[![Data Policy: Fictional/Simulated](https://img.shields.io/badge/Data%20Authenticity-Simulated%20Dataset-amber)](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/02_DAYS_1_2_PRODUCT_AND_SOURCE_AUDIT.md)
[![Spec Fields](https://img.shields.io/badge/User%20Spec%20Fields-30%20Attributes-blue)](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/04_DAYS_5_6_USER_ANALYTICS_SPEC.md)

---

### Mandatory Data Authenticity Declaration (Section 2 & 34)
> [!IMPORTANT]
> **VELOOP is a real product under development, but the dataset supplied for this assignment is fictional/simulated.**
> All empirical metrics, user numbers, behavioral distributions, event counts, and task stats are derived exclusively from the provided simulated datasets (`VELoop_Rewards_Data_01.xlsx` and `VELOOP_Simulated_User_Behavior_1000.xlsx`).  
> In compliance with strict company integrity standards:
> - Simulated data is **never** presented as actual VELOOP users, actual earnings, actual withdrawals, actual revenue, actual retention, or actual company statistics.
> - Assumptions are **never** silently converted into facts.
> - All items are classified as **Confirmed**, **Proposed**, or **To Be Verified**.

---

## 1. Quick Access & Interactive Portal Link

You can explore the entire project blueprint interactively via the built-in portal:

- **Interactive Local Web Portal:** Open [`index.html`](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/index.html) in any browser, or run the local server:
  ```powershell
  python scripts/serve_portal.py
  # Access at http://localhost:8080/index.html
  ```
- **Primary Milestone Documentation:**
  1. [`docs/01_EXECUTIVE_SUMMARY_DAY_1_TO_6.md`](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/01_EXECUTIVE_SUMMARY_DAY_1_TO_6.md) — 2–4 Page Milestone Executive Summary
  2. [`docs/02_DAYS_1_2_PRODUCT_AND_SOURCE_AUDIT.md`](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/02_DAYS_1_2_PRODUCT_AND_SOURCE_AUDIT.md) — Days 1–2: Product Architecture & Evidence Registers
  3. [`docs/03_DAYS_3_4_DATA_READINESS_AUDIT.md`](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/03_DAYS_3_4_DATA_READINESS_AUDIT.md) — Days 3–4: Work Package A, Coverage Matrix & 10 Analytics Gaps
  4. [`docs/04_DAYS_5_6_USER_ANALYTICS_SPEC.md`](file:///c:/Users/yyogi/OneDrive/Desktop/yogitha/data%20analytics/docs/04_DAYS_5_6_USER_ANALYTICS_SPEC.md) — Days 5–6: Work Package B, Identity Standards & User Analytics Spec

---

## 2. 22–25 Day Schedule Alignment: Days 1–6 Scope

| Sprint Phase | Recommended Timeline | Deliverables & Work Packages Covered | Status |
| :--- | :--- | :--- | :--- |
| **Days 1–2** | Days 1–2 | Product Documentation Review; Source Register; Confirmed/Proposed/To-Be-Verified Classification; Work Package S (Assumption Register) | **Completed** |
| **Days 3–4** | Days 3–4 | Work Package A: Product Data Readiness Audit; User Action Flow Decomposition; The Analytical Triad; Data Coverage Matrix; 10 Critical Analytics Gaps | **Completed** |
| **Days 5–6** | Days 5–6 | Work Package B: User & Account Analytics Specification; 4 Core Identity Standards (`user_id`, `event_id`, `session_id`, `transaction_id`); 7-State User Lifecycle Machine; 30-Field User Specification Table | **Completed** |
| *Future* | Days 7–8 | Work Package C: Earning & Reward Analytics Specification | *Upcoming* |
| *Future* | Days 9–10 | Work Package D: Wallet & Withdrawal Analytics Specification | *Upcoming* |
| *Future* | Day 11 | Work Package E: Referral & Engagement Analytics | *Upcoming* |
| *Future* | Days 12–14 | Work Package F: Production Event Tracking Plan | *Upcoming* |

---

## 3. Project Directory Structure

```
c:\Users\yyogi\OneDrive\Desktop\yogitha\data analytics/
│
├── README.md                                  # Complete Project Overview & Milestone Index
├── index.html                                 # Interactive Web Documentation & Analytics Portal
├── requirements.txt                           # Python Dependencies (pandas, openpyxl)
├── .gitignore                                 # Git Ignore Rules
│
├── data/
│   ├── raw/                                   # Downloaded Official Synthetic Datasets
│   │   ├── VELoop_Rewards_Data_01.xlsx        # 1,000 clean user profiles & messy audit sheet
│   │   └── VELOOP_Simulated_User_Behavior_1000.xlsx # 7,913 sessions, 35,704 events, 9,846 tasks
│   └── exports/                               # Clean Machine-Readable CSV Deliverables
│       ├── source_and_verification_register.csv # 20 Product facts classified
│       ├── assumption_register.csv            # 15 Technical unknowns with owners
│       ├── data_coverage_matrix.csv           # 23 Core measurable events
│       ├── top_10_analytics_gaps.csv          # 10 Pre-production engineering blockers
│       └── user_analytics_specification.csv   # 30 User analytics fields
│
├── docs/                                      # Structured Analytical Reports
│   ├── 01_EXECUTIVE_SUMMARY_DAY_1_TO_6.md     # Deliverable 01 (Executive Summary)
│   ├── 02_DAYS_1_2_PRODUCT_AND_SOURCE_AUDIT.md# Days 1–2 Full Audit Report
│   ├── 03_DAYS_3_4_DATA_READINESS_AUDIT.md    # Days 3–4 Work Package A Report
│   ├── 04_DAYS_5_6_USER_ANALYTICS_SPEC.md     # Days 5–6 Work Package B Specification
│   └── registers/
│       ├── source_verification_register.md    # Section 6 Source Register Table
│       └── assumption_verification_register.md# Section 25 Work Package S Register
│
├── specs/                                     # Machine-Readable JSON Schemas
│   ├── source_and_verification_register.json
│   ├── assumption_register.json
│   ├── event_data_coverage_matrix.json
│   ├── top_10_analytics_gaps.json
│   ├── user_analytics_spec.json
│   ├── user_lifecycle_state_machine.json
│   └── dataset_profile_summary.json
│
└── scripts/                                   # Analytics Tools & Verification Scripts
    ├── profile_data.py                        # Automated data profiling script
    ├── export_registers_to_csv.py             # Generates all CSV & JSON exports
    └── serve_portal.py                        # Local HTTP web server runner
```

---

## 4. Key Deliverables Summary (Days 1–6)

### Days 1–2: Evidence Discipline & Source Audits
- **Source & Verification Register:** 20 critical product claims logged with exact sources, verified types (Official/Simulated/Internal), and status (`Confirmed`, `Proposed`, `To Be Verified`).
- **Assumption & Verification Register (Work Package S):** 15 technical uncertainties (e.g. backend event streaming, double-entry ledgers, session timeouts, S2S ad postbacks) classified with explicit operational risk ratings and engineering owners.

### Days 3–4: Data Readiness Audit & Analytics Gaps (Work Package A)
- **Product Area Mapping:** All 17 ecosystem modules mapped from Authentication and Onboarding to Gamification, Referrals, Exchange, and Withdrawals.
- **The Analytical Triad:** Clear architectural separation between client **User Events**, server **System Events**, and legally binding **Business Outcomes**.
- **Data Coverage Matrix:** 23 core platform events specified with triggers, data requirements, sources, and priorities.
- **Top 10 Critical Analytics Gaps:** Deep dive into 10 high-impact vulnerabilities affecting future production reporting, including:
  1. *Total absence of withdrawal events in telemetry.*
  2. *Lack of client-side `event_id` idempotency headers for retry deduplication.*
  3. *Disconnect between auth transactions and the feature event stream.*
  4. *Zero successful conversions in Exchange Center across 1,690 events.*
  5. *Unverified client-side ad view reward crediting.*
  6. *Single mutable progression balance column lacking an immutable double-entry ledger.*
  7. *Inconsistent referral funnel hurdles.*
  8. *Lack of client heartbeat for reliable session boundaries.*
  9. *Unsanitized PII in analytical workspaces.*
  10. *Ambiguous UTC vs solar midnight streak evaluation windows.*

### Days 5–6: User & Account Analytics Specification (Work Package B)
- **Four Foundational Identifiers (B1):**
  1. `user_id`: Stable, immutable anchor for user entity resolution across devices.
  2. `event_id`: Cryptographic UUIDv4 idempotency key for network retry deduplication.
  3. `session_id`: Alphanumeric token renewed after 30-min sliding inactivity cutoff.
  4. `transaction_id`: Append-only reference for double-entry financial auditability.
- **User Lifecycle State Machine:** 7-state audited lifecycle (`Created`, `Pending Verification`, `Active`, `Inactive/Dormant`, `Churned`, `Suspended`, `Deleted/Anonymized`).
- **User Analytics Specification Table (B2):** 30 production fields specified with data types, requirements, sources, validation rules, and privacy protections.

---

## 5. Non-Negotiable Integrity Rules Compliance Checklist

| Rule # | Integrity Mandate | Project Compliance Evidence |
| :---: | :--- | :--- |
| **1** | Never fabricate production data. | Explicitly acknowledged; all metrics traced to synthetic sample. |
| **2** | Never represent simulated data as actual VELOOP statistics. | Disclaimers embedded across all reports, registers, and the web portal. |
| **3** | Never create fake company performance claims from dataset. | Avoided vanity metrics; focused on analytical readiness and structure. |
| **4** | Never invent confidential security mechanisms. | Security assumptions marked as "To Be Verified" with engineering owners. |
| **5** | Never request passwords / API keys / payment credentials. | Strictly barred from analytics specifications; tokens hashed or excluded. |
| **6** | Never claim a proposed analytics event already exists. | All unverified events explicitly marked **Proposed** or **To Be Verified**. |
| **7** | Never hide uncertainty. | Assumption Register documents 15 high-risk operational unknowns. |
| **8** | Never convert an assumption into a fact. | Strict 3-tier status classification applied across all tables. |
| **9** | Never add unnecessary personal-data fields. | Exact birth dates bucketed into age ranges; raw emails replaced with hashes. |
| **10** | Never optimize the project for appearance instead of accuracy. | Deep technical evaluation of real failure modes and engineering blockers. |
| **11** | Every important analytical conclusion must be traceable. | Full provenance linked to official PDF sections or downloaded sheets. |
| **12** | Production data must replace simulated data through governance. | Data transition and CDC pipelines outlined in architectural notes. |

---

## 6. How to Run & Verify

1. **Install Python Prerequisites:**
   ```powershell
   pip install -r requirements.txt
   ```
2. **Re-export Deliverables & Validate Schemas:**
   ```powershell
   python scripts/export_registers_to_csv.py
   python scripts/profile_data.py
   ```
3. **Launch the Local Interactive Blueprint Portal:**
   ```powershell
   python scripts/serve_portal.py
   # Opens http://localhost:8080/index.html
   ```
