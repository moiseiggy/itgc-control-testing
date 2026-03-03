# ITGC Test Matrix Templates

> Standardized matrix structures for recurring sample-based ITGC testing.
>
> Claude selects and adapts the appropriate matrix based on control type
> and objective. All matrices are Excel-copy friendly (pipe-delimited).

---

## Matrix Index

| # | Matrix | Use For |
|---|---|---|
| 1 | General Sample-Based Control Test | Data interfaces · Monitoring · Allocation · Routing · Control execution |
| 2 | Completeness & Accuracy Tie-Out | Pre/post files · Batch loads · Snowflake ingestion · PFC batch |
| 3 | Access Review Sampling | AD · Snowflake · Oracle · ServiceNow · DynamoDB · Mainframe |
| 4 | Change Monitoring / Git Validation | Git blame · Code changes · SAFE samples · Deployment verification |
| 5 | Allocation Logic Testing | Payment allocation · Interest/principal · Tolerance rules · MEA/MPE |
| 6 | Routing Logic / Approval Grid Validation | Approval routing · Attribute-based decision engines |
| 7 | Monitoring & Alert Testing | Failure detection · Alert configuration · Escalation validation |
| 8 | Population Completeness (Raw-to-Review) | Raw dataset inclusion in review workbook |
| 9 | Light-Touch C&A Reperformance | Independent recalculation · Attribute spot-check |

---

## Matrix Design Rules

Claude must always:

- Keep tables Excel-friendly (pipe-delimited)
- Avoid merged cells
- Avoid narrative inside tables
- Keep conclusions concise
- Not overstate assurance
- Separate completeness and accuracy when applicable
- Tie conclusions to evidence inspected

**When evidence is partial:** Build the matrix skeleton, identify gaps
clearly, flag missing evidence fields, and never fabricate counts.

---

## 1. General Sample-Based Control Test Matrix

**Use for:** Data interface testing · Monitoring validation · Allocation
validation · Routing logic testing · Control execution samples

**Control Objective:** [State objective clearly]

**Population Source:** [System / Query / Report Name]

**Sample Selection Method:** [Random / Risk-based / Specific scenario / Test of one / Threshold-based]

### Test Matrix

| Sample ID | Key Attributes Tested | Expected Result | Evidence Inspected | Result (Pass/Fail) | Tester Conclusion |
|---|---|---|---|---|---|
| S1 | [List attributes] | [Expected behavior] | [Logs / Query / Screenshot] | | |
| S2 | | | | | |
| S3 | | | | | |

---

## 2. Completeness & Accuracy Tie-Out Matrix

**Use for:** Pre-job vs. post-job files · Raw → Staging → Final · Batch
file → System load · Snowflake ingestion · PFC batch completeness

**Control Objective:** Ensure complete and accurate transfer of data
from [Source] to [Target].

### Record Count Reconciliation

| Stage | Record Count | Source of Evidence | Variance | Explanation | Conclusion |
|---|---|---|---|---|---|
| Raw Source | | | | | |
| Staging | | | | | |
| Final Output | | | | | |

### KDE Attribute Validation

| Sample ID | KDE 1 | KDE 2 | KDE 3 | Source Value | Target Value | Match (Y/N) | Notes |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

---

## 3. Access Review Sampling Matrix

**Use for:** AD · Snowflake · Oracle · ServiceNow · DynamoDB · Mainframe · Windows Server

**Control Objective:** Validate completeness and accuracy of user access review.

### Population Validation

| Step | Population Count | Source | Reviewed Count | Match (Y/N) | Notes |
|---|---|---|---|---|---|
| | | | | | |

### Sample Testing

| User ID | Role / Permission | Reviewer Decision | Evidence of Review | Terminated? | Appropriate Access? | Conclusion |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## 4. Change Monitoring / Git Validation Matrix

**Use for:** Git blame validation · Code change monitoring · SAFE change
samples · Deployment verification

**Control Objective:** Validate that unauthorized changes did not occur
during FY[XX].

### Version Validation

| File / Component | Last Modified Date | Modified By | In Scope Period? | Evidence Source | Conclusion |
|---|---|---|---|---|---|
| | | | | | |

### Deployment Validation *(if applicable)*

| Change ID | Change Date | Approval Evidence | Deployment Evidence | Post-Implementation Validation | Conclusion |
|---|---|---|---|---|---|
| | | | | | |

---

## 5. Allocation Logic Testing Matrix
*(FS-006 Style)*

**Use for:** Payment allocation · Interest vs. principal logic · $10
tolerance rule · MEA / MPE aggregation · Transaction ordering

**Control Objective:** Validate allocation logic processes transactions
according to documented business rules.

### Allocation Sequence Validation

| Sample ID | Transaction Type | Input Amount | Allocation Sequence Expected | Allocation Observed | Variance | Conclusion |
|---|---|---|---|---|---|---|
| | | | | | | |

### Tolerance Validation *(if applicable)*

| Sample ID | Payment Amount | Tolerance Threshold | Expected Behavior | Observed Behavior | Conclusion |
|---|---|---|---|---|---|
| | | | | | |

---

## 6. Routing Logic / Approval Grid Validation Matrix
*(COMM-064 / COMM-099 Style)*

**Control Objective:** Validate approval routing logic functions based
on defined attributes.

### Routing Validation

| Sample ID | Risk Rating | Exposure | LGD | Product Type | Grid Expected | Grid Observed | Match (Y/N) | Conclusion |
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |

---

## 7. Monitoring & Alert Testing Matrix

**Control Objective:** Validate monitoring alerts trigger on failure conditions.

### Alert Validation

| Job Name | Failure Simulated? | Alert Triggered? | Alert Timestamp | Escalation Evidence | Resolution Evidence | Conclusion |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## 8. Population Completeness Matrix
*(Raw-to-Review VLOOKUP)*

**Use for:** Validating raw dataset inclusion in review workbook.

### Population Inclusion Validation

| Raw Record ID | Present in Review? (Y/N) | Exception? | Explanation | Conclusion |
|---|---|---|---|---|
| | | | | |

---

## 9. Light-Touch C&A Reperformance Matrix

### Independent Reperformance

| Step | Source Count | Recalculated Count | Match (Y/N) | Notes |
|---|---|---|---|---|
| | | | | |

### Key Attribute Validation

| Record ID | Attribute | Source Value | Final Value | Match (Y/N) |
|---|---|---|---|---|
| | | | | |

---

*These templates provide documentation structure for ITGC and SOX testing
workflows. They do not replace professional judgment or formal audit standards.*
