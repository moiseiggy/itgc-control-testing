# Control Objective → Test Matrix & Documentation Mapper

> This document maps common ITGC / SOX control types to appropriate test
> matrices, completeness & accuracy requirements, tester write-up templates,
> typical risks, and red flags.
>
> Claude uses this file to determine how to structure output automatically.

---

## Mapper Index

| # | Control Type | Core Objective |
|---|---|---|
| 1 | Data Interface / Data Movement | Ensure complete and accurate transfer of data from source to target |
| 2 | Access Review (UAR / Privileged) | Ensure access rights are appropriate and periodically reviewed |
| 3 | Change Monitoring / Code Controls | Ensure unauthorized changes do not occur or are properly approved |
| 4 | Approval Routing / Decision Engine | Ensure routing logic functions according to policy attributes |
| 5 | Allocation / Financial Processing | Ensure correct sequencing and allocation of financial transactions |
| 6 | Monitoring & Alerting | Ensure failures are detected and escalated timely |
| 7 | Update Testing / Migration | Ensure modernization does not impact control effectiveness |

---

## 1. Data Interface / Data Movement Controls
*(Examples: FS-006 · FS-028 · CARD-085 · COMM-097)*

**Objective:** Ensure complete and accurate transfer of data from source to target.

### Use These Matrices
- Completeness & Accuracy Tie-Out Matrix
- KDE Attribute Validation Matrix
- Allocation Logic Matrix *(if financial impact)*

### Required Sections
- Completeness (record counts, ingestion logs)
- Accuracy (KDE value comparison)
- Monitoring validation
- Exception handling logic

### Common Evidence
SQL queries · Record count screenshots · Batch logs · EMR/Glue/Lambda code · PagerDuty alerts · Splunk logs

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| Dropped records | Record count mismatches unexplained |
| Silent transformation logic | Manual Excel manipulations |
| Upstream filtering not disclosed | No source system tie-out |
| Hard-coded exclusions | Monitoring alerts configured but not tested |

---

## 2. Access Review Controls (UAR / Privileged Access)
*(Examples: DFS-UAR-011 · Snowflake UAR · Oracle DB Review · DynamoDB Review)*

**Objective:** Ensure access rights are appropriate and reviewed periodically.

### Use These Matrices
- Access Review Sampling Matrix
- Population Validation Matrix
- Raw-to-Review VLOOKUP Matrix
- Light-Touch C&A Matrix

### Required Sections
- Completeness of population
- Accuracy of extracted roles
- Reviewer evidence
- Terminated user validation
- Privileged access validation

### Common Evidence
Raw extracts (Postgres, AD, Snowflake) · PowerShell scripts · SQL scripts · Pivot tables · Reviewer sign-off logs

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| Population filtered before review | Reviewer reviewing their own access |
| Service accounts excluded | No QA over extract |
| Manual manipulation of review file | Aggregation logic unclear |
| Privileged roles not separately reviewed | System accounts excluded without documentation |

---

## 3. Change Monitoring / Code Controls
*(Examples: TECH-684 · Git Blame validation · SAFE changes)*

**Objective:** Ensure unauthorized changes do not occur or are properly approved.

### Use These Matrices
- Change Monitoring Matrix
- Git Version Validation Matrix
- Deployment Validation Matrix

### Required Sections
- Last modified date
- In-scope period validation
- Approval evidence
- Deployment evidence
- Post-implementation validation

### Common Evidence
Git history · Change tickets · SAFE documentation · Impact analysis · Vendor notifications

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| Retroactive approvals | No linkage between code and ticket |
| Emergency changes bypassing control | Version comparison not possible |
| QA-only validation | No evidence of testing in production |
| No production confirmation | Hard-coded changes undocumented |

---

## 4. Approval Routing / Decision Engine Controls
*(Examples: COMM-064 · COMM-099 · FDM Dashboard · CDAT)*

**Objective:** Ensure routing logic functions according to policy attributes.

### Use These Matrices
- Routing Logic Matrix
- Scenario-Based Sample Matrix
- Attribute Sensitivity Testing Matrix

### Required Sections
- Attribute-based routing validation
- Sample of one per scenario
- Risk rating changes
- Exposure changes
- Grid mapping validation

### Common Evidence
Code snippets · Policy grid · UI screenshots · API logs · Attribute tables

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| OR vs. AND logic misapplied | Inability to isolate routing logic |
| Hidden filtering upstream | Only positive testing performed |
| Hard-coded grid mapping | LGD / PD logic undocumented |
| Entitlements conflated with routing logic | No validation of lower-bound scenarios |

---

## 5. Allocation / Financial Processing Controls
*(Examples: FS-006 · Payment allocation · Interest calculation)*

**Objective:** Ensure correct sequencing and allocation of financial transactions.

### Use These Matrices
- Allocation Logic Matrix
- Tolerance Threshold Matrix
- Transaction Ordering Validation Matrix

### Required Sections
- Allocation sequence
- Tolerance validation
- Before / after balance validation
- Exception handling logic

### Common Evidence
Transaction-level logs · Posted sequence numbers · Allocation code · Balance snapshots

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| Allocation sequence incorrect | Balance reduction does not reconcile |
| Tolerance misapplied | Allocation code references wrong field |
| Partial payments mishandled | Hard-coded ordering |
| Overpayment logic flawed | Manual adjustments present |

---

## 6. Monitoring & Alerting Controls
*(Examples: PagerDuty setup · Lambda monitoring · Splunk alerts)*

**Objective:** Ensure failures are detected and escalated timely.

### Use These Matrices
- Monitoring & Alert Testing Matrix

### Required Sections
- Trigger condition
- Alert configuration
- Escalation evidence
- Resolution documentation

### Common Evidence
PagerDuty logs · SNS topics · Splunk dashboards · CloudWatch alerts

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| Alert configured but not tied to failure | No evidence of an actual triggered alert |
| No escalation path | Manual review disguised as automated |
| Alert fatigue | Dead letter queue unmonitored |
| Monitoring only infra-level, not business-level | |

---

## 7. Update Testing / Migration Controls
*(Examples: CDC → MSF migration (FS-028) · EMR → Glue migration)*

**Objective:** Ensure modernization does not impact control effectiveness.

### Use These Matrices
- Pre/Post Comparison Matrix
- KDE Validation Matrix
- Monitoring Validation Matrix

### Required Sections
- Technology change documented
- Core logic unchanged
- KDE integrity maintained
- Monitoring migrated
- No dropped tables

### Common Evidence
Architecture diagrams · New job code · Updated D1/D2 tables · Glue job configs

### Key Risks & Red Flags

| Risk | Red Flag |
|---|---|
| Logic altered unintentionally | "Lift and shift" claimed without evidence |
| New filters introduced | No mapping of old tables to new tables |
| Monitoring not migrated | No validation of new D1 tables |
| Downstream jobs not updated | |

---

## Quick Decision Guide

| If the control involves... | Use this approach |
|---|---|
| Record counts | Completeness Matrix |
| Role review | Access Review Matrix |
| Code logic | Code Inspection Template + Scenario Matrix |
| Routing logic | Routing Matrix |
| Allocation | Allocation Matrix |
| Git version | Change Monitoring Matrix |
| Migration | Pre/Post Comparison Matrix |

---

## Enforcement Rules for Claude

1. Identify the primary objective type
2. Determine whether completeness, accuracy, or both apply
3. Select the matrix accordingly
4. Include the appropriate tester write-up template
5. Flag gaps if evidence is insufficient
6. Avoid overstating assurance
7. Separate routing logic from entitlement logic if both exist

---

*This mapper provides structured reasoning guidance for ITGC and SOX
testing workflows. It does not replace professional judgment or formal
audit standards.*