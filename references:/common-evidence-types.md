# Common Evidence Types in ITGC Testing

> A reference guide for interpreting what evidence proves — and what it
> does NOT prove — before drawing audit conclusions.
>
> Claude must never assume evidence proves more than it actually demonstrates.

---

## Evidence Index

| # | Evidence Type | Key Limitation |
|---|---|---|
| 1 | SQL Query Output | Does not prove upstream completeness |
| 2 | Code Snippet | Does not prove production deployment |
| 3 | UI Screenshot | Does not prove backend logic or enforcement |
| 4 | PagerDuty / Alert Screenshot | Does not prove all failure scenarios are covered |
| 5 | Pivot Table / Aggregated Workbook | Does not prove raw data is complete or unfiltered |
| 6 | Git Blame / Version History | Does not prove deployment to production |
| 7 | Architecture Diagram | Does not prove operational effectiveness |
| 8 | Batch Log / Job Log | Does not prove field-level accuracy |
| 9 | Impact Analysis / SAFE Document | Does not prove testing or proper deployment |
| 10 | Reviewer Sign-Off | Does not prove review was substantive |

---

## 1. SQL Query Output

| What It Proves | What It Does NOT Prove |
|---|---|
| Data presence | Upstream completeness |
| Field values | Transformation logic (unless script reviewed) |
| Record counts | That the query wasn't manually filtered |

**Best Practices:**
- Request the query text
- Confirm no undocumented `WHERE` clause exclusions
- Tie counts to the system of record

---

## 2. Code Snippet
*(Java · Go · Python · Lambda · SQL)*

| What It Proves | What It Does NOT Prove |
|---|---|
| Processing logic | Code is deployed to production |
| Conditional statements | Version hasn't changed |
| Routing logic | Monitoring exists |
| Allocation sequence | |

**Best Practices:**
- Confirm environment (QA vs. Prod)
- Inspect version history
- Tie to change ticket if applicable

---

## 3. UI Screenshot

| What It Proves | What It Does NOT Prove |
|---|---|
| Configuration setting | System-wide enforcement |
| Status | Backend logic |
| User entitlement | That alerts trigger properly |
| Alert existence | |

**Best Practices:**
- Pair with log evidence
- Validate backend logic if control is critical

---

## 4. PagerDuty / Alert Screenshot

| What It Proves | What It Does NOT Prove |
|---|---|
| Alert is configured | Trigger logic covers all failure scenarios |
| Alert triggered | Escalation was appropriate |
| Alert resolved | Root cause was fixed |

**Best Practices:**
- Request at least one triggered example
- Inspect the escalation path
- Validate service key alignment

---

## 5. Pivot Table / Aggregated Review Workbook

| What It Proves | What It Does NOT Prove |
|---|---|
| Reviewer performed a review | Raw data is complete |
| Aggregation was performed | No filtering occurred before the pivot |
| | No hidden rows present |

**Best Practices:**
- Request the raw extract
- Reperform the pivot independently
- Perform a raw-to-review VLOOKUP

---

## 6. Git Blame / Version History

| What It Proves | What It Does NOT Prove |
|---|---|
| Last modified date | Code is deployed to production |
| Author of change | Related files are unchanged |
| | Configuration files are unchanged |

**Best Practices:**
- Confirm branch and environment
- Confirm no changes during the in-scope period
- Tie to release log

---

## 7. Architecture Diagram

| What It Proves | What It Does NOT Prove |
|---|---|
| Intended system design | Operational effectiveness |
| System components | Implementation matches the diagram |
| Logical data flow | Monitoring covers all data hops |

**Best Practices:**
- Validate with execution logs
- Confirm actual job names against diagram
- Confirm active vs. legacy component status

---

## 8. Batch Log / Job Log

| What It Proves | What It Does NOT Prove |
|---|---|
| Job executed | Field-level accuracy |
| Success / failure status | Upstream data was correct |
| Record counts | Failure conditions are properly handled |

**Best Practices:**
- Inspect error handling logic
- Confirm monitoring is active on job failure
- Tie count to downstream table

---

## 9. Impact Analysis / SAFE Document

| What It Proves | What It Does NOT Prove |
|---|---|
| Management documented change rationale | Testing was performed |
| Risk evaluation occurred | Change was deployed properly |
| | Code matches documentation |

**Best Practices:**
- Inspect test evidence directly
- Confirm production deployment
- Confirm reviewer approval date

---

## 10. Reviewer Sign-Off

| What It Proves | What It Does NOT Prove |
|---|---|
| Review occurred | Review was substantive |
| Reviewer acknowledged | Reviewer inspected raw data |
| | Reviewer was independent |

**Best Practices:**
- Inspect reviewer notes
- Confirm no self-review occurred
- Confirm population tie-out was performed

---

## Final Rule for Claude

| If evidence only proves... | Do NOT imply... |
|---|---|
| Configuration | Operational testing |
| Logic | Completeness |
| Monitoring | Accuracy |
| Sign-off | Substantive review |

Always scope conclusions strictly to what was actually inspected.

---

*This reference guide supports IT audit documentation workflows.
It does not replace professional judgment or formal audit standards.*
